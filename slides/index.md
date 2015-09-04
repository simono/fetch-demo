# Fetch Me If You Can
## The new JavaScript Fetch API

Simon Olofsson &bull; [@solofs](https://twitter.com/solofs)

---

#  Different
## ways to fetch a resource

* HTML: `img`
* CSS: `background-image`
* JS: `XMLHttpRequest`

---

# Inconsistent
## handling of redirects, CORS etc.

---

<!-- .slide: data-background="http://i.giphy.com/QMlde8HVzLTAk.gif" data-background-size="500px" -->

---

# Fetch standard
## unifies this

---

# Plus

---

# `fetch()`
## JavaScript API

---

# No more
## `XMLHttpRequest`

---

<!-- .slide: data-background="http://i.giphy.com/KPSzkxvcDNHI4.gif" data-background-size="500px" -->

---

# XMLHttpRequest
```
var req = new XMLHttpRequest();
req.open('GET', 'http://httpbin.org/get');
req.responseType = 'json';

req.onload = function() {
  console.log(req.response);
};

req.onerror = function() {
  console.log('Error :-(');
};

req.send();
```

---

# jQuery
```
jQuery.getJSON('http://httpbin.org/get', function(data) {
  console.log(data);
}).fail(function() {
  console.log('Error :-(');
});
```

---

<!-- .slide: data-background="http://41.media.tumblr.com/b265c797666e5c9c1999b74f8fdba9db/tumblr_mizvlhM2kT1s4tpo3o1_500.jpg" data-background-size="500px" -->

---

<!-- .slide: data-background="http://cdn0.meme.li/instances/300x300/39256697.jpg" data-background-size="500px" -->

---

# Fetch API
```
fetch('http://httpbin.org/get')
.then(function(res) {
  return res.json();
}).then(function(data) {
  console.log(data);
}).catch(function() {
  console.log('Error :-(');
});
```
Most modern Browsers or [Polyfill](https://github.com/github/fetch)

---

<!-- .slide: data-background="http://i.giphy.com/wGFCMW7AiqCbK.gif" data-background-size="500px" -->

---

# ES6 Arrow functions
```
fetch('http://httpbin.org/get')
.then(res => res.json())
.then(data => console.log(data))
.catch(e => console.log('Error :-('));
```
Current Desktop Browsers

---

# ES7 Async functions
```
(async() => {
  try {
    var res = await fetch('http://httpbin.org/get');
    var data = await res.json();
    console.log(data);
  } catch (e) {
    console.log('Error :-('));
  }
})();
```
Only Transpilers (Traceur, Babel etc.)

---

<!-- .slide: data-background="http://i.giphy.com/gOmS1l5BNTFZu.gif" data-background-size="500px" -->

---

# Thanks for listening
## Questions?

---

<!-- .slide: data-background="http://i.giphy.com/NTjVvG5rktX3y.gif" data-background-size="500px" -->
