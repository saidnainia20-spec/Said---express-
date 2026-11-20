
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SAID EXPRESS - Livraison Settat</title>
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial,sans-serif;background:#f4f5f7;color:#222}
header{background:#151515;color:white;text-align:center;padding:25px 12px}
.logo{font-size:30px;font-weight:bold;color:#f4c400}
header p{margin:8px}
main{max-width:520px;margin:20px auto;padding:15px}
.card{background:white;padding:20px;border-radius:15px;margin-bottom:16px;box-shadow:0 3px 12px #0001}
h2{margin-top:0}
input,select,textarea{width:100%;padding:14px;margin:8px 0;border:1px solid #ddd;border-radius:9px;font-size:16px}
button{width:100%;padding:15px;background:#f4c400;border:0;border-radius:9px;font-weight:bold;font-size:17px;cursor:pointer}
.price{display:flex;justify-content:space-between;padding:12px;background:#fff8d9;border-radius:9px;margin:8px 0}
.green{background:#168b48;color:white}
footer{text-align:center;padding:20px;color:#777}
</style>
</head>
<body>

<header>
<div class="logo">SAID EXPRESS</div>
<h2>خدمة التوصيل بسطات</h2>
<p>طلبك يوصل حتى لباب دارك 🚴</p>
</header>

<main>
<div class="card">
<h2>📦 طلب خدمة التوصيل</h2>

<form id="orderForm">
<input id="name" placeholder="الاسم الكامل" required>
<input id="phone" placeholder="رقم الهاتف" required>
<input id="pickup" placeholder="مكان أخذ الطلب" required>
<input id="destination" placeholder="عنوان التوصيل" required>

<select id="area" onchange="updatePrice()">
<option value="15">داخل مدينة سطات - 15 درهم</option>
<option value="20">منطقة بعيدة - 20 درهم</option>
</select>

<select id="service">
<option>توصيل المشتريات</option>
<option>توصيل الأكل</option>
<option>توصيل الأدوية</option>
<option>توصيل الوثائق والطرود</option>
<option>خدمة أخرى</option>
</select>

<textarea id="details" placeholder="ملاحظات إضافية (اختياري)"></textarea>

<div class="price">
<span>ثمن التوصيل</span>
<strong id="price">15 DH</strong>
</div>

<button type="submit" class="green">إرسال الطلب عبر واتساب</button>
</form>
</div>

<div class="card">
<h2>💰 أسعار التوصيل</h2>
<div class="price"><span>داخل مدينة سطات</span><b>15 DH</b></div>
<div class="price"><span>المناطق البعيدة</span><b>20 DH</b></div>
</div>

<div class="card">
<h2>☎️ اتصل بنا</h2>
<p>للطلب والاستفسار:</p>
<button onclick="window.open('https://wa.me/212603681664')">
تواصل معنا عبر واتساب
</button>
</div>

</main>

<footer>
SAID EXPRESS © 2026
<br>خدمتكم مسؤوليتنا ❤️
</footer>

<script>
function updatePrice(){
document.getElementById('price').textContent =
document.getElementById('area').value + ' DH';
}

document.getElementById('orderForm').addEventListener('submit',function(e){
e.preventDefault();

const name=document.getElementById('name').value;
const phone=document.getElementById('phone').value;
const pickup=document.getElementById('pickup').value;
const destination=document.getElementById('destination').value;
const price=document.getElementById('area').value;
const service=document.getElementById('service').value;
const details=document.getElementById('details').value;

const message=
'🚴 SAID EXPRESS - طلب توصيل جديد%0A%0A'+
'الاسم: '+encodeURIComponent(name)+'%0A'+
'الهاتف: '+encodeURIComponent(phone)+'%0A'+
'مكان الأخذ: '+encodeURIComponent(pickup)+'%0A'+
'عنوان التوصيل: '+encodeURIComponent(destination)+'%0A'+
'الخدمة: '+encodeURIComponent(service)+'%0A'+
'الثمن: '+price+' DH%0A'+
'ملاحظات: '+encodeURIComponent(details);

window.open('https://wa.me/212603681664?text='+message,'_blank');
});
</script>

</body>
</html>
