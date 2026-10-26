# Kinetik Deyimler Sözlüğü

Türkçe deyimlerin mecaz anlamını harflerin hareketiyle anlatan, web tabanlı ve açık erişimli bir kinetik tipografi sözlüğü denemesi.

**Canlı sürüm:** https://zehraworks.github.io/kinetik-deyimler-sozlugu/

## Ön çalışma: ilk beş madde

| Deyim | Mecaz türü | Fırça | Hareket |
|---|---|---|---|
| ağzı kulaklarına varmak | Beden | eğri | Satır bir gülümseme eğrisine oturur, kelimeler kulaklara doğru açılır. |
| yerin dibine girmek | Yön (aşağı) | batma | Harfler sırayla zeminin altına batar; en son "dibine" kaybolur. |
| aklı başından gitmek | Dağılma ve düzen | dağılma | "aklı" sözcüğü parçalara ayrılıp savrulur, sonra yerine toplanır. |
| içi içine sığmamak | Kap (iç/dış) | taşma | Sözcükler çerçevenin içinde büyür, duvarlara sıkışır, sonunda taşar. |
| göz açıp kapayıncaya kadar | Hız ve zaman | kırpma | "ö" harfinin noktaları göz gibi kırpılır; kırpma anında deyimin geri kalanı belirir. |

## Motor nasıl çalışıyor?

Deyimler tek tek kodlanmıyor. Motorun birkaç hareket türü ("fırça") var. Her deyim, bu fırçalardan birini hangi ayarlarla kullanacağını söyleyen kısa bir veri tarifinden ibaret:

```js
{
  firca: 'batma',
  vurgu: 1,
  ayarlar: { yon: 1, mesafe: 1.45, kademe: 0.18, hedef: null, sonKalan: 1, egim: 0, zemin: true, hizEgrisi: 'hizlanan' },
  zamanlama: { giris: 2600, bekleme: 900, cikis: 1300, dinlenme: 600 },
  durgun: 0.45
}
```

Sayfanın sonundaki "burnu havada" maddesi için yeni kod yazılmadı. Batma fırçasının yönü yukarı, hedefi de tek bir sözcük yapıldı.

Türkçe harfler: "göz açıp kapayıncaya kadar" maddesinde "ö" harfinin noktaları harf gövdesinden ayrı çiziliyor ve ayrı hareket ediyor.

Animasyonlar p5.js ile tarayıcıda çiziliyor. İşletim sisteminde hareket azaltma ayarı açıksa animasyonlar kendiliğinden oynamaz, yalnızca "Baştan oynat" düğmesiyle oynar.

## Yerelde çalıştırma

Derleme adımı yok. `index.html` dosyasını tarayıcıda açman yeterli.
