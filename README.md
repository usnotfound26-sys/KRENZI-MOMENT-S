# KRENZI MOMENTS — Starter Website

Paket awal photobooth multi-screen yang bisa diunggah ke GitHub Pages.

## Cara memasang
1. Ekstrak ZIP ini.
2. Buat repository baru di GitHub.
3. Upload **isi folder** ini (index.html, style.css, script.js, README.md), bukan folder ZIP-nya.
4. Commit perubahan.
5. Buka **Settings → Pages**.
6. Pada Build and deployment, pilih **Deploy from a branch**.
7. Pilih branch `main` dan folder `/ (root)` (di GitHub biasanya tertulis `/ (root)`, bukan `/root`), lalu Save.
8. Tunggu GitHub Pages menerbitkan situs. Buka URL yang ditampilkan di bagian Pages.

## Fitur yang sudah ada di paket awal
- Alur multi-screen: Home → Event Setup → Frame → Layout → Camera → Result.
- 11 pilihan frame bernama sesuai keputusan proyek.
- Layout Selector terpisah dari frame, tanpa layout 2×2 wajib.
- Akses kamera browser, countdown, beberapa filter, ambil foto, hapus/retake foto.
- Preview hasil, unduh PNG, dan berbagi melalui share sheet bila didukung browser.
- Tampilan responsif untuk HP dan laptop.

## Penting: status desain frame
Daftar 10 frame utama dipertahankan berdasarkan nama/tema yang telah disepakati. Paket starter ini memakai ilustrasi CSS sederhana sebagai placeholder visual; ini **belum merupakan reproduksi final** dari 10 desain preview yang sebelumnya disetujui. Cousins Edition menampilkan nama dekoratif: ABI • DIVA • RISKA • AIYRA. Sebelum publikasi final, aset frame perlu disempurnakan agar cocok dengan desain referensi yang disetujui.

## Penting: pengiriman email otomatis
GitHub Pages hanya menyajikan file statis dan tidak dapat mengirim email otomatis dengan aman sendirian. Tombol Send to Email sudah disiapkan, tetapi **belum akan mengirim email sampai backend email aman dikonfigurasi**.

Untuk mengaktifkannya:
1. Siapkan backend HTTPS (misalnya serverless function) yang menerima `multipart/form-data` dengan field `email`, `photo`, dan `eventName`.
2. Backend harus memvalidasi alamat email, membatasi ukuran file, menerapkan rate limit, dan mengirim PNG sebagai lampiran melalui penyedia email.
3. Di `script.js`, sebelum dipublikasikan, tambahkan konfigurasi:
   `window.KRENZI_EMAIL_ENDPOINT = "https://alamat-backend-kamu.example/send";`
4. Jangan pernah menaruh password SMTP, API secret, atau private key di `script.js` atau repository publik.

## Catatan kamera
Akses kamera memerlukan izin browser dan secure context (HTTPS). GitHub Pages menggunakan HTTPS. Jika kamera tidak terbuka, periksa izin kamera browser dan pastikan halaman dibuka dari URL HTTPS.

## Catatan
Ini adalah paket starter yang bisa diuji dan dikembangkan. Periksa kamera, ukuran layar, dan hasil unduhan di perangkat target sebelum dipakai pada acara sungguhan.
