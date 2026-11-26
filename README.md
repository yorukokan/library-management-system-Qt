<div align="center">

<!-- Header Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B1120,50:15803D,100:41CD52&height=210&section=header&text=Library%20Management%20System&fontSize=40&fontColor=F8FAFC&fontAlignY=38&desc=C%2B%2B17%20%E2%80%A2%20Qt%20Widgets%20%E2%80%A2%20SQLite%20Desktop%20Automation&descSize=16&descAlignY=62&animation=fadeIn" width="100%" alt="Library Management System Banner"/>

<!-- Typing Animation -->
<a href="https://github.com/yorukokan/library-management-system-Qt">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=18&duration=2600&pause=900&color=41CD52&center=true&vCenter=true&width=780&lines=Desktop+Library+Automation+with+C%2B%2B17+%2B+Qt+Widgets;SQLite+CRUD+for+Members%2C+Books%2C+Loans+%2B+Returns;15-Day+Grace+Period+%2B+Automated+Overdue+Fee+Engine;C%2B%2B17+ve+Qt+Widgets+ile+K%C3%BCt%C3%BCphane+Y%C3%B6netim+Otomasyonu" alt="Typing SVG"/>
</a>

<br/>

<!-- Quick Action Pills -->
<p>
  <img src="https://img.shields.io/badge/Qt_Widgets-C%2B%2B17_%C2%B7_SQLite-41CD52?style=for-the-badge&logo=qt&logoColor=white&labelColor=0B0F19" alt="Qt Widgets C++17 SQLite"/>
  <a href="https://github.com/yorukokan"><img src="https://img.shields.io/badge/GitHub-yorukokan-181717?style=for-the-badge&logo=github&logoColor=white&labelColor=0B0F19" alt="GitHub"/></a>
  <a href="https://linkedin.com/in/okanyoruk"><img src="https://img.shields.io/badge/LinkedIn-Okan_Y%C3%B6r%C3%BCk-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0B0F19" alt="LinkedIn"/></a>
  <a href="mailto:okanyoruk.tr@gmail.com"><img src="https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0B0F19" alt="Email"/></a>
</p>

</div>

---

## 🎯 Overview · Proje Özeti

<table>
<tr>
<td width="50%" valign="top">

<h3>🇬🇧 English</h3>

A desktop **Library Management System** built with **C++17**, **Qt Widgets**, and **SQLite** (`QSQLITE`). The application organizes daily library workflows into four dedicated dialog modules launched from a central `MainWindow`: **Member Management**, **Book Inventory**, **Book Borrowing**, and **Book Returns**.

Data is queried via parameterized `QSqlQuery` statements and rendered in real time through `QSqlQueryModel` and `QTableView`. Built-in integrity checks prevent deleting members with unreturned books or books currently on loan, while the return workflow automatically calculates overdue penalties beyond a **15-day** grace period.

> 🎬 **Demo Video:** Watch [Library-Management.mp4](Library-Management.mp4) directly in the repository.

</td>
<td width="50%" valign="top">

<h3>🇹🇷 Türkçe</h3>

**C++17**, **Qt Widgets** ve **SQLite** (`QSQLITE`) ile geliştirilmiş masaüstü **Kütüphane Yönetim Sistemi**. Uygulama, merkezi `MainWindow` penceresinden açılan dört ayrı pencere modülüyle günlük kütüphane süreçlerini yönetir: **Üye İşlemleri**, **Kitap İşlemleri**, **Ödünç Alma** ve **Ödünç Teslim Etme**.

Tüm veritabanı işlemleri parametreli `QSqlQuery` sorgularıyla yürütülür ve `QSqlQueryModel` aracılığıyla `QTableView` tablolarına anlık yansıtılır. Yerleşik bütünlük kontrolleri, teslim edilmemiş kitabı bulunan üyelerin veya ödünçte olan kitapların silinmesini engeller; teslim modülü ise **15 günü** aşan gecikmeler için otomatik borç hesaplar.

> 🎬 **Demo Videosu:** Uygulama akışını [Library-Management.mp4](Library-Management.mp4) dosyasından izleyebilirsiniz.

</td>
</tr>
</table>

---

## ✨ Key Features · Öne Çıkan Özellikler

<table>
<tr>
<td width="50%" valign="top">

<h4>👤 Member Management · Üye İşlemleri</h4>

<b>EN:</b> Full CRUD operations on the <code>üye</code> table with empty-field validation and click-to-populate row selection. Blocks member deletion if any active record exists in <code>odunc_alinan</code>.<br/>
<b>TR:</b> <code>üye</code> tablosu üzerinde boş alan kontrollü ekleme, güncelleme, silme ve tablo satırından form doldurma. Üyenin <code>odunc_alinan</code> tablosunda teslim edilmemiş kitabı varsa silme işlemini engeller.

<br/><code>islemleruye.h</code> · <code>islemleruye.cpp</code> · <code>islemleruye.ui</code>

