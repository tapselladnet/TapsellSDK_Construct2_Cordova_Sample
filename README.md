<div dir="rtl">
<h1>مستندات راه‌اندازی تبلیغات تپسل در Construct2</h1>
&nbsp; (نسخه پلاگین: ۱.۰.۳ – نسخه اندروید: ۳.۰.۳۴ – نسخه iOS:
<span style="color: #ffffff;">ـ</span>۳.۰.۵ ) توجه پلاگین تپسل، در نسخه‌های
۳.۰.۰ و بالاتر cordova قابل استفاده است. اگر نسخه cordova شما خارج از این محدوده باشد، امکان استفاده از این پلاگین را نخواهید
داشت. نسخه کتابخانه اندروید مورد نیاز
]جهت استفاده از SDK تپسل می‌بایست از build tools نسخه 23 و بالاتر استفاده کنید.
فهرست مطالب
<ul>
	<li style="list-style-type: none;">
		<ul>
			<li>
				<a href="#rewarded">پیاده‌سازی تپسل در Construct 2</a>
			</li>
			<li>
				<a href="#build">ایجاد پروژه Cordova و دریافت خروجی اندروید/iOS</a>
			</li>
			<li>
				<a href="https://github.com/tapselladnet/TapsellConstruct2PluginSample">پروژه نمونه</a>
			</li>
		</ul>
	</li>
</ul>



<!-- <div id="android-init"></div> -->

<!-- <div id="ios-init"></div> -->

<div id="rewarded">
<h2>پیاده‌سازی تپسل در Construct 2</h2>
<h3>
	<strong>گام ۱: دریافت و نصب پلاگین تپسل برای Construct 2</strong>
</h3>
ابتدا فایل پلاگین تپسل برای Construct 2 را از آدرس زیر را دانلود کنید.
<p style="text-align: center;">
	<a href="https://storage.backtory.com/tapsell-server/sdk/TapsellConstruct2-1.1-a3.0.32-i3.0.5.c2addon">
		<button>دانلود پلاگین</button>
	</a>
</p>
نرم افزار Construct 2 را باز کرده و در پروژه خود، فایل پلاگین را داخل نرم‌افزار drag and drop کنید. با این روش پلاگین تپسل
در نرم‌افزار نصب می‌شود. &nbsp;
<h3>گام ۲: دریافت کلید تپسل</h3>
وارد
<a href="https://dashboard.tapsell.ir/">داشبورد تپسل</a> شده و با تعریف یک اپلیکیشن جدید با عنوان پکیج اپلیکیشن اندرویدی خود، یک کلید تپسل دریافت کنید. &nbsp;
<h3>
	<strong>گام ۳: شروع کار با پلاگین تپسل</strong>
</h3>
برای شروع کار با پلاگین تپسل باید یک شی از نوع
<code>TapsellSDKv3</code> در پروژه خود ایجاد کنید. برای این کار در قسمت Projects کلیک راست کرده و از طریق پنجره Insert New Object این شی را ایجاد
کنید.

<img class="size-full wp-image-1112" src="https://answers.tapsell.ir/wp-content/uploads/2017/03/1.png" alt="Construct2_Implementation_1"
 width="717" height="655" /> سپس با کلیک روی شی ایجاد شده در تب Porjects، مشخصات آن در تب Properties باز می شود. در بخش appkey، کلید تپسل که در مرحله
قبل دریافت نمودید را وارد نمایید. در پلاگین تپسل دو اکشن و پنج رویداد (Event) قابل استفاده هستند. این موارد در تصویر زیر
قابل مشاهده هستند.
<p style="text-align: center;">
	<img class="size-full wp-image-1118 aligncenter" src="https://answers.tapsell.ir/wp-content/uploads/2017/03/3.png" alt="Construct2_Implementation_3"
	 width="703" height="486" />
</p>
اکشن‌ها و رویدادهای فوق برای دریافت و نمایش تبلیغ استفاده می‌شوند. &nbsp;
<h3>
	<strong>گام ۴: دریافت تبلیغ</strong>
