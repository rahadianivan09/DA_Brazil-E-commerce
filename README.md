> **Penting:** Pastikan menjalankan perintah dari folder `submission/`, 
bukan dari dalam folder `dashboard/`. Path data CSV bersifat relatif 
terhadap lokasi pemanggilan.

---

# 🛒 Brazilian E-Commerce Analytics Dashboard

## 📋 Deskripsi Proyek
Dashboard analisis interaktif berbasis Streamlit untuk dataset Brazilian E-Commerce Public (Olist), mencakup analisis delivery, revenue, RFM segmentation, dan geospatial.

---

## 🚀 Setup Environment

### 1. Clone Repository
```bash
git clone https://github.com/rahadianivan09/DA_Brazil-E-commerce.git
cd DA_Brazil-E-commerce
```

### 2. Buat Virtual Environment
```bash
python -m venv venv
```

### 3. Aktifkan Virtual Environment
- **Windows:**
```bash
  venv\Scripts\activate
```
- **Mac/Linux:**
```bash
  source venv/bin/activate
```

### 4. Install Dependencies
```bash
pip install -r requirements.txt
```

### 5. Jalankan Dashboard
```bash
streamlit run Dashboard/dashboard.py
```

Dashboard akan otomatis terbuka di browser: `http://localhost:8501`

---

## ☁️ Dashboard Online (Streamlit Cloud)

Dashboard sudah di-deploy dan dapat diakses di:

👉 **[Link Dashboard](https://ecomercebrazildashboard.streamlit.app/)**

> Lihat `url.txt` untuk link terbaru.

---

## 📦 Dataset

**Brazilian E-Commerce Public Dataset by Olist**

- Sumber: [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- Periode: September 2016 – Oktober 2018
- 9 tabel relasional dengan 99,441 orders

| Tabel | Baris | Keterangan |
|---|---|---|
| orders | 99,441 | Tabel utama transaksi |
| order_items | 112,650 | Detail item per order |
| order_payments | 103,886 | Metode & nilai pembayaran |
| order_reviews | 99,224 | Review & rating pelanggan |
| products | 32,951 | Informasi produk |
| customers | 99,441 | Data pelanggan |
| sellers | 3,095 | Data seller |
| geolocation | 1,000,163 | Koordinat per zip code |
| category_names | 71 | Terjemahan nama kategori |

---

## 🔬 Metode Analisis

### Analisis Utama
- **Delivery Delay Analysis** — Kalkulasi selisih hari antara 
  actual vs estimated delivery date per kategori produk
- **Review Score Correlation** — Korelasi Pearson antara 
  delivery delay dan customer satisfaction score
- **Revenue Trend Analysis** — Tren pendapatan bulanan (MoM growth)
- **Payment Method Analysis** — Distribusi kontribusi tiap metode pembayaran

### Analisis Lanjutan
- **RFM Analysis** — Segmentasi 93,358 pelanggan unik ke 8 segmen 
  berdasarkan Recency, Frequency, dan Monetary value
- **Geospatial Analysis** — Distribusi order, revenue, dan kepuasan 
  pelanggan berdasarkan 27 state di Brasil

---

## 📈 Key Findings

### Pertanyaan 1 — Delivery & Review
- Korelasi negatif moderat (r = -0.23) antara delay dan review score
- Semua kategori rata-rata dikirim **lebih cepat** dari estimasi
- Review anjlok ke **1.698** saat terlambat >7 hari (vs 4.224 saat early)
- Kategori bermasalah di antara top 10 delay terlama: Audio (3.83) dan Home Confort (3.86) — review rendah bukan karena delay tapi kualitas produk

### Pertanyaan 2 — Revenue & Payment
- Revenue tumbuh dari 127,545 BRL (Jan 2017) ke puncak 
  **1,153,528 BRL** (Nov 2017 — Black Friday effect, +53.57% MoM)
- **Credit card mendominasi 78.45%** revenue dengan avg cicilan 3.5x
- Sejak 2018 revenue stabil di kisaran 1M BRL per bulan

### RFM Segmentation
- Segmen terbesar: **At Risk** (17,463 pelanggan / 18.7%)
- Segmen paling berharga: **Champions** (avg monetary R$280)
- **Potential Loyalists** (avg R$258) — peluang upgrade terbesar

### Geospatial
- **SP dominasi 43.3%** dari total orders (40,399 orders)
- Top 3 state (SP, RJ, MG) = 68.6% total orders (64,028 orders)
- Revenue per order tertinggi di state kecil: BA (R$181.66)

---

## 🎯 Rekomendasi Action Item

1. **Investigasi kualitas produk** Audio & Home Confort — masuk top 10 delay terlama namun review tetap rendah (3.83 dan 3.86), indikasi masalah kualitas produk bukan delay
2. **Eliminasi Very Late delivery** (>7 hari) yang membuat 
   review anjlok dari 4.224 ke 1.698
3. **Replikasi Black Friday** ke event belanja lain seperti Cyber Monday untuk menduplikasi lonjakan revenue +53%
4. **Win-back campaign** untuk segmen At Risk (17,463 pelanggan) 
   via email personalisasi + diskon eksklusif
5. **Upgrade Potential Loyalists** menjadi Champions 
   melalui program reward — monetary hampir setara (R$258 vs R$280)

---

## 🛠️ Tech Stack

| Library | Versi | Kegunaan |
|---|---|---|
| pandas | 2.1.4 | Data manipulation |
| numpy | 1.26.4 | Numerical computation |
| matplotlib | 3.8.2 | Visualisasi data |
| seaborn | 0.13.2 | Statistical visualization |
| streamlit | 1.32.0 | Dashboard interaktif |
| gdown | 5.1.0 | Download dataset dari GDrive |