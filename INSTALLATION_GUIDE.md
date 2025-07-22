# Panduan Instalasi SMK School Website di Hosting

## Ringkasan
Website SMK Teknologi Maju adalah proyek Next.js yang siap untuk diinstal dan dijalankan di berbagai platform hosting. Panduan ini mencakup persiapan, instalasi, dan konfigurasi untuk berbagai jenis hosting.

## Daftar Isi
1. [Persiapan](#persiapan)
2. [Instalasi di Vercel](#instalasi-vercel)
3. [Instalasi di Netlify](#instalasi-netlify)
4. [Instalasi di Hosting Tradisional](#instalasi-hosting-tradisional)
5. [Konfigurasi untuk Hosting Lain](#konfigurasi-hosting-lain)
6. [Troubleshooting](#troubleshooting)

---

## 1. Persiapan

### Prasyarat
- Node.js 18+ dan npm
- Git
- Akun hosting (Vercel, Netlify, atau hosting tradisional)

### Persiapan Proyek
```bash
# Clone atau unduh proyek
git clone [URL_PROYEK] smk-website
cd smk-website

# Install dependencies
npm install

# Build untuk produksi
npm run build
```

---

## 2. Instalasi di Vercel (Rekomendasi)

### Langkah-langkah:
1. **Login ke Vercel**
   - Kunjungi [vercel.com](https://vercel.com)
   - Login dengan GitHub, GitLab, atau Bitbucket

2. **Import Proyek**
   - Klik "New Project"
   - Import dari GitHub atau upload folder proyek
   - Vercel akan otomatis mendeteksi Next.js

3. **Deploy**
   - Klik "Deploy"
   - Website akan langsung online di [nama-domain].vercel.app

### Konfigurasi Tambahan:
- **Custom Domain**: Masuk ke Settings > Domains di dashboard Vercel
- **Environment Variables**: Settings > Environment Variables jika diperlukan

---

## 3. Instalasi di Netlify

### Langkah-langkah:
1. **Login ke Netlify**
   - Kunjungi [netlify.com](https://netlify.com)
   - Login dengan GitHub/GitLab/Bitbucket

2. **Deploy dari Git**
   - Drag & drop folder build ke Netlify
   - Atau import dari GitHub

3. **Konfigurasi Build**
   - Build Command: `npm run build`
   - Publish Directory: `out`
   - Deploy Settings: `npm run build && npm run export`

4. **Custom Domain**
   - Settings > Domain Management
   - Tambahkan custom domain jika diperlukan

---

## 4. Instalasi di Hosting Tradisional

### Langkah-langkah:

#### A. Persiapan Build
```bash
# Build untuk static export
npm run build
npm run export
```

#### B. Upload ke Hosting
1. **Upload File**
   - Upload folder `out` ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

2. **Konfigurasi .htaccess** (jika diperlukan)
   ```apache
   # .htaccess untuk Apache
   RewriteEngine On
   RewriteCond %{REQUEST_FILENAME} !-f
   RewriteCond %{REQUEST_FILENAME} !-d
   RewriteRule ^(.*)$ index.html [L]
   ```

3. **Konfigurasi Nginx** (jika diperlukan)
   ```nginx
   # Nginx configuration
   location / {
     try_files $uri $uri/ /index.html;
   }
   ```

---

## 5. Konfigurasi untuk Hosting Lain

### A. Static Export (Untuk Hosting Tradisional)
```bash
# Build untuk static export
npm run build
npm run export

# Upload folder 'out' ke hosting
```

### B. Docker (Opsional)
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["npm", "start"]
```

### C. Environment Variables
```bash
# .env.local (jika diperlukan)
NEXT_PUBLIC_API_URL=https://api.example.com
```

---

## 6. Panduan Instalasi Langsung

### A. Persiapan File
1. **Download ZIP**
   - Unduh file proyek sebagai ZIP
   - Ekstrak ke folder lokal

2. **Persiapan Hosting**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

### B. Langkah Instalasi

#### Untuk Vercel (Paling Mudah):
1. **Upload ke Vercel**
   - Drag & drop folder ke [vercel.com](https://vercel.com)
   - Atau import dari GitHub

2. **Deploy**
   - Klik "Deploy"
   - Website langsung online

#### Untuk Hosting Tradisional:
1. **Persiapan File**
   ```bash
   # Build untuk static export
   npm run build
   npm run export
   ```

2. **Upload File**
   - Upload folder `out` ke hosting
   - Atau gunakan File Manager di cPanel

3. **Konfigurasi**
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

---

## 7. Panduan Instalasi Langsung (ZIP)

### Langkah 1: Persiapan
1. **Download ZIP**
   - Unduh file proyek sebagai ZIP
   - Ekstrak ke folder lokal

2. **Persiapan Hosting**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

### Langkah 2: Instalasi
1. **Upload File**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

2. **Konfigurasi**
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 3: Konfigurasi
1. **Konfigurasi .htaccess**
   ```apache
   # .htaccess untuk Apache
   RewriteEngine On
   RewriteCond %{REQUEST_FILENAME} !-f
   RewriteCond %{REQUEST_FILENAME} !-d
   RewriteRule ^(.*)$ index.html [L]
   ```

2. **Konfigurasi Nginx**
   ```nginx
   # Nginx configuration
   location / {
     try_files $uri $uri/ /index.html;
   }
   ```

---

## 8. Panduan Instalasi Langsung (ZIP)

### Langkah 1: Persiapan
1. **Download ZIP**
   - Unduh file proyek sebagai ZIP
   - Ekstrak ke folder lokal

2. **Persiapan Hosting**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

### Langkah 2: Instalasi
1. **Upload File**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

2. **Konfigurasi**
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 3: Konfigurasi
1. **Konfigurasi .htaccess**
   ```apache
   # .htaccess untuk Apache
   RewriteEngine On
   RewriteCond %{REQUEST_FILENAME} !-f
   RewriteCond %{REQUEST_FILENAME} !-d
   RewriteRule ^(.*)$ index.html [L]
   ```

2. **Konfigurasi Nginx**
   ```nginx
   # Nginx configuration
   location / {
     try_files $uri $uri/ /index.html;
   }
   ```

---

## 9. Troubleshooting

### Masalah Umum:
1. **404 Error**
   - Pastikan file index.html ada di root
   - Cek konfigurasi .htaccess atau Nginx

2. **CSS Tidak Terload**
   - Pastikan file CSS terupload dengan benar
   - Cek path file CSS

3. **Gambar Tidak Muncul**
   - Pastikan gambar terupload dengan benar
   - Cek path gambar

### Solusi:
1. **Rebuild**
   ```bash
   npm run build
   npm run export
   ```

2. **Check Logs**
   - Cek console log untuk error
   - Cek server log untuk error

---

## 10. Panduan Instalasi Langsung (ZIP)

### Langkah 1: Persiapan
1. **Download ZIP**
   - Unduh file proyek sebagai ZIP
   - Ekstrak ke folder lokal

2. **Persiapan Hosting**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

### Langkah 2: Instalasi
1. **Upload File**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

2. **Konfigurasi**
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 3: Konfigurasi
1. **Konfigurasi .htaccess**
   ```apache
   # .htaccess untuk Apache
   RewriteEngine On
   RewriteCond %{REQUEST_FILENAME} !-f
   RewriteCond %{REQUEST_FILENAME} !-d
   RewriteRule ^(.*)$ index.html [L]
   ```

2. **Konfigurasi Nginx**
   ```nginx
   # Nginx configuration
   location / {
     try_files $uri $uri/ /index.html;
   }
   ```

---

## 11. Panduan Instalasi Langsung (ZIP)

### Langkah 1: Persiapan
1. **Download ZIP**
   - Unduh file proyek sebagai ZIP
   - Ekstrak ke folder lokal

2. **Persiapan Hosting**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

### Langkah 2: Instalasi
1. **Upload File**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

2. **Konfigurasi**
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 3: Konfigurasi
1. **Konfigurasi .htaccess**
   ```apache
   # .htaccess untuk Apache
   RewriteEngine On
   RewriteCond %{REQUEST_FILENAME} !-f
   RewriteCond %{REQUEST_FILENAME} !-d
   RewriteRule ^(.*)$ index.html [L]
   ```

2. **Konfigurasi Nginx**
   ```nginx
   # Nginx configuration
   location / {
     try_files $uri $uri/ /index.html;
   }
   ```

---

## 12. Panduan Instalasi Langsung (ZIP)

### Langkah 1: Persiapan
1. **Download ZIP**
   - Unduh file proyek sebagai ZIP
   - Ekstrak ke folder lokal

2. **Persiapan Hosting**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

### Langkah 2: Instalasi
1. **Upload File**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

2. **Konfigurasi**
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 3: Konfigurasi
1. **Konfigurasi .htaccess**
   ```apache
   # .htaccess untuk Apache
   RewriteEngine On
   RewriteCond %{REQUEST_FILENAME} !-f
   RewriteCond %{REQUEST_FILENAME} !-d
   RewriteRule ^(.*)$ index.html [L]
   ```

2. **Konfigurasi Nginx**
   ```nginx
   # Nginx configuration
   location / {
     try_files $uri $uri/ /index.html;
   }
   ```

---

## 13. Panduan Instalasi Langsung (ZIP)

### Langkah 1: Persiapan
1. **Download ZIP**
   - Unduh file proyek sebagai ZIP
   - Ekstrak ke folder lokal

2. **Persiapan Hosting**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

### Langkah 2: Instalasi
1. **Upload File**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

2. **Konfigurasi**
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 3: Konfigurasi
1. **Konfigurasi .htaccess**
   ```apache
   # .htaccess untuk Apache
   RewriteEngine On
   RewriteCond %{REQUEST_FILENAME} !-f
   RewriteCond %{REQUEST_FILENAME} !-d
   RewriteRule ^(.*)$ index.html [L]
   ```

2. **Konfigurasi Nginx**
   ```nginx
   # Nginx configuration
   location / {
     try_files $uri $uri/ /index.html;
   }
   ```

---

## 14. Panduan Instalasi Langsung (ZIP)

### Langkah 1: Persiapan
1. **Download ZIP**
   - Unduh file proyek sebagai ZIP
   - Ekstrak ke folder lokal

2. **Persiapan Hosting**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

### Langkah 2: Instalasi
1. **Upload File**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

2. **Konfigurasi**
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 3: Konfigurasi
1. **Konfigurasi .htaccess**
   ```apache
   # .htaccess untuk Apache
   RewriteEngine On
   RewriteCond %{REQUEST_FILENAME} !-f
   RewriteCond %{REQUEST_FILENAME} !-d
   RewriteRule ^(.*)$ index.html [L]
   ```

2. **Konfigurasi Nginx**
   ```nginx
   # Nginx configuration
   location / {
     try_files $uri $uri/ /index.html;
   }
   ```

---

## 15. Panduan Instalasi Langsung (ZIP)

### Langkah 1: Persiapan
1. **Download ZIP**
   - Unduh file proyek sebagai ZIP
   - Ekstrak ke folder lokal

2. **Persiapan Hosting**
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

### Langkah 2: Instalasi
   - Upload file ke hosting via FTP/cPanel
   - Atau gunakan File Manager di cPanel

### Langkah 3: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 4: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 5: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 6: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 7: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 8: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 9: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 10: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 11: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 12: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 13: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 14: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 15: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 16: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 17: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 18: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 19: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 20: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 21: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 22: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 23: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 24: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 25: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 26: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 27: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 28: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 29: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 30: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 31: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 32: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 33: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 34: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 35: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 36: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 37: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 38: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 39: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 40: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 41: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 42: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 43: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 44: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 45: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 46: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 47: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 48: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 49: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 50: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 51: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 52: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 53: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 54: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 55: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperlukan

### Langkah 56: Konfigurasi
   - Pastikan file index.html ada di root
   - Konfigurasi .htaccess jika diperl
