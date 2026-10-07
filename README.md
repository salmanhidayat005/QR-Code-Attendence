# QR Code Scanner Attendance Device

PHP 8+ aur MySQL par mabni project. Frontend, backend aur database alag alag folders mein hain.

## Folder structure
```
qr-attendance/
├── index.php                  Front controller (saari requests yahan se)
├── config/config.php          Settings (DB user/pass, timezone, default admin)
├── database/
│   ├── Database.php           MySQL connection + auto install
│   └── schema.sql             Tables (users, people, attendance)
├── backend/
│   ├── helpers.php            Chhote helper functions
│   ├── routes.php             Saare routes (?r=...)
│   ├── models/                User.php, Person.php, Attendance.php
│   └── controllers/           Auth, Dashboard, People, Attendance, Scan
└── frontend/
    ├── views/                 layout, login, dashboard, people, card, attendance, password, scan
    └── assets/
        ├── css/               style.css, scan.css
        └── js/                scan.js, card.js
```

## Setup
1. XAMPP/WAMP mein Apache + MySQL start karein.
2. Poora `qr-attendance` folder `htdocs/` mein copy karein.
3. `config/config.php` mein DB user/password check karein (XAMPP default: root, khali password).
4. Browser mein `http://localhost/qr-attendance/` kholein. Database aur tables khud ban jayenge.
5. Login: `admin` / `admin123` (turant Password page se badal lein).

## Routes
| URL | Kaam |
|---|---|
| `?r=scan` | Scanner device page (public) |
| `?r=api_scan` (POST JSON `{"code":"..."}`) | Scan API |
| `?r=login`, `?r=logout`, `?r=password` | Admin auth |
| `?r=dashboard` | Dashboard |
| `?r=people`, `?r=card&id=1` | People aur QR card |
| `?r=attendance` | Report + CSV export |

## Note
Camera sirf `localhost` ya HTTPS par chalta hai. Online hosting par SSL zaroor lagayein.