</h3>
نمایش یک تبلیغ ویدئویی در اپلیکیشن به دو صورت ممکن است صورت پذیرد. یک روش، نمایش تبلیغ بصورت stream می‌باشد. در این حالت،
همزمان که کاربر درحال مشاهده بخشی از تبلیغ است، ادامه آن از اینترنت لود می‌گردد. ممکن است به دلیل کندی سرعت اینترنت، در این
حالت کاربر با مکث‌های متعددی در هنگام دریافت و مشاهده تبلیغ مواجه شود. برای اینکه کاربر در هنگام نمایش تبلیغ منتظر نماند
و تجربه کاربر در استفاده از اپلیکیشن بهبود یابد،روش دیگری نیز در SDK تپسل تعبیه شده است که در آن ابتدا فایل ویدئوی تبلیغاتی
بطور کامل بارگذاری شده و سپس تبلیغ نمایش داده می‌شود. همچنین در تپسل، تبلیغ می تواند در ناحیه‌های مختلفی از برنامه شما (مانند
فروشگاه، انتهای هر مرحله، ابتدای مرحله جهت دریافت امتیاز دوبرابر، دریافت بنزین/لایف و ...) پخش شود. در تپسل به این ناحیه‌ها
zone گفته می شود. ناحیه‌های هر اپلیکیشن در پنل تپسل تعریف می شوند. جهت دریافت یک تبلیغ، باید از اکشن
<code>requestAd</code> استفاده کنید. ورودی اول (
<code>Caching options</code>) تعیین کننده کش شدن/نشدن تبلیغ است. ورودی دوم (
<code>ZoneId</code>) شناسه تبلیغگاه مورد نظر در اپلیکیشن شماست که در داشبور تپسل در صفحه اپلیکیشن شما قابل تعریف است.

<img class="wp-image-1113 aligncenter" src="https://answers.tapsell.ir/wp-content/uploads/2017/03/2.png" alt="Construct2_Implementation_1"
 width="481" height="264" /> &nbsp; کش کردن ویدئو تنها در ناحیه‌هایی که کاربر
با احتمال زیادی پس از باز کردن اپلیکیشن تبلیغ آن را مشاهده می‌کند، از تبلیغ Cached استفاده کنید. جهت توضیحات بیشتر درباره
روش انتخاب متد دریافت مناسب،
<a href="https://answers.tapsell.ir/?ht_kb=cached-vs-streamed">اینجا</a> را مطالعه کنید. توضیحات ورودی
<code>Caching options</code> در جدول ۱ آمده است. &nbsp;
<table style="text-align: center; border-collapse: collapse;" width="100%" cellpadding="6">
	<caption>جدول ۱ مقادیر مختلف پارامتر Caching options در درخواست تبلیغ</caption>
	<tbody>
		<tr style="border-bottom: 1px solid #ddd;">
			<th width="40%">مقدار</th>
			<th width="60%">توضیحات</th>
		</tr>
		<tr style="background-color: #fefefe;">
			<td width="40%">Cached</td>
			<td width="60%">دریافت ویدئو و نمایش آن پس از دانلود کامل</td>
		</tr>
		<tr style="background-color: #f2f2f2;">
			<td width="40%">Streamed</td>
			<td width="60%">نمایش ویدئو بصورت برخط (stream)</td>
		</tr>
	</tbody>
</table>
&nbsp;
<h3>
	<strong>گام ۵: دریافت نتیجه درخواست تبلیغ</strong>
