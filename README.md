
# SIMPUS D‑CARE — Laravel Bug‑Fix Test

**Tujuan:** Menguji kemampuan kandidat menemukan dan memperbaiki bug kode PHP/Laravel yang umum
terjadi pada modul *Patient Management* (pendaftaran & listing pasien) dalam sistem informasi puskesmas (SIMPUS).

## Instruksi Kandidat
1. Fork/clone repo ini atau download sebagai ZIP, lalu buka di environment Laravel lokal Anda.
2. Jalankan `composer install` serta `cp .env.example .env` & atur koneksi database.
3. Jalankan `php artisan migrate:fresh --seed` (disediakan seeder sederhana).
4. Aplikasi seharusnya menampilkan daftar pasien di `/patients`, dan form tambah di `/patients/create`.
   Saat ini terdapat **≥10 bug** (fatal error, logic error, validation, security) yang membuat aplikasi tidak berjalan sesuai harapan.
5. Perbaiki seluruh bug hingga:
   - Rute `/patients` menampilkan tabel pasien tanpa error.
   - Rute `/patients/create` dapat menyimpan data valid & melakukan validasi field wajib.
   - CSRF & mass‑assignment aman.
6. Buat commit terpisah per bug yang Anda perbaiki dan jelaskan perbaikannya di pesan commit.
7. Kirim URL repo atau ZIP hasil perbaikan ke tim rekrutmen paling lambat 24 jam setelah menerima tes.

## Bug Checklist (disembunyikan untuk kandidat)
- Namespace/`use` salah → **PatientController**
- Tidak `use` Model → **PatientController**
- Validation kosong
- Mass assignment tidak dilindungi
- Route salah method
- Blade lupa `@csrf`
- Query builder ambil kolom salah
- Migration tipe data keliru
- Seeder tidak dipanggil
- View pakai variable undefined

*Selamat mengerjakan!*
