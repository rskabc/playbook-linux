# 🚀 Ansible Playbook: Setup Server AlmaLinux

Playbook ini digunakan untuk otomatisasi setup awal server berbasis **AlmaLinux**, meliputi instalasi paket utilitas, konfigurasi SNMP, NTP lokal Indonesia, dan banner keamanan SSH.

---

## 📁 Nama File

```bash
setupserver.yml
```

---

## 📦 Fitur yang Dilakukan oleh Playbook

### ✅ Install Paket
- `htop`, `nano`, `tree`, `curl`, `wget`, `zip`, `unzip`, `git`, `yum-utils`
- `net-tools`, `bind-utils`, `traceroute`, `snmp`, `chrony`, `bash-completion`, `EPEL`

### 🔐 Konfigurasi SNMP (v2c)
- Community: `public`
- Lokasi: `Jakarta, Indonesia`
- Kontak: `reski.abuchaer@gmail.com`

### ⏰ Konfigurasi NTP (Chrony)
- Server: `0.id.pool.ntp.org`, `1.id.pool.ntp.org`

### 📢 Konfigurasi SSH Banner
Menampilkan peringatan saat user login ke SSH:
```
Peringatan: Akses ke sistem ini diawasi. Segala aktivitas Anda dapat dicatat dan diaudit.
Jika Anda tidak berwenang, segera keluar dari sistem ini.
```

---

## ▶️ Cara Menjalankan

1. Buat inventori misalnya `inventory.ini`:
```ini
[almalinux]
192.168.1.100 ansible_user=root
```

2. Jalankan playbook:
```bash
ansible-playbook -i inventory.ini setupserver.yml
```

> Pastikan kamu memiliki akses SSH ke server dan `python` sudah tersedia di sana.

---

## 🛡️ Catatan Keamanan

- Pastikan hanya mengatur SNMP dengan akses jaringan terbatas jika menggunakan community string publik.
- Jangan lupa ubah `ansible_user` jika bukan `root`.

---

## 👨‍💻 Pembuat

Chaerul | [chaer.newbie@gmail.com](mailto:chaer.newbie@gmail.com)