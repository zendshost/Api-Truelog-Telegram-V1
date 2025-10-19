# 🤖 Secure Notifier Bot v1.0

![Lisensi MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Node.js](https://img.shields.io/badge/Node.js-v18.x-green.svg)
![Express.js](https://img.shields.io/badge/Express-4.x-orange.svg)
![Telegraf.js](https://img.shields.io/badge/Telegraf-4.x-blue.svg)

**Secure Notifier Bot** adalah sebuah backend tangguh yang dibangun dengan Node.js dan Express, terintegrasi dengan bot Telegram untuk menyediakan sistem notifikasi yang aman, cepat, dan andal. Proyek ini dirancang untuk memudahkan developer menerima pemberitahuan penting dari aplikasi atau server mereka langsung ke akun Telegram.

---

## ✨ Fitur Utama

-   **🚀 Notifikasi Real-time:** Kirim pemberitahuan secara instan melalui API endpoint yang aman.
-   **🔐 Keamanan Terjamin:** Menggunakan variabel lingkungan (`.env`) untuk menyimpan token rahasia dan konfigurasi.
-   **⚙️ Mudah Dikonfigurasi:** Cukup dengan beberapa langkah untuk menjalankan bot di server Anda.
-   **📝 Logging:** Dilengkapi sistem logging untuk memantau aktivitas server dan bot.
-   ** scalable:** Arsitektur modular yang mudah dikembangkan untuk fitur-fitur baru.
-   **💬 Interaksi Bot:** Perintah dasar pada bot untuk memeriksa status dan mendapatkan bantuan.

---

## 📋 Prasyarat

Sebelum memulai, pastikan Anda telah menginstal perangkat lunak berikut di sistem Anda:

-   [Node.js](https://nodejs.org/) (disarankan versi 18.x atau lebih baru)
-   [npm](https://www.npmjs.com/) atau [yarn](https://yarnpkg.com/)
-   Akun Telegram

Anda juga memerlukan **Bot Token** dari Telegram. Dapatkan dengan berbicara pada [@BotFather](https://t.me/BotFather) di Telegram dan ikuti instruksinya.

---

## 🛠️ Instalasi & Konfigurasi

Ikuti langkah-langkah di bawah ini untuk menjalankan proyek ini di lingkungan lokal atau server Anda.

**1. Clone Repositori**

```bash
git clone https://github.com/username/secure-notifier-bot.git
cd secure-notifier-bot
```

**2. Instal Dependensi**

Gunakan `npm` atau `yarn` untuk menginstal semua paket yang dibutuhkan.

```bash
npm install
```
*atau*
```bash
yarn install
```

**3. Konfigurasi Lingkungan**

Salin file `.env.example` menjadi `.env` dan isi variabel yang diperlukan.

```bash
cp .env.example .env
```

Buka file `.env` dan sesuaikan nilainya:

```dotenv
# Konfigurasi Server
PORT=3000

# Konfigurasi Bot Telegram
# Dapatkan token dari @BotFather
TELEGRAM_BOT_TOKEN="ISI_DENGAN_TOKEN_BOT_ANDA"

# ID Chat Admin (opsional, untuk notifikasi khusus)
# Dapatkan ID Anda dari @userinfobot
ADMIN_CHAT_ID="ISI_DENGAN_ID_CHAT_ADMIN"

# Kunci Rahasia untuk Endpoint API
# Gunakan string acak yang kuat untuk keamanan
API_SECRET_KEY="GANTI_DENGAN_KUNCI_RAHASIA_ANDA"
```

**4. Jalankan Aplikasi**

Setelah konfigurasi selesai, jalankan server dengan perintah berikut:

```bash
npm start
```

Server Anda sekarang akan berjalan di `http://localhost:3000` (atau port yang Anda tentukan). Bot Telegram Anda juga sudah aktif dan siap menerima perintah.

---

## 🚀 Cara Penggunaan

### Interaksi dengan Bot

Buka aplikasi Telegram Anda dan cari bot yang telah Anda buat. Anda bisa memulai interaksi dengan perintah berikut:

-   `/start` - Memulai bot dan menampilkan pesan selamat datang.
-   `/status` - Memeriksa status kesehatan server dan koneksi bot.
-   `/help` - Menampilkan daftar perintah yang tersedia.

### Mengirim Notifikasi via API

Proyek ini menyediakan sebuah endpoint API yang aman untuk mengirim notifikasi. Anda bisa memanggilnya dari aplikasi atau layanan lain.

**Endpoint:** `POST /api/notify`

**Headers:**
- `Content-Type`: `application/json`
- `X-API-Secret`: `GANTI_DENGAN_KUNCI_RAHASIA_ANDA` (sesuai `.env`)

**Body (JSON):**

```json
{
  "message": "⚠️ Peringatan: Penggunaan CPU server mencapai 95%!",
  "priority": "high"
}
```

Contoh penggunaan dengan `curl`:

```bash
curl -X POST http://localhost:3000/api/notify \
-H "Content-Type: application/json" \
-H "X-API-Secret: GANTI_DENGAN_KUNCI_RAHASIA_ANDA" \
-d '{"message": "✅ Deployment berhasil di lingkungan produksi.", "priority": "low"}'
```

Notifikasi akan langsung dikirim ke `ADMIN_CHAT_ID` yang telah dikonfigurasi.

---

## 📁 Struktur Proyek

```
.
├── sessions/         # Direktori untuk menyimpan file sesi (jika ada)
├── index.js          # File utama aplikasi
├── .env              # File konfigurasi lingkungan (Jangan di-commit)
├── .env.example      # Contoh file konfigurasi
├── package.json      # Daftar dependensi dan skrip proyek
├── package-lock.json # Kunci versi dependensi
└── README.md         # Dokumentasi ini
```

---

## 🤝 Berkontribusi

Kontribusi dari komunitas sangat kami hargai! Jika Anda ingin berkontribusi, silakan:

1.  **Fork** repositori ini.
2.  Buat *branch* baru (`git checkout -b fitur/nama-fitur`).
3.  Lakukan perubahan dan **commit** (`git commit -m 'Menambahkan fitur X'`).
4.  **Push** ke *branch* Anda (`git push origin fitur/nama-fitur`).
5.  Buka **Pull Request**.

---

## 📄 Lisensi

Proyek ini dilisensikan di bawah [Lisensi MIT](LICENSE).

---

## 📞 Developer & Dukungan

Proyek ini dikelola dan dikembangkan oleh **zendshost**.

-   **Telegram:** [@zendshost](https://t.me/zendshost)

> **Catatan Komersial:**
> Skrip ini juga tersedia sebagai produk berbayar dengan dukungan penuh dan fitur tambahan seharga **Rp 1.000.000,-**. Jika Anda tertarik untuk membeli versi komersial atau membutuhkan kustomisasi, silakan hubungi kontak di atas.