</td>
<td width="50%" valign="top">

<h4>📚 Book Inventory &amp; History · Kitap İşlemleri</h4>

<b>EN:</b> Manages books and stock counts in the <code>kitap</code> table, prevents deleting books that are currently loaned out, and displays both active loans and historical return records for any selected book.<br/>
<b>TR:</b> <code>kitap</code> tablosunda kitap adı ve stok yönetimi yapar, ödünçte olan kitabın silinmesini engeller ve seçilen kitabın hem güncel ödünç hem de geçmiş teslim kayıtlarını iki ayrı tabloda listeler.

<br/><code>islemlerkitap.h</code> · <code>islemlerkitap.cpp</code> · <code>islemlerkitap.ui</code>

</td>
</tr>
<tr>
<td width="50%" valign="top">

<h4>📤 Book Borrowing · Ödünç Alma</h4>

<b>EN:</b> Pairs members and books across three synchronized tables, blocks duplicate active loans for the same <code>(uye_no, kitap_no)</code> pair, stores <code>odunc_alma_tarihi</code>, and decrements <code>kitap_sayisi</code> by 1.<br/>
<b>TR:</b> Üyeler, kitaplar ve ödünç listesini aynı ekranda sunar; aynı üyenin aynı kitabı tekrar ödünç almasını engeller, <code>QDateEdit</code> ile alma tarihini kaydeder ve <code>kitap_sayisi</code> stoğunu 1 azaltır.

<br/><code>islemleroduncalma.h</code> · <code>islemleroduncalma.cpp</code> · <code>islemleroduncalma.ui</code>

</td>
<td width="50%" valign="top">

<h4>📥 Returns &amp; Overdue Fees · Ödünç Teslim ve Borç</h4>

<b>EN:</b> Moves returned loans from <code>odunc_alinan</code> to <code>odunc_teslim_edilen</code> and computes overdue fees in <code>hesapla_borc(QDate)</code>: 15-day grace period, then <code>4 × (days - 15)</code> per late day.<br/>
<b>TR:</b> İade edilen kaydı <code>odunc_alinan</code> tablosundan silip <code>odunc_teslim_edilen</code> tablosuna aktarır; <code>hesapla_borc(QDate)</code> ile 15 günü aşan her gün için <code>4 × (gün - 15)</code> gecikme borcu hesaplar.

<br/><code>islemleroduncteslim.h</code> · <code>islemleroduncteslim.cpp</code> · <code>islemleroduncteslim.ui</code>

</td>
</tr>
<tr>
<td width="50%" valign="top">

<h4>🖥️ Central Hub &amp; DB Handshake · Ana Pencere</h4>

<b>EN:</b> Initializes the shared <code>QSQLITE</code> connection on startup, reports connection status in <code>QStatusBar</code>, and passes the active <code>QSqlDatabase</code> instance to each modal/modeless <code>QDialog</code>.<br/>
<b>TR:</b> Başlangıçta <code>QSQLITE</code> veritabanı bağlantısını kurar, durum çubuğunda bağlantı sonucunu gösterir ve ortak <code>QSqlDatabase</code> nesnesini tüm alt <code>QDialog</code> ekranlarına aktarır.

<br/><code>main.cpp</code> · <code>mainwindow.h</code> · <code>mainwindow.cpp</code> · <code>mainwindow.ui</code>

</td>
<td width="50%" valign="top">

<h4>🎨 Embedded Qt Resources · Gömülü Kaynaklar</h4>

<b>EN:</b> Packages all 9 background and module icon assets under the <code>:/images</code> virtual prefix via Qt Resource System, compiled directly into the binary with <code>qmake</code>.<br/>
<b>TR:</b> 9 adet arka plan ve modül simgesi <code>:/images</code> önekiyle Qt Resource System üzerinden derlenerek çalıştırılabilir dosya içine gömülür.

<br/><code>Resources.qrc</code> · <code>LibraryManagement.pro</code> · <code>images/</code>

</td>
</tr>
</table>

---

## 🏗️ Architecture · Mimari

```text
main.cpp
   │
   ▼
MainWindow (mainwindow.h/.cpp/.ui)
   │  QSqlDatabase::addDatabase("QSQLITE") ──▶ QStatusBar status
   │
   ├──▶ islemlerUye (QDialog)          ──▶ [ üye ]  (+ check: odunc_alinan)
   │       CRUD + unreturned-book guard
   │
   ├──▶ islemlerKitap (QDialog)        ──▶ [ kitap ] + [ odunc_alinan ] + [ odunc_teslim_edilen ]
   │       CRUD + on-loan guard + 2 history views
   │
   ├──▶ islemlerOduncAlma (QDialog)    ──▶ [ üye ] + [ kitap ] + [ odunc_alinan ]
   │       Duplicate-loan guard + stock decrement (kitap_sayisi - 1)
   │
   └──▶ islemlerOduncteslim (QDialog)  ──▶ [ odunc_alinan ] ──▶ [ odunc_teslim_edilen ]
           hesapla_borc(QDate): days > 15 ? 4 * (days - 15) : 0
```