</h3>
پس از ارسال درخواست تبلیغ، نتیجه آن به رویدادهای تپسل برگردانده می‌شود. لذا شما باید برای تبلیغگاه مورد استفاده رویدادهای
دریافت نتیجه درخواست را در
<code>EventSheet</code> پروژه خود اضافه کنید. توضیحات این رویدادها در جدول ۲ آمده است. &nbsp;
<table style="text-align: center; border-collapse: collapse;" width="100%" cellpadding="6">
	<caption>جدول ۲ رویدادهای دریافت نتیجه درخواست تبلیغ</caption>
	<tbody>
		<tr style="border-bottom: 1px solid #ddd;">
			<th width="40%">تابع</th>
			<th width="60%">توضیحات (زمان اجرا)</th>
		</tr>
		<tr style="background-color: #fefefe;">
			<td dir="ltr" width="40%">onError</td>
			<td width="60%">هنگامی که هر نوع خطایی در پروسه‌ی دریافت تبلیغ برای تبلیغگاه مورد نظر بوجود بیاید</td>
		</tr>
		<tr style="background-color: #f2f2f2;">
			<td dir="ltr" width="40%">onAdAvailable</td>
			<td width="60%">زمانی که تبلیغ برای تبلیغگاه مورد نظر دریافت شده و آماده‌ی نمایش باشد.</td>
		</tr>
		<tr style="background-color: #fefefe;">
			<td dir="ltr" width="40%">onNoAdAvailable</td>
			<td width="60%">در صورتی که تبلیغی برای نمایش در تبلیغگاه مورد نظر وجود نداشته باشد.</td>
		</tr>
		<tr style="background-color: #f2f2f2;">
			<td dir="ltr" width="40%">onNoNetwork</td>
			<td width="60%">زمانی که دسترسی به شبکه موجود نباشد.</td>
		</tr>
		<tr style="background-color: #fefefe;">
			<td dir="ltr" width="40%">onExpiring</td>
			<td width="60%">زمانی که تبلیغ منقضی شود. هر تبلیغ مدت زمان مشخصی معتبر است و در صورتی که تا قبل از آن نمایش داده نشود منقضی شده و دیگر
				قابل نمایش نخواهد بود.</td>
		</tr>
		<tr style="background-color: #f2f2f2;">
			<td dir="ltr" width="40%">onOpened</td>
			<td width="60%">زمانی که تبلیغ شروع به پخش شود</td>
		</tr>
		<tr style="background-color: #fefefe;">
			<td dir="ltr" width="40%">onClosed</td>
			<td width="60%">زمانی که تبلیغ پایان یافته و کاربر در لحظه بازگشت به اپلیکیشن است</td>
		</tr>
	</tbody>
</table>
&nbsp; در تصویر زیر، پیاده‌سازی این توابع در پروژه نمونه، نمایش داده‌شده‌است.
<p style="text-align: center;">
	<img class="wp-image-1119 aligncenter" src="https://answers.tapsell.ir/wp-content/uploads/2017/03/4.png" alt="Construct2_Implementation_4"
	 width="672" height="381" />
</p>
&nbsp;
<h3>گام ۶: نمایش تبلیغ</h3>
پس از دریافت یک تبلیغ، بوسیله اکشن
<code>showAd</code> می‌توانید تبلیغ را برای تبلیغگاه مورد نظر نمایش دهید. در این مرحله نیز باید شناسه تبلیغگاه مورد نظر (
<code>ZoneId</code>) را به عنوان ورودی اکشن بدهید. توضیحات ورودی‌های اکشن
<code>showAd</code> در جدول ۳ در ادامه آمده است. &nbsp;
<p style="text-align: center;">
	<img class=" wp-image-1120 aligncenter" src="https://answers.tapsell.ir/wp-content/uploads/2017/03/5.png" alt="Construct2_Implementation_5"
	 width="483" height="363" />
</p>
&nbsp;
<table style="text-align: center; border-collapse: collapse;" width="100%" cellpadding="6">
	<caption>جدول ۳ ورودی‌های اکشن showAd</caption>
	<tbody>
		<tr style="border-bottom: 1px solid #ddd;">
			<th width="40%">تابع</th>
			<th width="60%">توضیحات</th>
		</tr>
		<tr style="background-color: #fefefe;">
			<td dir="ltr" width="40%">Back Button</td>
			<td width="60%">
				<div align="right">فعال‌بودن/نبودن دکمه‌ی بازگشت گوشی در هنگام پخش تبلیغ</div>
			</td>
		</tr>
		<tr style="background-color: #f2f2f2;">
			<td dir="ltr" width="40%">Immersive Mode</td>
			<td width="60%">
				<div align="right">فعال‌بودن/نبودن حالت Immersive در هنگام پخش تبلیغ</div>
			</td>
		</tr>
		<tr style="background-color: #fefefe;">
			<td dir="ltr" width="40%">Rotation Mode</td>
			<td width="60%">
				<div align="right">تعیین وضعیت گوشی در هنگام پخش تبلیغ به یکی از حالات:</div>
				<div align="left">ROTATION_LOCKED_PORTRAIT ROTATION_LOCKED_LANDSCAPE ROTATION_UNLOCKED ROTATION_LOCKED_REVERSED_PORTRAIT ROTATION_LOCKED_REVERSED_LANDSCAPE
				</div>
			</td>
		</tr>
		<tr style="background-color: #f2f2f2;">
			<td dir="ltr" width="40%">Warning Dialog</td>
			<td width="60%">
				<div align="right">نمایش دیالوگ اخطار در هنگام بازگشت از تبلیغات جایزه‌دار</div>
			</td>
		</tr>
	</tbody>
