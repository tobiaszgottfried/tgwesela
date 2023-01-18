Próbowałem skorzystać z funkcji do załadowania obrazów w typie lazy


<img data-src="img/ekipa/ekipa1.webp" loading="lazy" alt=".." class="lazyload"/>
i z skryptem js
<script>
  if ('loading' in HTMLImageElement.prototype) {
      const images = document.querySelectorAll("img.lazyload");
      images.forEach(img => {
          img.src = img.dataset.src;
      });
  } else {
      // Dynamically import the LazySizes library
    let script = document.createElement("script");
    script.async = true;
    script.src =
      "https://cdnjs.cloudflare.com/ajax/libs/lazysizes/4.1.8/lazysizes.min.js";
    document.body.appendChild(script);
  }
</script>

aczkolwiek nie dokońca rozumiem o co w tym chodziło.. a rezultat to był skrypty blokujące render strony na 20sekund... 

wydaje mi się że problemem jest tylko i wyłącznie za duży rozmiar plików są one 1920px/1280px a powinny być dużo mniejsze. 

Co o tym sądzisz?