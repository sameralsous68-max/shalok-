<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <title>متجر شالوك للملابس</title>
  <style>
    body { font-family: Tahoma, Arial; margin:0; background:#f4f4f4; }

    .hero {
      background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://i.imgur.com/2x8b7yG.png') center/cover no-repeat;
      color:#fff;
      text-align:center;
      padding:80px 20px;
    }
    .hero h1 { font-size:42px; margin-bottom:10px; }
    .hero p { font-size:18px; opacity:0.9; }

    .container { width:90%; margin:auto; padding:40px 0; }

    .categories {
      display:grid;
      grid-template-columns:repeat(auto-fill,minmax(250px,1fr));
      gap:25px;
      margin-bottom:40px;
    }

    .category-box {
      position:relative;
      height:200px;
      border-radius:16px;
      overflow:hidden;
      cursor:pointer;
      box-shadow:0 6px 15px rgba(0,0,0,0.15);
      transition: transform 0.3s ease;
    }

    .category-box:hover {
      transform: scale(1.05);
    }

    .category-box img {
      width:100%;
      height:100%;
      object-fit:cover;
    }

    .category-box::after {
      content:"";
      position:absolute;
      inset:0;
      background:linear-gradient(to top, rgba(0,0,0,0.7), rgba(0,0,0,0.1));
    }

    .category-title {
      position:absolute;
      bottom:15px;
      right:15px;
      color:#fff;
      font-size:22px;
      font-weight:bold;
      z-index:2;
    }

    .category-content { display:none; margin-bottom:40px; opacity:0; transition: opacity 0.5s ease; }
    .category-content.show { display:block; opacity:1; }

    .products { display:grid; grid-template-columns:repeat(auto-fill,minmax(220px,1fr)); gap:25px; }

    .product { background:#fff; border-radius:15px; padding:15px; text-align:center; box-shadow:0 6px 15px rgba(0,0,0,0.12); }
    .product img { width:100%; border-radius:12px; }
    .product h3 { margin:12px 0 5px; }
    .product p { margin:5px 0 15px; font-weight:bold; }

    .buy { background:#25D366; color:#fff; border:none; padding:14px; border-radius:10px; cursor:pointer; width:100%; font-size:16px; }
    .group-btn { background:#075E54; color:#fff; border:none; padding:14px; border-radius:10px; cursor:pointer; width:100%; font-size:16px; margin-top:10px; }

    footer { background:#111; color:#fff; text-align:center; padding:20px; margin-top:40px; }
  </style>
</head>
<body>

<section class="hero">
  <h1>Shalok Hijabs</h1>
  <p>أناقة عصرية • حجز سريع عبر واتساب</p>
</section>

<div class="container">

  <div class="categories">
    <div class="category-box" onclick="openCategory('hijabs')">
      <img src="https://i.imgur.com/Ny3FZ7b.jpg" alt="حجابات">
      <div class="category-title">حجابات</div>
    </div>

    <div class="category-box" onclick="openCategory('women')">
      <img src="https://i.imgur.com/0KzXy9E.jpg" alt="ملابس نسائية">
      <div class="category-title">ملابس نسائية</div>
    </div>
  </div>

  <div id="hijabs" class="category-content">
    <h2>حجابات</h2>
    <div class="products">
      <div class="product">
        <img src="https://i.imgur.com/FjWwD9p.jpg" alt="حجاب شالوك">
        <h3>حجاب شالوك ناعم</h3>
        <p>السعر: 15$</p>
        <button class="buy" onclick="buyNow('حجاب شالوك ناعم','15$')">اشتري الآن</button>
      </div>
    </div>
    <button class="group-btn" onclick="joinGroup()">انضم لمجموعة واتساب</button>
  </div>

  <div id="women" class="category-content">
    <h2>ملابس نسائية</h2>
    <div class="products">
      <div class="product">
        <img src="https://i.imgur.com/wJ9k7Sk.jpg" alt="فستان شالوك">
        <h3>فستان شالوك أنيق</h3>
        <p>السعر: 40$</p>
        <button class="buy" onclick="buyNow('فستان شالوك أنيق','40$')">اشتري الآن</button>
      </div>
    </div>
    <button class="group-btn" onclick="joinGroup()">انضم لمجموعة واتساب</button>
  </div>

</div>

<footer>
  جميع الحقوق محفوظة © شالوك
</footer>

<script>
  function buyNow(product, price) {
    const message = `مرحبا، أرغب بشراء المنتج التالي:%0Aالمنتج: ${product}%0Aالسعر: ${price}`;
    const phoneNumber = "0996909146";
    const whatsappLink = `https://wa.me/${phoneNumber}?text=${message}`;
    window.open(whatsappLink, '_blank');
  }

  function joinGroup() {
    const whatsappGroup = "https://chat.whatsapp.com/Hz16xghpT0kKfJ3fE8elDN";
    window.open(whatsappGroup, '_blank');
  }

  function openCategory(id) {
    document.querySelectorAll('.category-content').forEach(c => c.classList.remove('show'));
    const cat = document.getElementById(id);
    cat.classList.add('show');
    cat.scrollIntoView({ behavior: 'smooth', block: 'start' });
  }
</script>

</body>
</html>
