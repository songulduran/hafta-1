# Bilgisayar Mimarisi

Bilgisayarın bir programı çalıştırırken kullandığı temel donanım bileşenleri arasında **CPU, RAM ve Cache** bulunur. Bu bileşenlerin nasıl çalıştığını anlamak, yazdığımız kodun bilgisayar tarafından nasıl işlendiğini anlamamızı sağlar.

---

## 1. CPU (Central Processing Unit)

CPU, bilgisayarın **işlemcisi** olarak görev yapar. Programlardan gelen komutları işler ve gerekli işlemleri gerçekleştirir.

CPU'nun temel bölümleri:

### ALU (Arithmetic Logic Unit)

ALU, matematiksel ve mantıksal işlemleri gerçekleştirir.

Örneğin:

```text
5 + 3
10 > 5
x == 10
```

gibi işlemler ALU tarafından gerçekleştirilir.

### Kontrol Birimi (Control Unit)

Kontrol birimi, CPU içerisindeki işlemlerin **hangi sırayla ve nasıl gerçekleştirileceğini** yönetir.

Programdaki komutları alır, gerekli birimlere iletir ve işlemlerin koordinasyonunu sağlar.

---

## 2. Cache Bellek

Cache, CPU'nun sık kullandığı verilere daha hızlı ulaşabilmesi için kullanılan **çok hızlı bir bellek türüdür**.

Cache'in temel amacı CPU ile RAM arasındaki hız farkını azaltmaktır.

### Cache Katmanları

Cache genellikle üç seviyede incelenir:

### L1 Cache

- CPU'ya en yakın cache seviyesidir.
- En hızlı cache türüdür.
- Kapasitesi diğer seviyelere göre daha küçüktür.

### L2 Cache

- L1'e göre daha büyük fakat biraz daha yavaştır.
- CPU'nun sık ihtiyaç duyduğu verileri tutar.

### L3 Cache

- L1 ve L2'den daha büyük kapasiteye sahiptir.
- Bunlara göre daha yavaştır.
- Genellikle işlemci çekirdekleri arasında paylaşılabilir.

Genel olarak hız sıralaması:

```text
L1 → L2 → L3 → RAM → Disk
```

CPU bir veriyi cache içerisinde bulursa RAM'e gitmesine gerek kalmaz. Bu nedenle cache, programların performansı açısından önemlidir.

---

## 3. RAM (Random Access Memory)

RAM, bilgisayarın programları çalıştırırken ihtiyaç duyduğu verileri **geçici olarak tuttuğu ana bellektir**.

Örneğin bir program açıldığında programın çalışması için gerekli veriler RAM'e yüklenir.

RAM'in özellikleri:

- CPU'ya göre daha yavaştır.
- Cache belleğe göre daha büyük kapasiteye sahiptir.
- Geçici bellektir.
- Bilgisayar kapatıldığında RAM'deki veriler kaybolur.

Basit bir örnek:

```text
Program → RAM'e yüklenir
       ↓
CPU → Gerekli verileri RAM'den ister
       ↓
Cache → Sık kullanılan verileri daha hızlı erişim için tutabilir
       ↓
CPU → İşlemi gerçekleştirir
```

---

## 4. CPU, Cache ve RAM Arasındaki İlişki

Bir program çalışırken CPU'nun ihtiyaç duyduğu veriler farklı bellek seviyelerinden alınabilir.

Basitleştirilmiş yapı:

```text
CPU
 ↓
L1 Cache
 ↓
L2 Cache
 ↓
L3 Cache
 ↓
RAM
 ↓
Depolama (SSD/HDD)
```

CPU önce daha hızlı olan cache seviyelerinde veriyi arar. Veri bulunamazsa daha alt seviyelere ve sonunda RAM'e ulaşılır.

Bu yapı sayesinde CPU'nun sürekli olarak yavaş belleklere erişmesi engellenir.

---

## 5. Kod Donanım Seviyesinde Nasıl İşlenir?

Örneğin:

```javascript
let sonuc = 5 + 3;
```

gibi basit bir kod yazdığımızda işlem doğrudan JavaScript kodunun CPU tarafından okunması şeklinde gerçekleşmez.

Genel olarak:

```text
Kaynak Kod
    ↓
Programlama Dili / Çalıştırma Ortamı
    ↓
Makine Talimatları
    ↓
CPU
    ↓
ALU ve diğer CPU birimleri
    ↓
Sonuç
```

CPU, kendisine verilen düşük seviyeli talimatları işler. Gerekli veriler cache veya RAM'den alınır ve işlemci içerisinde işlenir.

---

## 6. Neden Bilgisayar Mimarisi Öğrenilmeli?

Bilgisayar mimarisini öğrenmek, yazılım geliştirirken bilgisayarın kodu arka planda nasıl işlediğini anlamaya yardımcı olur.

Özellikle:

- Performans problemlerini anlamayı,
- Bellek kullanımını kavramayı,
- CPU ve RAM arasındaki ilişkiyi anlamayı,
- Cache'in neden önemli olduğunu kavramayı,
- Kodun donanım üzerinde nasıl çalıştığını anlamayı

sağlar.

> **Özet:** CPU işlemleri gerçekleştirir, RAM çalışan programların verilerini geçici olarak tutar, Cache ise CPU'nun sık ihtiyaç duyduğu verilere daha hızlı ulaşmasını sağlar.