### 🗄️ SQLite Schema · Veritabanı Şeması (`Library_database.db`)

| Table · Tablo | Columns · Sütunlar | Notes · Açıklama |
| :--- | :--- | :--- |
| `üye` | `uye_no` *(PK, AUTOINCREMENT)*, `uye_ad`, `uye_soyad` | Member records · Üye kayıtları |
| `kitap` | `kitap_no` *(PK, AUTOINCREMENT)*, `kitap_ad`, `kitap_sayisi` | Book catalog & stock · Kitap kataloğu ve stok |
| `odunc_alinan` | `uye_no` *(FK)*, `kitap_no` *(FK)*, `odunc_alma_tarihi` *(dd.MM.yyyy)* | Active loans · Aktif ödünç kayıtları |
| `odunc_teslim_edilen` | `uye_no` *(FK)*, `kitap_no` *(FK)*, `alma_tarihi`, `verme_tarihi`, `borc` | Returned loans & overdue fees · Teslim geçmişi ve borç |

---

## 🛠️ Tech Stack · Teknoloji Yığını

<div align="center">

![C++17](https://img.shields.io/badge/C%2B%2B17-00599C?style=for-the-badge&logo=cplusplus&logoColor=white&labelColor=0D1117)
![Qt Widgets](https://img.shields.io/badge/Qt_Widgets-41CD52?style=for-the-badge&logo=qt&logoColor=white&labelColor=0D1117)
![Qt SQL](https://img.shields.io/badge/Qt_SQL-2E8B57?style=for-the-badge&logo=qt&logoColor=white&labelColor=0D1117)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white&labelColor=0D1117)
![qmake](https://img.shields.io/badge/qmake-15803D?style=for-the-badge&logo=qt&logoColor=white&labelColor=0D1117)

</div>

---

## 📂 Project Structure · Proje Yapısı

```text
library-management-system-Qt/
├── LibraryManagement.pro         # qmake project config (core, gui, sql, widgets, C++17)
├── Library_database.db           # Pre-populated SQLite database (4 tables)
├── Library-Management.mp4        # Application demo video
├── Resources.qrc                 # Qt resource manifest (:/images prefix)
├── main.cpp                      # QApplication entry point
├── mainwindow.{h,cpp,ui}         # Central navigation hub & QSQLITE connection setup
├── islemleruye.{h,cpp,ui}        # Member CRUD dialog (islemlerUye)
├── islemlerkitap.{h,cpp,ui}      # Book inventory & loan history dialog (islemlerKitap)
├── islemleroduncalma.{h,cpp,ui}  # Book borrowing workflow dialog (islemlerOduncAlma)
├── islemleroduncteslim.{h,cpp,ui}# Book return & overdue fee dialog (islemlerOduncteslim)
└── images/                       # UI backgrounds & module icons (9 PNG/JPG assets)
```

---

## 🚀 Getting Started · Kurulum ve Çalıştırma

### 1. Prerequisites · Gereksinimler
- **Qt 5 or Qt 6** (`core`, `gui`, `widgets`, `sql` modules + `QSQLITE` driver)
- **C++17** compatible compiler (`g++`, `clang++`, or MSVC) and `qmake` (or **Qt Creator**)

### 2. Clone the Repository · Repoyu Klonla

```bash
git clone https://github.com/yorukokan/library-management-system-Qt.git
cd library-management-system-Qt
```

### 3. Configure the SQLite Database Path · Veritabanı Yolunu Ayarla

> [!IMPORTANT]
> The repository ships the pre-populated SQLite database as `Library_database.db`. Before building, update the `database.setDatabaseName(...)` call in `mainwindow.cpp` so it points directly to `Library_database.db` (and ensure `Library_database.db` is located in your active build/working directory):

```cpp
// mainwindow.cpp
database.setDatabaseName("Library_database.db");
```

### 4. Build & Run · Derleme ve Çalıştırma

**Option A — CLI (`qmake` + `make`)**

```bash
qmake LibraryManagement.pro
make
./LibraryManagement
```

**Option B — Qt Creator**
1. Open `LibraryManagement.pro` in **Qt Creator** and configure a Desktop Qt kit.
2. Update `database.setDatabaseName("Library_database.db")` in `mainwindow.cpp` and place `Library_database.db` in the active build/working directory.
3. Click **Build & Run** (`Ctrl+R`).

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B1120,50:15803D,100:41CD52&height=100&section=footer" width="100%" alt="Footer Wave"/>

<sub>⚡ <b>Okan Yörük</b> · C++17 · Qt Widgets · SQLite · <a href="https://github.com/yorukokan">github.com/yorukokan</a></sub>

</div>
