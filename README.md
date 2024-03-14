# Ask For A Date

## Proje Hakkında

Ask For A Date, kullanıcıya basit bir etkileşimli deneyim sunan bir JavaScript uygulamasıdır. Bu uygulama, Çıkma teklifi etmek için bir senaryo sunar ve kullanıcının yanlış bir tuşa basması durumunda eğlenceli bir tepki verir.

## Nasıl Çalışır?

Kullanıcı ekranda "Evet" ve "Hayır" butonlarına sahip bir kutu görür. Kullanıcı "Tab" tuşuna bastığında, "Hayır" butonu bir patlama animasyonu ile kaybolur, başlık metni değişir ve "Evet" butonu kalır. Ardından, başlık metni tekrar orijinal haline döner.

## Nasıl Kullanılır?

Proje dosyalarını bilgisayarınıza klonlayın veya indirin. Daha sonra, HTML dosyasını bir tarayıcıda açarak uygulamayı görüntüleyebilirsiniz.

## Örnek Kod Parçası

```javascript
document.addEventListener('keydown', function (event) {
    if (event.key === 'Tab') {
        const noButton = document.querySelector('.btnNo'); // noButton değişkenini tanımla
        if (!noButton.dataset.tabPressed) { // Eğer tab daha önce basılmadıysa devam et
            noButton.dataset.tabPressed = true; // tab basıldı olarak işaretle
            noButton.style.animation = 'explode 0.5s forwards'; // Patlama animasyonunu etkinleştir
            setTimeout(() => noButton.style.display = 'none', 500); // Butonu 0.5 saniye sonra gizle
            event.preventDefault(); // Tab tuşunun varsayılan davranışını engelle

            // "title" içindeki span öğelerini gizle
            const titleSpans = document.querySelectorAll('.title span');
            titleSpans.forEach(span => {
                span.style.opacity = '0';
            });

            // "title" içindeki "h1" öğesini göster
            const titleH1 = document.querySelector('.title h1');
            titleH1.style.opacity = '1';

            // "title" içindeki "h1" öğesinin metnini değiştir
            titleH1.textContent = 'Hile yapmak yok :)';

            // Orijinal başlığa geri dön
            setTimeout(() => {
                titleH1.textContent = 'Çıkalım mı artık?';
            }, 2000);
        }
    }
});
```

 ## Katkıda Bulunma

Katkıda bulunmak isterseniz, bir çekme isteği göndermek veya bir sorun bildirmek için GitHub sayfamızı ziyaret edebilirsiniz.

## Lisans

Bu proje MIT Lisansı altında lisanslanmıştır. Daha fazla bilgi için [LICENSE](LICENSE) dosyasına bakın. İyi çalışmalar dilerim ^^ 

[![Instagram](https://img.shields.io/badge/Instagram-%23E4405F.svg?&style=flat-square&logo=instagram&logoColor=white)](https://www.instagram.com/kodlama.dili/)
