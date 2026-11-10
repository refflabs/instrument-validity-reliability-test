# Instrument Validity & Reliability Test

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/refflabs/instrument-validity-reliability-test/blob/main/notebooks/Uji_Validitas_Reliabilitas_Modul.ipynb)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)

Repository ini berisi skrip Jupyter Notebook untuk melakukan **Uji Validitas** dan **Uji Reliabilitas** data instrumen kuesioner berskala Likert secara otomatis menggunakan Python.

---

## 📌 Fitur Utama

1. **Uji Validitas (Pearson Product-Moment & Corrected Item-Total Correlation)**
   - Menghitung nilai $r_{\text{hitung}}$ butir terhadap total skor per dimensi.
   - Perhitungan otomatis $r_{\text{tabel}}$ berdasarkan derajat kebebasan ($df = n - 2$) dan taraf signifikansi $\alpha = 0{,}05$.
   - Penentuan status butir (*Valid* / *Tidak valid*).

2. **Uji Reliabilitas (Cronbach's Alpha)**
   - Menghitung koefisien *Cronbach's Alpha* per dimensi instrumen.
   - Kategorisasi tingkat reliabilitas (*Sangat baik*, *Baik*, *Reliabel*, *Tidak reliabel*).
   - Analisis *Alpha if item deleted* untuk melihat pengaruh penghapusan butir terhadap reliabilitas keseluruhan.

3. **Simulasi Eliminasi Butir Tidak Valid**
   - Menguji ulang nilai reliabilitas setelah butir yang tidak valid dibuang.

4. **Export Otomatis ke Excel**
   - Menyimpan tabel rekapitulasi validitas dan reliabilitas ke dalam file `hasil_uji_validitas_reliabilitas.xlsx` multi-sheet.

---

## 📂 Struktur Proyek

```text
instrument-validity-reliability-test/
├── .gitignore
├── LICENSE
├── README.md
├── requirements.txt
└── notebooks/
    └── Uji_Validitas_Reliabilitas_Modul.ipynb
```

---

## 🚀 Cara Menjalankan

### Opsi 1: Google Colab (Paling Mudah)
Klik tombol badge di atas atau klik tautan berikut:  
👉 [**Buka di Google Colab**](https://colab.research.google.com/github/refflabs/instrument-validity-reliability-test/blob/main/notebooks/Uji_Validitas_Reliabilitas_Modul.ipynb)

Tinggal jalankan setiap cell secara berurutan dan unggah file Excel kuesioner Anda saat diminta pada Langkah 2.

### Opsi 2: Lokal (VS Code / Jupyter Notebook)

1. Clone repositori:
   ```bash
   git clone https://github.com/refflabs/instrument-validity-reliability-test.git
   cd instrument-validity-reliability-test
   ```

2. Buat virtual environment (opsional tapi disarankan):
   ```bash
   python -m venv venv
   # Di Windows:
   venv\Scripts\activate
   # Di macOS/Linux:
   source venv/bin/activate
   ```

3. Pasang dependensi yang diperlukan:
   ```bash
   pip install -r requirements.txt
   ```

4. Buka notebook:
   ```bash
   jupyter notebook notebooks/Uji_Validitas_Reliabilitas_Modul.ipynb
   ```
   *(Catatan: Jika dijalankan di lingkungan lokal non-Colab, ubah bagian `files.upload()` pada Langkah 2 menjadi pembacaan file lokal seperti `df = pd.read_excel("path/ke/file.xlsx")`)*.

---

## 📋 Format Data Masukan

Program dirancang untuk membaca file spreadsheet (`.xlsx`) dengan ketentuan:
- Kolom-kolom awal merupakan data demografi (misal: *Timestamp*, *Kelas*, *Jenis Kelamin*).
- Kolom butir kuesioner menggunakan format penamaan `Dimensi [Pertanyaan]`.
- Respon kuesioner menggunakan skala Likert standar 5 poin:
  - *Sangat Tidak Setuju (STS)* $\rightarrow$ 1
  - *Tidak Setuju (TS)* $\rightarrow$ 2
  - *Netral (N)* $\rightarrow$ 3
  - *Setuju (S)* $\rightarrow$ 4
  - *Sangat Setuju (SS)* $\rightarrow$ 5

---

## 📄 Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE).
