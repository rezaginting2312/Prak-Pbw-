## ✨ Author
**Nama:** Reza Brema Ginting  
**NPM:** 4523210092  
**Mata Kuliah:** Praktikum Pemrograman Berbasis Web  
**Repository:** [GitHub - Prak-Pbw-](https://github.com/rezaginting2312/Prak-Pbw-.git)
# Prak-Pbw-
# 📰 Aplikasi Berita dengan Fitur Komentar & Panel Admin (FilamentPHP)

Proyek ini adalah aplikasi berbasis **Laravel** dengan fitur utama untuk menampilkan daftar berita, membaca detail berita, menambahkan komentar dari pengunjung, serta panel admin menggunakan **FilamentPHP** untuk mengelola data berita, wartawan, dan komentar.

---

## 🚀 Fitur Utama

### 👥 Pengguna Umum
- Melihat daftar berita.
- Membaca detail berita.
- Menambahkan komentar pada setiap berita.

### 🛠️ Admin (Filament)
- Mengelola data **berita**, **wartawan**, dan **komentar** melalui dashboard.
- CRUD (Create, Read, Update, Delete) semua data dari panel admin.
- Tampilan admin modern menggunakan **FilamentPHP**.

---

## 🧩 Teknologi yang Digunakan

- **Laravel 11**
- **PHP 8+**
- **MySQL / MariaDB**
- **FilamentPHP v3**
- **Blade Template**
- **Eloquent ORM**

---

## 📂 Struktur Folder Utama

```
app/
 ├── Filament/
 │   └── Resources/
 │       ├── NewsResource/
 │       ├── WartawanResource/
 │       └── KomentarResource/
 ├── Http/
 │   ├── Controllers/
 │   │   ├── NewsController.php
 │   │   ├── KomentarController.php
 │   │   └── Admin/
 │   │       └── KomentarController.php
 │   └── Models/
 │       ├── News.php
 │       ├── Komentar.php
 │       └── Wartawan.php
resources/
 ├── views/
 │   ├── news/
 │   │   ├── index.blade.php
 │   │   └── show.blade.php
 │   └── layouts/
database/
 ├── migrations/
 └── seeders/
```

---

## ⚙️ Instalasi & Menjalankan Proyek

1. **Clone Repository**
   ```bash
   git clone https://github.com/rezaginting2312/Prak-Pbw-.git
   cd Prak-Pbw-
   ```

2. **Install Dependencies**
   ```bash
   composer install
   npm install && npm run dev
   ```

3. **Konfigurasi Environment**
   - Duplikat file `.env.example` menjadi `.env`
   - Ubah konfigurasi database sesuai kebutuhan:
     ```
     DB_DATABASE=nama_database
     DB_USERNAME=root
     DB_PASSWORD=
     ```

4. **Generate Key**
   ```bash
   php artisan key:generate
   ```

5. **Migrasi & Seeder**
   ```bash
   php artisan migrate --seed
   ```

6. **Jalankan Server Lokal**
   ```bash
   php artisan serve
   ```

7. Akses:
   - **Website publik:** [http://localhost:8000/news](http://localhost:8000/news)
   - **Dashboard Admin:** [http://localhost:8000/admin](http://localhost:8000/admin)

---

## 💬 Fitur Komentar (Frontend)

- Pengguna dapat menulis komentar langsung di halaman detail berita.
- Komentar disimpan di tabel `komentars`.
- Setiap komentar berelasi dengan satu berita (`news_id`).

---

## 🧠 Relasi Database

| Tabel | Relasi |
|-------|---------|
| `news` | memiliki banyak `komentars` |
| `komentars` | milik satu `news` |
| `wartawans` | dapat terhubung dengan `news` |

Contoh di model:

```php
// App\Models\News.php
public function komentars() {
    return $this->hasMany(Komentar::class);
}

// App\Models\Komentar.php
public function news() {
    return $this->belongsTo(News::class);
}
```

---

## 🔑 Login Admin Filament

Jika kamu menggunakan seeder bawaan:
```
Email: admin@example.com
Password: password
```

> Kamu bisa ubah atau buat akun admin baru melalui seeder atau artisan command.

---
Tampilan Daftar Berita
<img width="1919" height="1079" alt="Screenshot 2025-11-12 175430" src="https://github.com/user-attachments/assets/5e9eacb6-da65-4355-a546-4a84e16323b5" />

Tampilan Komentar
<img width="1919" height="1079" alt="Screenshot 2025-11-12 185558" src="https://github.com/user-attachments/assets/83f94112-381b-46b7-82f4-6d2d97a655eb" />
<img width="1892" height="1079" alt="Screenshot 2025-11-12 185831" src="https://github.com/user-attachments/assets/07892d07-d515-437e-b5b9-5b0e4a4138b3" />
<img width="1919" height="1079" alt="Screenshot 2025-11-12 185842" src="https://github.com/user-attachments/assets/f1b31a3f-d633-483c-aa54-f95c29d11d70" />
<img width="1919" height="1079" alt="Screenshot 2025-11-12 185853" src="https://github.com/user-attachments/assets/8605c3b4-f0ad-4d09-a1fb-e554e78035bc" />



## 🧾 License
Proyek ini dibuat untuk keperluan pembelajaran mata kuliah **Praktikum Pemrograman Berbasis Web**  
© 2025 — bebas digunakan untuk keperluan akademik.

---