</table>
&nbsp;
<h3>
	<strong>گام ۷: دریافت نتیجه نمایش تبلیغ</strong>
</h3>
جهت دریافت نتیجه نمایش تبلیغات، باید از رویدادهای
<code>onAdShowFinished</code> و
<code>onAdShowCanceled</code> استفاده نمایید و در آن‌ها شناسه تبلیغ‌گاه را به عنوان ورودی بدهید. در صورتیکه رویداد
<code>onAdShowFinished</code> اجرا شد، می‌توانید جایزه درون برنامه کاربر (سکه/اعتبار/بنزین/...) را به کاربر بدهید.

<img class="size-full wp-image-1121 aligncenter" src="https://answers.tapsell.ir/wp-content/uploads/2017/03/6.png" alt="Construct2_Implementation_6"
 width="973" height="187" /> &nbsp;
<h3>نمونه پیاده‌سازی</h3>
یک نمونه پیاده‌سازی پلاگین تپسل در پروژه Construct 2 در repository زیر آمده است.
<p style="text-align: center;">
	<a href="https://github.com/tapselladnet/TapsellConstruct2PluginSample">
		<button>مشاهده پروژه نمونه</button>
	</a>
</p>
</div>

<!-- <div id="native-banner"></div> -->

<!-- <div id="native-video"></div> -->

<!-- <div id="standard-banner"></div> -->

<!-- <div id="advanced-options"></div> -->

<div id="build">
<h2>ایجاد پروژه Cordova و دریافت خروجی اندروید</h2>
<h3>گام
	<strong>۱</strong>: گرفتن خروجی Cordova از پروژه Construct 2</h3>
برای استفاده از تپسل در پروژه Construct 2 لازم است از Cordova برای خروجی گرفتن استفاده کنید روش Build توسط سایت ها (به این
دلیل که باید پلاگین تپسل به پروژه Cordova اضافه شود) معمولا جوابگو نیست. همچنین با این روش حجم فایل خروجی به نسبت خروجی سایت
هایی مثل Cocoon به طرز محسوسی کمتر می باشد. در نرم افزار Construct 2، از تب Home گزینه Export Project را انتخاب کنید. در
پنجره باز شده از قسمت Mobile، گزینه Cordova را انتخاب کنید و روی گزینه Next کلیک کنید. در پنجره‌ای که باز می‌شود، در قسمت
Export files to پوشه www از پروژه Cordova خود را انتخاب کنید و روی گزینه Next کلیک کنید. در پنجره نهایی پس از وارد کردن تنظیمات
مورد نظرتان، روی دکمه Export کلیک نمایید. پروژه Cordova شما آماده اجرا است.
<h3></h3>
<h3>
	<strong>گام </strong>۲
	<strong>: اضافه کردن پلاگین تپسل به پروژه Cordova</strong>
</h3>
برای گرفتن خروجی اندروید، باید از Cordova استفاده کنید:

<a href="https://cordova.apache.org/docs/en/latest/guide/cli/">آموزش راه اندازی Cordova</a>

جهت اضافه کردن SDK تپسل به پروژه Cordova، باید با command prompt به محل قرارگیری پروژه Cordova رفته و دستور زیر را اجرا کنید.
<pre dir="ltr"> cordova plugin add tapsell-construct2</pre> &nbsp; با این دستور میتوانید خروجی اندروید از پروژه Cordova بگیرید:
<pre dir="ltr">cordova build android</pre> &nbsp; اگر اجرای دستور بالا به مشکل خورد با دستور زیر یک پروژه Cordova جدید ایجاد کنید:
<pre dir="ltr">cordova create myAppName</pre> &nbsp; و پلتفرم اندروید را به آن اضافه کنید:
<pre dir="ltr">cordova platform add android</pre> &nbsp; پلاگین تپسل را اضافه کنید:
<pre dir="ltr"> cordova plugin add tapsell-construct2</pre> &nbsp; فولدر www را از خروجی که قبلا گرفته بودید در محل پروژه جدید کپی کنید و دوباره خروجی بگیرید. &nbsp; &nbsp; لطفا نظرات
</div>

</div>
