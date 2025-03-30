# performans

•	Gerçekçi Kullanıcı Davranışı Simülasyonu:
Request’ler arasına Constant Timer ekleyerek, gerçek kullanıcı davranışını taklit edecek şekilde gecikmeler simüle edilmiştir. Bu sayede test senaryoları, sistemin yük altında gerçek kullanım senaryolarına daha yakın bir şekilde değerlendirilmesini sağlamaktadır.
•	Anlamlı Sonuç Analizi için Listener Yapısı:
Tüm listener’lar tek bir Thread Group altında konumlandırılmıştır. Ancak her bir senaryo, listener’larda anlaşılır olması adına kendi adlarıyla ayrıştırılmıştır. Böylece analiz sırasında senaryo bazlı performans değerlendirmesi yapılabilmektedir.
•	Senaryolar Arası Tekrar Eden Request’ler:
Her senaryoda hemen hemen aynı request’lere istek atılıyor. Bu tekrarın sebebi, her birinin kullanıcı deneyimini farklı şekilde etkiliyor olmasıdır. Örneğin, Test 4'te kullanıcı siteye girip arama alanına "telefon" yazıyor, ardından çıkan ürünü tıklayarak ürün detay sayfasına yönlendiriliyor. Bu işlem, belirli bir yükten sonra diğer kullanıcıların arama çubuğundaki sonuçları görmesini, ürün listesini görüntülemesini veya ürün detay sayfasına ulaşmasını olumsuz etkileyebilir. Bu nedenle, bu senaryolar üzerinden sistemin farklı adımlardaki performansını gözlemlemek önemlidir.
________________________________________
Test Senaryoları Açıklamaları
•	Test 1 – Ana Sayfa Açılış Performans Testi:
Kullanıcıların ana sayfayı yüklerken karşılaştığı performans ölçülmüştür. Sayfanın erişilebilirlik ve yanıt süresi analiz edilmiştir.
•	Test 2 – Searchbar Dropdown Doğrulama:
Arama çubuğuna veri girildiğinde yük altındayken açılan dropdown menüde doğru ürünlerin listelenip listelenmediği kontrol edilmiştir.
•	Test 3 – Ürün Listeleme Kontrolü:
Arama işlemi yapıldıktan sonra listelenen ürünlerin ilk öğesinin doğru şekilde geldiği ve yük altında performans kaybı yaşanıp yaşanmadığı test edilmiştir.
•	Test 4 – Ürün Detay Sayfası Yönlendirme:
Arama sonucu gelen ilk ürün tıklanarak ürün detay sayfasına yönlendirilir. Yük altındayken kullanıcıların bu adımlarda ürün detayına ulaşıp ulaşamadığı kontrol edilmiştir. Bu test, sistemin daha derin işlemler sırasında kaynak kullanımı üzerindeki etkisini gözlemlemek için önemlidir.
