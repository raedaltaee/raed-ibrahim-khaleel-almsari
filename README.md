<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>حقيبة تدريبية عن 5G و 6G</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f4f8;
            color: #333;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        .header {
            background-color: #1a202c;
            color: #ffffff;
            padding: 1.5rem;
            border-radius: 0.75rem;
            margin-bottom: 2rem;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .header .logos {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 1rem;
        }
        .header .logos img {
            width: 80px;
            height: 80px;
            object-fit: contain;
            background-color: #ffffff;
            padding: 0.5rem;
            border-radius: 0.5rem;
        }
        @media (min-width: 768px) {
            .header .logos img {
                width: 100px;
                height: 100px;
            }
        }
        .lecture-card {
            background-color: #ffffff;
            border-radius: 0.75rem;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease-in-out;
        }
        .lecture-card:hover {
            transform: translateY(-5px);
        }
        .lecture-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            padding-bottom: 1rem;
            margin-bottom: 1rem;
            border-bottom: 1px solid #e2e8f0;
        }
        .lecture-header h2 {
            font-size: 1.5rem;
            font-weight: 600;
            color: #2c5282;
        }
        .lecture-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-out;
        }
        .lecture-content.open {
            max-height: 2500px;
        }
        .interactive-section {
            background-color: #e6fffa;
            border-left: 5px solid #38b2ac;
            border-radius: 0.5rem;
            padding: 1rem;
            margin-top: 1rem;
            color: #2c7a7b;
        }
        .btn-toggle {
            background-color: #4299e1;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 0.5rem;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        .btn-toggle:hover {
            background-color: #3182ce;
        }
        ul {
            list-style-type: disc;
            margin-right: 1.5rem;
            padding-right: 0;
        }
        li {
            margin-bottom: 0.5rem;
        }
        .activity-task-section {
            background-color: #f7fafc;
            border-left: 3px solid #63b3ed;
            border-radius: 0.5rem;
            padding: 1rem;
            margin-top: 1rem;
            margin-bottom: 1rem;
        }
        .activity-task-section h4 {
            font-weight: 600;
            color: #2b6cb0;
            margin-bottom: 0.5rem;
        }
        .survey-form label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        .survey-form input[type="radio"],
        .survey-form textarea {
            margin-left: 0.5rem;
            margin-bottom: 1rem;
        }
        .survey-form textarea {
            width: 100%;
            padding: 0.5rem;
            border: 1px solid #cbd5e0;
            border-radius: 0.25rem;
            resize: vertical;
        }
        .survey-form button {
            background-color: #48bb78;
            color: white;
            border: none;
            padding: 0.75rem 1.5rem;
            border-radius: 0.5rem;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        .survey-form button:hover {
            background-color: #38a169;
        }
        .author-info, .course-info-section, .lecture-details-section, .logistics-section, .recommendations-section, .technologies-section, .rubric-section, .conclusion-section, .external-links-section, .acknowledgement-section, .quranic-verse-section {
            background-color: #e0f2f7;
            border-radius: 0.75rem;
            padding: 1.5rem;
            margin-bottom: 2rem;
            text-align: center;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
            color: #2c5282;
        }
        .author-info h3, .course-info-section h3, .lecture-details-section h3, .logistics-section h3, .recommendations-section h3, .technologies-section h3, .rubric-section h3, .conclusion-section h3, .external-links-section h3, .acknowledgement-section h3, .quranic-verse-section h3 {
            font-size: 1.75rem;
            font-weight: 700;
            margin-bottom: 0.75rem;
        }
        .author-info p, .course-info-section p, .lecture-details-section p, .logistics-section p, .recommendations-section p, .technologies-section p, .rubric-section p, .conclusion-section p, .external-links-section p, .acknowledgement-section p, .quranic-verse-section p {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
        }
        .author-info a, .course-info-section a, .lecture-details-section a, .logistics-section a, .recommendations-section a, .technologies-section a, .rubric-section a, .conclusion-section a, .external-links-section a, .acknowledgement-section a, .quranic-verse-section a {
            color: #3182ce;
            text-decoration: none;
            font-weight: 600;
        }
        .author-info a:hover, .course-info-section a:hover, .lecture-details-section a:hover, .logistics-section a:hover, .recommendations-section a:hover, .technologies-section a:hover, .rubric-section a:hover, .conclusion-section a:hover, .external-links-section a:hover, .acknowledgement-section a:hover, .quranic-verse-section a:hover {
            text-decoration: underline;
        }
        .course-info-section ul, .lecture-details-section ul, .logistics-section ul, .recommendations-section ul, .technologies-section ul, .rubric-section ul, .conclusion-section ul, .external-links-section ul, .acknowledgement-section ul, .quranic-verse-section ul {
            list-style-type: none;
            padding: 0;
            margin: 0 auto;
            max-width: 800px;
            text-align: right;
        }
        .course-info-section ul li, .lecture-details-section ul li, .logistics-section ul li, .recommendations-section ul li, .technologies-section ul li, .rubric-section ul li, .conclusion-section ul li, .external-links-section ul li, .acknowledgement-section ul li, .quranic-verse-section ul li {
            background-color: #f0f9ff;
            padding: 0.75rem 1rem;
            border-radius: 0.5rem;
            margin-bottom: 0.5rem;
            border-right: 3px solid #63b3ed;
            text-align: right;
            font-size: 1rem;
        }
        .lecture-details-section {
            background-color: #f0f9ff;
            border-right: 4px solid #4299e1;
            margin-top: 1rem;
            margin-bottom: 1.5rem;
            padding: 1rem 1.5rem;
            text-align: right;
            color: #2c5282;
        }
        .lecture-details-section h4 {
            font-size: 1.25rem;
            font-weight: 600;
            margin-bottom: 0.75rem;
            color: #2b6cb0;
        }
        .lecture-details-section ul {
            list-style-type: disc;
            margin-right: 1.5rem;
            padding-right: 0;
            text-align: right;
        }
        .lecture-details-section ul li {
            background-color: transparent;
            border: none;
            padding: 0.25rem 0;
            margin-bottom: 0.25rem;
            font-size: 0.95rem;
            color: #4a5568;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1rem;
            margin-bottom: 1.5rem;
            background-color: #ffffff;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
            border-radius: 0.5rem;
            overflow: hidden;
        }
        th, td {
            border: 1px solid #e2e8f0;
            padding: 0.75rem 1rem;
            text-align: right;
        }
        th {
            background-color: #ebf8ff;
            font-weight: 600;
            color: #2c5282;
        }
        tr:nth-child(even) {
            background-color: #f7fafc;
        }
        tr:hover {
            background-color: #e2f3ff;
        }
        .rubric-table th, .rubric-table td {
            text-align: right;
            padding: 12px;
            border: 1px solid #ddd;
        }
        .rubric-table thead tr {
            background-color: #f2f2f2;
        }
        .rubric-table tbody tr:nth-child(odd) {
            background-color: #fafafa;
        }
        .quranic-verse-section {
            background-color: #d1fae5; /* Light green */
            color: #065f46; /* Darker green text */
            border-right: 5px solid #10b981; /* Green border */
            padding: 2rem;
            margin-bottom: 2rem;
            border-radius: 0.75rem;
            font-size: 1.2rem;
            font-weight: 600;
            line-height: 1.8;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        .quranic-verse-section p {
            margin-bottom: 1rem;
            font-style: italic;
        }
        .quranic-verse-section .reference {
            font-size: 0.9rem;
            font-weight: 400;
            color: #047857;
        }
    </style>
</head>
<body class="font-inter">
    <div class="container">
        <header class="header">
            <div class="logos">
                <img src="https://placehold.co/80x80/ffffff/000000?text=شعار+الجامعة+المستنصرية" alt="شعار الجامعة المستنصرية" onerror="this.onerror=null;this.src='https://placehold.co/80x80/ffffff/000000?text=شعار+جامعة'">
                <img src="https://placehold.co/80x80/ffffff/000000?text=شعار+التعليم+المستمر" alt="شعار قسم التعليم المستمر" onerror="this.onerror=null;this.src='https://placehold.co/80x80/ffffff/000000?text=شعار+تعليم'">
                <img src="https://placehold.co/80x80/ffffff/000000?text=شعار+وزارة+التعليم" alt="شعار وزارة التعليم العالي والبحث العلمي" onerror="this.onerror=null;this.src='https://placehold.co/80x80/ffffff/000000?text=شعار+وزارة'">
            </div>
            <h1 class="text-3xl font-bold">حقيبة تدريبية تفاعلية شاملة عن تقنيات الاتصالات المستخدمة في الجيل الخامس والسادس</h1>
            <p class="mt-2 text-lg">استكشاف أحدث التطورات في عالم الاتصالات اللاسلكية</p>
        </header>

        <section class="author-info">
            <h3>إعداد وتقديم:</h3>
            <p class="text-xl font-bold">رائد إبراهيم خليل إبراهيم</p>
            <p>ماجستير هندسة اتصالات</p>
            <p>الجامعة المستنصرية</p>
            <p>ديوان الوقف الشيعي</p>
            <p>البريد الإلكتروني: <a href="mailto:raedalmsari79@gmail.com">raedalmsari79@gmail.com</a></p>
        </section>

        <main>
            <section class="quranic-verse-section">
                <p>بسم الله الرحمن الرحيم</p>
                <p>"يَرْفَعِ اللَّهُ الَّذِينَ آمَنُوا مِنكُمْ وَالَّذِينَ أُوتُوا الْعِلْمَ دَرَجَاتٍ ۚ وَاللَّهُ بِمَا تَعْمَلُونَ خَبِيرٌ"</p>
                <p class="reference">صدق الله العظيم (سورة المجادلة، الآية 11)</p>
            </section>

            <section class="course-info-section">
                <h3>الفئة المستهدفة</h3>
                <p>هذه الحقيبة التدريبية موجهة بشكل أساسي إلى:</p>
                <ul class="list-disc pr-6 text-right mx-auto">
                    <li>المهندسون والفنيون العاملون في قطاع الاتصالات وتقنية المعلومات.</li>
                    <li>الباحثون والأكاديميون المهتمون بأحدث التطورات في الشبكات اللاسلكية.</li>
                    <li><li>طلاب الهندسة والعلوم الحاسوبية المتخصصون في مجال الاتصالات.</li>
                    <li>المتخصصون في تطوير الأعمال وصناع القرار الذين يرغبون في فهم تأثيرات 5G و 6G المستقبلية.</li>
                    <li>أي شخص لديه اهتمام عام بتقنيات الاتصالات اللاسلكية المتقدمة ويرغب في اكتساب معرفة معمقة.</li>
                </ul>
            </section>

            <section class="course-info-section">
                <h3>الأهداف العامة للحقيبة التدريبية</h3>
                <p>بنهاية هذه الحقيبة التدريبية، سيكون المتدرب قادرًا على:</p>
                <ul class="list-disc pr-6 text-right mx-auto">
                    <li>فهم المفاهيم الأساسية والركائز التقنية للجيل الخامس (5G).</li>
                    <li>التعرف على التقنيات المتقدمة المستخدمة في شبكات 5G مثل Massive MIMO و mmWave وتقسيم الشبكة.</li>
                    <li>استكشاف الرؤية المستقبلية والمتطلبات الرئيسية للجيل السادس (6G).</li>
                    <li>التعرف على التقنيات الناشئة في 6G مثل اتصالات التيراهرتز والأسطح الذكية القابلة لإعادة التكوين والاتصالات الكمومية.</li>
                    <li>تحليل التطبيقات وحالات الاستخدام المتوقعة لـ 5G و 6G في مختلف القطاعات.</li>
                    <li>فهم التحديات الرئيسية المتعلقة بنشر وتطبيق هذه التقنيات، بما في ذلك الأمن والخصوصية.</li>
                    <li>اكتساب القدرة على تقييم الاتجاهات المستقبلية والابتكارات في مجال الاتصالات اللاسلكية.</li>
                </ul>
            </section>

            <section class="course-info-section">
                <h3>محتويات الحقيبة التدريبية (نظرة عامة)</h3>
                <p>تتكون هذه الحقيبة التدريبية من ست محاضرات شاملة، تغطي كل منها جوانب محددة من تقنيات 5G و 6G، بالإضافة إلى أنشطة تفاعلية ومهام عملية واختبار نهائي لتعزيز الفهم:</p>
                <ul class="list-disc pr-6 text-right mx-auto">
                    <li>**المحاضرة الأولى:** مقدمة في 5G وأساسياتها.</li>
                    <li>**المحاضرة الثانية:** التقنيات الأساسية في 5G (الجزء الأول: الهوائيات المتقدمة وموجات المليمتر).</li>
                    <li>**المحاضرة الثالثة:** التقنيات الأساسية في 5G (الجزء الثاني: تقسيم الشبكة، الحوسبة الطرفية، SDN/NFV) وتطبيقات 5G.</li>
                    <li>**المحاضرة الرابعة:** مقدمة في 6G وتقنياتها الناشئة (الجزء الأول: رؤية 6G، اتصالات التيراهرتز، الذكاء الاصطناعي/التعلم الآلي).</li>
                    <li>**المحاضرة الخامسة:** التقنيات الناشئة في 6G (الجزء الثاني: RIS، الاتصالات الكمومية، ISAC، البلوك تشين) وتطبيقات 6G.</li>
                    <li>**المحاضرة السادسة:** التحديات والآفاق المستقبلية لـ 5G و 6G (النشر، الأمن، التوحيد القياسي، خارطة الطريق).</li>
                    <li>**الاختبار النهائي:** لتقييم الفهم الشامل للمحتوى.</li>
                    <li>**استبيانات التقييم:** لجمع الملاحظات حول المحاضر، الحقيبة، والإعدادات اللوجستية.</li>
                </ul>
            </section>

            <section class="course-info-section">
                <h3>مسار الجلسات للحقيبة التدريبية</h3>
                <p>توضح الجداول التالية توزيع المحاضرات والأنشطة على مدار الجلسات التدريبية المقترحة:</p>
                <table>
                    <thead>
                        <tr>
                            <th>الجلسة</th>
                            <th>المحاضرة</th>
                            <th>الموضوع الرئيسي</th>
                            <th>المدة المقترحة</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>الجلسة 1</td>
                            <td>المحاضرة الأولى</td>
                            <td>مقدمة في 5G وأساسياتها</td>
                            <td>3 ساعات</td>
                        </tr>
                        <tr>
                            <td>الجلسة 2</td>
                            <td>المحاضرة الثانية</td>
                            <td>التقنيات الأساسية في 5G (الجزء الأول)</td>
                            <td>3 ساعات</td>
                        </tr>
                        <tr>
                            <td>الجلسة 3</td>
                            <td>المحاضرة الثالثة</td>
                            <td>التقنيات الأساسية في 5G (الجزء الثاني) وتطبيقاتها</td>
                            <td>3 ساعات</td>
                        </tr>
                        <tr>
                            <td>الجلسة 4</td>
                            <td>المحاضرة الرابعة</td>
                            <td>مقدمة في 6G وتقنياتها الناشئة (الجزء الأول)</td>
                            <td>3 ساعات</td>
                        </tr>
                        <tr>
                            <td>الجلسة 5</td>
                            <td>المحاضرة الخامسة</td>
                            <td>التقنيات الناشئة في 6G (الجزء الثاني) وتطبيقاتها</td>
                            <td>3 ساعات</td>
                        </tr>
                        <tr>
                            <td>الجلسة 6</td>
                            <td>المحاضرة السادسة</td>
                            <td>التحديات والآفاق المستقبلية لـ 5G و 6G</td>
                            <td>3 ساعات</td>
                        </tr>
                        <tr>
                            <td>الجلسة 7</td>
                            <td>الاختبار النهائي والاستبيانات</td>
                            <td>تقييم شامل وملاحظات</td>
                            <td>ساعة ونصف</td>
                        </tr>
                    </tbody>
                </table>
            </section>

            <section class="technologies-section">
                <h3>التقنيات المستخدمة في إعداد الحقيبة التدريبية</h3>
                <p>تم تصميم هذه الحقيبة التدريبية التفاعلية باستخدام أحدث التقنيات لضمان تجربة تعليمية سلسة وفعالة، بالإضافة إلى أدوات مساعدة لتقديم المحتوى وتقييم المتدربين:</p>
                <ul class="list-disc pr-6 text-right mx-auto">
                    <li>**HTML5:** لهيكلة المحتوى وتنظيم الأقسام.</li>
                    <li>**CSS3 (مع Tailwind CSS):** للتصميم الجذاب والمتجاوب الذي يناسب مختلف أحجام الشاشات والأجهزة.</li>
                    <li>**JavaScript:** لإضافة التفاعلية، مثل طي وفتح أقسام المحاضرات، وعرض الرسائل التوضيحية للأنشطة.</li>
                    <li>**Google Fonts (Inter):** لضمان وضوح وجمالية الخطوط المستخدمة.</li>
                    <li>**منصة العرض التفاعلية (Canvas/Immersive Document):** التي تتيح عرض الكود التفاعلي مباشرة.</li>
                    <li>**نماذج جوجل (Google Forms):** لإنشاء الاختبارات القصيرة والاستبيانات لتقييم المحاضر والحقيبة والإعدادات اللوجستية.</li>
                    <li>**جوجل كلاس روم (Google Classroom):** لإدارة الدورة التدريبية، توزيع المهام، جمع الواجبات، وتوفير ساحة نقاش للمتدربين.</li>
                    <li>**مايكروسوفت باوربوينت (Microsoft PowerPoint):** لإعداد الشرائح التقديمية التفصيلية لكل محاضرة.</li>
                </ul>
            </section>

            <div class="lecture-card">
                <div class="lecture-header" onclick="toggleLecture('lecture1')">
                    <h2>المحاضرة الأولى: مقدمة في 5G وأساسياتها</h2>
                    <button class="btn-toggle" id="toggle1">+</button>
                </div>
                <div class="lecture-content" id="lecture1-content">
                    <div class="lecture-details-section">
                        <h4>الأهداف السلوكية للمحاضرة:</h4>
                        <ul class="list-disc pr-6">
                            <li>أن يعرف المتدرب مفهوم الجيل الخامس (5G) وأهدافه الرئيسية.</li>
                            <li>أن يميز المتدرب بين الركائز الثلاث لـ 5G (eMBB, URLLC, mMTC).</li>
                            <li>أن يشرح المتدرب التطور التاريخي للشبكات الخلوية من 1G إلى 5G.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>محتويات المحاضرة:</h4>
                        <p class="font-semibold text-gray-700">1. مفهوم الجيل الخامس (5G):</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>تعريف 5G: الجيل الخامس لشبكات الاتصالات المتنقلة، يهدف إلى توفير سرعات أعلى، زمن انتقال أقل، وقدرة أكبر بكثير من الأجيال السابقة.</li>
                            <li>الأهداف الرئيسية لـ 5G: دعم تطبيقات جديدة مثل إنترنت الأشياء الضخم، المركبات ذاتية القيادة، والواقع الافتراضي/المعزز.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">2. الركائز الثلاث لـ 5G:</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>**النطاق العريض المحسن المتنقل (eMBB):** يوفر سرعات بيانات فائقة (حتى 10 جيجابت/ثانية) لتطبيقات مثل الفيديو عالي الدقة والواقع الافتراضي.</li>
                            <li>**الاتصالات فائقة الموثوقية بزمن انتقال منخفض (URLLC):** يضمن زمن انتقال منخفض للغاية (أقل من 1 مللي ثانية) وموثوقية عالية (99.999%) لتطبيقات التحكم الصناعي والقيادة الذاتية.</li>
                            <li>**الاتصالات الضخمة من نوع الآلة (mMTC):** يدعم عددًا هائلاً من الأجهزة المتصلة (مليون جهاز لكل كيلومتر مربع) مع استهلاك طاقة منخفض، مثالي لإنترنت الأشياء.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">3. تطور الشبكات الخلوية من 1G إلى 5G:</p>
                        <ul class="list-disc pr-6">
                            <li>**1G (الثمانينات):** صوت تناظري، مكالمات هاتفية أساسية.</li>
                            <li>**2G (التسعينات):** صوت رقمي، رسائل نصية قصيرة (SMS).</li>
                            <li>**3G (أوائل الألفينات):** بيانات متنقلة، تصفح الويب الأساسي، مكالمات الفيديو.</li>
                            <li>**4G/LTE (2010s):** نطاق عريض متنقل عالي السرعة، بث الفيديو، تطبيقات الهواتف الذكية.</li>
                            <li>**5G (أواخر 2010s - الآن):** قفزة نوعية في السرعة والقدرة وزمن الانتقال، تمكين تطبيقات جديدة.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>مسار الجلسة للمحاضرة الأولى:</h4>
                        <table>
                            <thead>
                                <tr>
                                    <th>العنصر</th>
                                    <th>الوصف</th>
                                    <th>المدة المقترحة</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>مقدمة المحاضرة</td>
                                    <td>ترحيب، أهداف المحاضرة، لمحة سريعة.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>مفهوم 5G وأهدافه</td>
                                    <td>شرح تعريف 5G وأهدافه الرئيسية.</td>
                                    <td>30 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>الركائز الثلاث لـ 5G</td>
                                    <td>شرح eMBB, URLLC, mMTC مع أمثلة.</td>
                                    <td>45 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 1.1: مناقشة جماعية</td>
                                    <td>مناقشة تأثير الأجيال السابقة وتوقع تأثير 5G.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 1.2: عرض فيديو</td>
                                    <td>مشاهدة فيديو "ما هو 5G؟" ومشاركة الملاحظات.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>تطور الشبكات الخلوية</td>
                                    <td>مراجعة تاريخية من 1G إلى 5G.</td>
                                    <td>30 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 1.1: بحث قصير</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 1.2: رسم بياني</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>أسئلة وأجوبة وملخص</td>
                                    <td>فتح باب الأسئلة وتلخيص المحاضرة.</td>
                                    <td>10 دقيقة</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>

                    <div class="activity-task-section">
                        <h4>النشاط 1.1: مناقشة جماعية</h4>
                        <p>ناقش مع زملائك كيف أثرت الأجيال السابقة (1G إلى 4G) على حياتنا اليومية، وتوقع تأثير 5G بناءً على الركائز الثلاث.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>النشاط 1.2: عرض فيديو</h4>
                        <p>شاهد فيديو توضيحي قصير عن "ما هو 5G؟" ومشاركة أبرز النقاط التي لفتت انتباهك.</p>
                    </div>
                    <button class="mt-2 btn-toggle" onclick="openVideo('https://www.youtube.com/watch?v=s_L-m6_tJqY')">تشغيل الفيديو (ما هو 5G؟)</button>
                    <div class="activity-task-section">
                        <h4>المهمة 1.1: بحث قصير</h4>
                        <p>ابحث عن مثالين واقعيين لكل ركيزة من ركائز 5G (eMBB, URLLC, mMTC) وكيف يمكن تطبيقها.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>المهمة 1.2: رسم بياني</h4>
                        <p>ارسم خطًا زمنيًا يوضح تطور الأجيال الخلوية الرئيسية (1G إلى 5G) مع ذكر أبرز مميزات كل جيل.</p>
                    </div>
                </div>
            </div>

            <div class="lecture-card">
                <div class="lecture-header" onclick="toggleLecture('lecture2')">
                    <h2>المحاضرة الثانية: التقنيات الأساسية في 5G (الجزء الأول)</h2>
                    <button class="btn-toggle" id="toggle2">+</button>
                </div>
                <div class="lecture-content" id="lecture2-content">
                    <div class="lecture-details-section">
                        <h4>الأهداف السلوكية للمحاضرة:</h4>
                        <ul class="list-disc pr-6">
                            <li>أن يشرح المتدرب مفهوم Massive MIMO وفوائده وتحدياته.</li>
                            <li>أن يصف المتدرب آلية عمل تشكيل الحزمة (Beamforming) وأهميته في 5G.</li>
                            <li>أن يحدد المتدرب خصائص موجات المليمتر (mmWave) وتحدياتها وتطبيقاتها.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>محتويات المحاضرة:</h4>
                        <p class="font-semibold text-gray-700">1. تقنيات الهوائيات المتقدمة:</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>**MIMO الضخم (Massive MIMO):**
                                <ul class="list-disc pr-6">
                                    <li>المفهوم: استخدام عدد كبير جداً من الهوائيات (عشرات إلى مئات) في المحطة الأساسية.</li>
                                    <li>الفوائد: زيادة سعة الشبكة، تحسين كفاءة الطيف، تحسين جودة الإشارة للمستخدمين المتعددين.</li>
                                    <li>التحديات: التعقيد الحسابي، الحاجة إلى معالجة إشارات قوية.</li>
                                </ul>
                            </li>
                            <li>**تشكيل الحزمة (Beamforming):**
                                <ul class="list-disc pr-6">
                                    <li>كيفية عمله: توجيه إشارة الراديو بدقة نحو المستخدم بدلاً من بثها في جميع الاتجاهات.</li>
                                    <li>أهميته: تقليل التداخل، زيادة كفاءة الطاقة، تحسين التغطية والسرعة.</li>
                                </ul>
                            </li>
                        </ul>
                        <p class="font-semibold text-gray-700">2. موجات المليمتر (mmWave):</p>
                        <ul class="list-disc pr-6">
                            <li>خصائص موجات المليمتر: استخدام ترددات عالية جداً (24 جيجاهرتز إلى 100 جيجاهرتز)، مما يوفر نطاقًا تردديًا هائلاً.</li>
                            <li>تحدياتها: مدى قصير، حساسية عالية للعوائق (مثل الجدران والأمطار)، تتطلب خلايا صغيرة وكثيفة.</li>
                            <li>تطبيقاتها في 5G: توفير سرعات فائقة في المناطق المزدحمة (مثل الملاعب ومراكز التسوق).</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>مسار الجلسة للمحاضرة الثانية:</h4>
                        <table>
                            <thead>
                                <tr>
                                    <th>العنصر</th>
                                    <th>الوصف</th>
                                    <th>المدة المقترحة</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>مقدمة المحاضرة</td>
                                    <td>ترحيب، أهداف المحاضرة، مراجعة سريعة للمحاضرة السابقة.</td>
                                    <td>10 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>تقنيات الهوائيات المتقدمة</td>
                                    <td>شرح Massive MIMO و Beamforming.</td>
                                    <td>60 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 2.1: محاكاة تفاعلية</td>
                                    <td>استكشاف محاكاة Beamforming.</td>
                                    <td>25 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>موجات المليمتر (mmWave)</td>
                                    <td>شرح خصائصها وتحدياتها وتطبيقاتها.</td>
                                    <td>45 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 2.2: تحليل فيديو</td>
                                    <td>مشاهدة فيديو تحديات موجات المليمتر.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 2.1: مقارنة</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 2.2: اقتراح حلول</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>أسئلة وأجوبة وملخص</td>
                                    <td>فتح باب الأسئلة وتلخيص المحاضرة.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>

                    <div class="activity-task-section">
                        <h4>النشاط 2.1: محاكاة تفاعلية</h4>
                        <p>استكشف محاكاة بسيطة لآلية عمل تشكيل الحزمة (Beamforming) وكيفية توجيه الإشارة.</p>
                    </div>
                    <button class="mt-2 btn-toggle" onclick="openVideo('https://www.youtube.com/watch?v=F_fJzK9a72k')">تشغيل المحاكاة (Beamforming)</button>
                    <div class="activity-task-section">
                        <h4>النشاط 2.2: تحليل فيديو</h4>
                        <p>شاهد فيديو يوضح تحديات موجات المليمتر في البيئات الحضرية وكيف يتم التغلب عليها.</p>
                    </div>
                    <button class="mt-2 btn-toggle" onclick="openVideo('https://www.youtube.com/watch?v=T_l420h5m_4')">تشغيل الفيديو (تحديات mmWave)</button>
                    <div class="activity-task-section">
                        <h4>المهمة 2.1: مقارنة</h4>
                        <p>قارن بين Massive MIMO و MIMO التقليدي من حيث الأداء والتعقيد والتطبيقات.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>المهمة 2.2: اقتراح حلول</h4>
                        <p>اقترح حلولاً مبتكرة للتغلب على تحديات انتشار موجات المليمتر في المباني الكثيفة.</p>
                    </div>
                </div>
            </div>

            <div class="lecture-card">
                <div class="lecture-header" onclick="toggleLecture('lecture3')">
                    <h2>المحاضرة الثالثة: التقنيات الأساسية في 5G (الجزء الثاني) وتطبيقاتها</h2>
                    <button class="btn-toggle" id="toggle3">+</button>
                </div>
                <div class="lecture-content" id="lecture3-content">
                    <div class="lecture-details-section">
                        <h4>الأهداف السلوكية للمحاضرة:</h4>
                        <ul class="list-disc pr-6">
                            <li>أن يشرح المتدرب مفهوم تقسيم الشبكة (Network Slicing) وفوائده.</li>
                            <li>أن يحدد المتدرب أهمية الحوسبة الطرفية (Edge Computing) في 5G وتطبيقاتها.</li>
                            <li>أن يوضح المتدرب دور الشبكات المعرفة بالبرمجيات (SDN) ومحاكاة وظائف الشبكة (NFV).</li>
                            <li>أن يذكر المتدرب أمثلة على تطبيقات 5G الحالية والمستقبلية.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>محتويات المحاضرة:</h4>
                        <p class="font-semibold text-gray-700">1. تقسيم الشبكة (Network Slicing):</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>المفهوم: إنشاء شبكات افتراضية متعددة ومنفصلة منطقياً على نفس البنية التحتية المادية.</li>
                            <li>الفوائد: تخصيص الموارد لكل خدمة (مثل شريحة لـ URLLC وشريحة لـ eMBB)، مرونة عالية، دعم خدمات متنوعة.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">2. الحوسبة الطرفية (Edge Computing):</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>المفهوم: معالجة البيانات بالقرب من مصدرها (الطرف) بدلاً من إرسالها إلى السحابة المركزية.</li>
                            <li>أهميته لتقليل زمن الانتقال: يقلل المسافة التي يجب أن تقطعها البيانات، مما يقلل زمن الاستجابة بشكل كبير.</li>
                            <li>تطبيقاتها في 5G: القيادة الذاتية، الواقع المعزز، الروبوتات الصناعية.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">3. الشبكات المعرفة بالبرمجيات (SDN) ومحاكاة وظائف الشبكة (NFV):</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>**SDN:** فصل مستوى التحكم عن مستوى البيانات في الشبكة، مما يتيح إدارة الشبكة برمجياً.</li>
                            <li>**NFV:** تحويل وظائف الشبكة التقليدية (مثل جدران الحماية والموجهات) إلى برامج تعمل على خوادم قياسية.</li>
                            <li>دورهما في مرونة وإدارة شبكات 5G: تمكين التكوين الديناميكي للشبكة، النشر السريع للخدمات، وتقليل التكاليف التشغيلية.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">4. تطبيقات 5G الحالية والمستقبلية:</p>
                        <ul class="list-disc pr-6">
                            <li>**المدن الذكية:** إدارة حركة المرور، إضاءة الشوارع الذكية، مراقبة البيئة.</li>
                            <li>**المركبات المتصلة والقيادة الذاتية:** الاتصال بين المركبات والبنية التحتية، تحديثات الخرائط في الوقت الفعلي.</li>
                            <li>**الرعاية الصحية الرقمية:** الجراحة عن بعد، المراقبة الصحية للمرضى عن بعد، سيارات الإسعاف المتصلة.</li>
                            <li>**الصناعة 4.0:** أتمتة المصانع، الروبوتات المتصلة، الصيانة التنبؤية.</li>
                            <li>**الواقع الافتراضي والمعزز (VR/AR) والترفيه:** تجارب غامرة عالية الجودة، الألعاب السحابية.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>مسار الجلسة للمحاضرة الثالثة:</h4>
                        <table>
                            <thead>
                                <tr>
                                    <th>العنصر</th>
                                    <th>الوصف</th>
                                    <th>المدة المقترحة</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>مقدمة المحاضرة</td>
                                    <td>ترحيب، أهداف المحاضرة، مراجعة سريعة للمحاضرة السابقة.</td>
                                    <td>10 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>تقسيم الشبكة (Network Slicing)</td>
                                    <td>شرح المفهوم والفوائد.</td>
                                    <td>40 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>الحوسبة الطرفية (Edge Computing)</td>
                                    <td>شرح المفهوم وأهميته وتطبيقاته.</td>
                                    <td>40 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 3.1: دراسة حالة تطبيقية</td>
                                    <td>تحليل دراسة حالة Network Slicing.</td>
                                    <td>25 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>الشبكات المعرفة بالبرمجيات (SDN) ومحاكاة وظائف الشبكة (NFV)</td>
                                    <td>شرح دورهما في مرونة وإدارة الشبكة.</td>
                                    <td>30 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 3.2: عصف ذهني</td>
                                    <td>التفكير في تطبيقات 5G جديدة.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 3.1: تصميم سيناريو</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 3.2: تقرير موجز</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>أسئلة وأجوبة وملخص</td>
                                    <td>فتح باب الأسئلة وتلخيص المحاضرة.</td>
                                    <td>10 دقيقة</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>

                    <div class="activity-task-section">
                        <h4>النشاط 3.1: دراسة حالة تطبيقية</h4>
                        <p>حلل دراسة حالة حول كيفية استخدام Network Slicing لدعم تطبيقات مختلفة في ملعب رياضي ذكي.</p>
                    </div>
                    <button class="mt-2 btn-toggle" onclick="openVideo('https://www.youtube.com/watch?v=kYJzXwA9c_I')">عرض دراسة الحالة (Network Slicing)</button>
                    <div class="activity-task-section">
                        <h4>النشاط 3.2: عصف ذهني</h4>
                        <p>فكر في تطبيقات جديدة لـ 5G في مجال الرعاية الصحية أو التعليم لم يتم ذكرها.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>المهمة 3.1: تصميم سيناريو</h4>
                        <p>صمم سيناريو لاستخدام الحوسبة الطرفية (Edge Computing) في تطبيق للمركبات ذاتية القيادة لتقليل زمن الانتقال.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>المهمة 3.2: تقرير موجز</h4>
                        <p>اكتب تقريرًا موجزًا عن دور SDN و NFV في تبسيط إدارة شبكات 5G.</p>
                    </div>
                </div>
            </div>

            <div class="lecture-card">
                <div class="lecture-header" onclick="toggleLecture('lecture4')">
                    <h2>المحاضرة الرابعة: مقدمة في 6G وتقنياتها الناشئة (الجزء الأول)</h2>
                    <button class="btn-toggle" id="toggle4">+</button>
                </div>
                <div class="lecture-content" id="lecture4-content">
                    <div class="lecture-details-section">
                        <h4>الأهداف السلوكية للمحاضرة:</h4>
                        <ul class="list-disc pr-6">
                            <li>أن يفهم المتدرب الدوافع وراء تطوير الجيل السادس (6G) ورؤيته المستقبلية.</li>
                            <li>أن يحدد المتدرب المتطلبات الرئيسية لشبكات 6G.</li>
                            <li>أن يشرح المتدرب مفهوم الاتصالات في نطاق التيراهرتز وإمكانياتها وتحدياتها.</li>
                            <li>أن يوضح المتدرب دور الذكاء الاصطناعي والتعلم الآلي في تحسين أداء شبكات 6G.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>محتويات المحاضرة:</h4>
                        <p class="font-semibold text-gray-700">1. رؤية الجيل السادس (6G):</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>لماذا 6G؟: تجاوز حدود 5G، الحاجة إلى سرعات أعلى، زمن انتقال أقل، كفاءة طاقوية أكبر، ودعم تطبيقات أكثر تعقيداً.</li>
                            <li>الرؤية المستقبلية لـ 6G:
                                <ul class="list-disc pr-6">
                                    <li>**الاتصال الشامل (Ubiquitous Connectivity):** اتصال سلس ومستمر في كل مكان ولكل شيء.</li>
                                    <li>**الذكاء الاصطناعي في كل مكان (AI-everywhere):** دمج الذكاء الاصطناعي في جميع مستويات الشبكة لتحسين الأداء والإدارة الذاتية.</li>
                                    <li>**الدمج بين العوالم المادية والرقمية:** تجارب غامرة تتجاوز الواقع الافتراضي والمعزز.</li>
                                </ul>
                            </li>
                            <li>المتطلبات الرئيسية لـ 6G: سرعات تصل إلى تيرا بت/ثانية، زمن انتقال ميكروثانية، كفاءة طاقوية غير مسبوقة، أمن وخصوصية معززين.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">2. الاتصالات في نطاق التيراهرتز (Terahertz Communication):</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>المفهوم: استخدام ترددات في نطاق التيراهرتز (0.1 THz إلى 10 THz) لنقل البيانات.</li>
                            <li>الإمكانيات الهائلة للنطاق الترددي: توفير نطاق ترددي أكبر بآلاف المرات من 5G، مما يتيح سرعات بيانات غير مسبوقة.</li>
                            <li>التحديات البحثية والتكنولوجية: ارتفاع توهين الإشارة، الحاجة إلى مكونات إلكترونية جديدة، تحديات التشكيل والإلغاء.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">3. الذكاء الاصطناعي والتعلم الآلي (AI/ML) في 6G:</p>
                        <ul class="list-disc pr-6">
                            <li>دوره في تحسين أداء الشبكة: تحسين تخصيص الموارد، إدارة التداخل، التنبؤ بالازدحام.</li>
                            <li>الإدارة الذاتية (Self-Organizing Networks - SON): تمكين الشبكة من تكوين نفسها، تحسين أدائها، وإصلاح الأعطال تلقائياً.</li>
                            <li>الشبكات الذكية والمستقلة: شبكات قادرة على التعلم والتكيف واتخاذ القرارات دون تدخل بشري كبير.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>مسار الجلسة للمحاضرة الرابعة:</h4>
                        <table>
                            <thead>
                                <tr>
                                    <th>العنصر</th>
                                    <th>الوصف</th>
                                    <th>المدة المقترحة</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>مقدمة المحاضرة</td>
                                    <td>ترحيب، أهداف المحاضرة، مراجعة سريعة.</td>
                                    <td>10 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>رؤية الجيل السادس (6G)</td>
                                    <td>شرح الدوافع، الرؤية المستقبلية، والمتطلبات.</td>
                                    <td>50 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>الاتصالات في نطاق التيراهرتز</td>
                                    <td>شرح المفهوم والإمكانيات والتحديات.</td>
                                    <td>45 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 4.1: نقاش مفتوح</td>
                                    <td>تخيل الحياة مع 6G.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>الذكاء الاصطناعي والتعلم الآلي في 6G</td>
                                    <td>شرح دور AI/ML في الشبكة.</td>
                                    <td>40 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 4.2: عرض تقديمي قصير</td>
                                    <td>تحضير عرض عن أهمية نطاق التيراهرتز.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 4.1: بحث عن متطلبات 6G</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 4.2: تصميم مفهوم</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>أسئلة وأجوبة وملخص</td>
                                    <td>فتح باب الأسئلة وتلخيص المحاضرة.</td>
                                    <td>10 دقيقة</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>

                    <div class="activity-task-section">
                        <h4>النشاط 4.1: نقاش مفتوح</h4>
                        <p>تخيل كيف ستبدو حياتنا اليومية مع تحقيق رؤية 6G للاتصال الشامل والذكاء الاصطناعي في كل مكان.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>النشاط 4.2: عرض تقديمي قصير</h4>
                        <p>جهز عرضًا تقديميًا موجزًا عن أهمية نطاق التيراهرتز في تحقيق سرعات 6G الفائقة.</p>
                    </div>
                    <button class="mt-2 btn-toggle" onclick="openVideo('https://www.youtube.com/watch?v=0hK4W_vD-d8')">تشغيل الفيديو (اتصالات التيراهرتز)</button>
                    <div class="activity-task-section">
                        <h4>المهمة 4.1: بحث عن متطلبات 6G</h4>
                        <p>ابحث عن أحدث الأوراق البحثية أو التقارير التي تتحدث عن المتطلبات غير التقنية لـ 6G (مثل المتطلبات الاجتماعية أو الاقتصادية).</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>المهمة 4.2: تصميم مفهوم</h4>
                        <p>صمم مفهومًا لخدمة جديدة يمكن أن تصبح ممكنة فقط بفضل دمج الذكاء الاصطناعي في شبكات 6G.</p>
                    </div>
                </div>
            </div>

            <div class="lecture-card">
                <div class="lecture-header" onclick="toggleLecture('lecture5')">
                    <h2>المحاضرة الخامسة: التقنيات الناشئة في 6G (الجزء الثاني) وتطبيقاتها</h2>
                    <button class="btn-toggle" id="toggle5">+</button>
                </div>
                <div class="lecture-content" id="lecture5-content">
                    <div class="lecture-details-section">
                        <h4>الأهداف السلوكية للمحاضرة:</h4>
                        <ul class="list-disc pr-6">
                            <li>أن يشرح المتدرب مفهوم الأسطح الذكية القابلة لإعادة التكوين (RIS) ودورها في تحسين الشبكة.</li>
                            <li>أن يتعرف المتدرب على أساسيات الاتصالات الكمومية وتطبيقاتها الأمنية المحتملة في 6G.</li>
                            <li>أن يوضح المتدرب مفهوم الاستشعار والاتصالات المتكاملة (ISAC) وتطبيقاتها.</li>
                            <li>أن يحدد المتدرب كيف يمكن لتقنية البلوك تشين تعزيز الأمن في شبكات 6G.</li>
                            <li>أن يتوقع المتدرب تطبيقات 6G المستقبلية مثل التوائم الرقمية والإنترنت الحسي.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>محتويات المحاضرة:</h4>
                        <p class="font-semibold text-gray-700">1. الأسطح الذكية القابلة لإعادة التكوين (Reconfigurable Intelligent Surfaces - RIS):</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>المفهوم: أسطح سلبية كبيرة تتكون من عناصر صغيرة يمكنها التحكم في انعكاس أو انكسار موجات الراديو.</li>
                            <li>كيفية تحسين تغطية الإشارة وكفاءة الطاقة: توجيه الإشارة بذكاء لتجاوز العوائق، تحسين جودة الإشارة للمستخدمين.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">2. الاتصالات الكمومية (Quantum Communication):</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>أساسيات الاتصالات الكمومية: استخدام مبادئ ميكانيكا الكم (مثل التشابك الفائق) لنقل المعلومات.</li>
                            <li>تطبيقاتها في الأمن: توزيع المفاتيح الكمومية (QKD) لتوفير أمان غير قابل للاختراق.</li>
                            <li>دورها المحتمل في 6G: توفير طبقة أمان فائقة للبيانات الحساسة.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">3. الاستشعار والاتصالات المتكاملة (Integrated Sensing and Communication - ISAC):</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>دمج وظائف الاستشعار والاتصالات: استخدام نفس موجات الراديو لكل من نقل البيانات واكتشاف الأجسام المحيطة (الرادار).</li>
                            <li>تطبيقات ISAC: المدن الذكية (مراقبة حركة المرور، اكتشاف المشاة)، المركبات ذاتية القيادة (تحديد المسافة والسرعة)، الرعاية الصحية (مراقبة العلامات الحيوية).</li>
                        </ul>
                        <p class="font-semibold text-gray-700">4. تقنية البلوك تشين (Blockchain) للأمن:</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>استخدام البلوك تشين لتعزيز الأمن والخصوصية: سجلات موزعة غير قابلة للتغيير لتأمين المعاملات، إدارة الهوية، والتحكم في الوصول.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">5. رؤية تطبيقات 6G:</p>
                        <ul class="list-disc pr-6">
                            <li>**الاتصالات الشاملة (Ubiquitous Connectivity):** اتصال في كل مكان، حتى في الفضاء وتحت الماء.</li>
                            <li>**التوائم الرقمية (Digital Twins):** نسخ افتراضية دقيقة للأشياء المادية أو الأنظمة، يتم تحديثها في الوقت الفعلي.</li>
                            <li>**الاتصالات الهولوغرافية (Holographic Communication):** نقل صور ثلاثية الأبعاد واقعية في الوقت الفعلي.</li>
                            <li>**الإنترنت الحسي (Internet of Senses):** نقل التجارب الحسية (اللمس، الشم، التذوق) عبر الشبكة.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>مسار الجلسة للمحاضرة الخامسة:</h4>
                        <table>
                            <thead>
                                <tr>
                                    <th>العنصر</th>
                                    <th>الوصف</th>
                                    <th>المدة المقترحة</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>مقدمة المحاضرة</td>
                                    <td>ترحيب، أهداف المحاضرة، مراجعة سريعة.</td>
                                    <td>10 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>الأسطح الذكية القابلة لإعادة التكوين (RIS)</td>
                                    <td>شرح المفهوم والدور في تحسين الشبكة.</td>
                                    <td>40 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>الاستشعار والاتصالات المتكاملة (ISAC)</td>
                                    <td>شرح المفهوم والتطبيقات.</td>
                                    <td>30 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>تقنية البلوك تشين للأمن</td>
                                    <td>شرح دور البلوك تشين في تعزيز الأمن.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 5.1: فيديو توضيحي</td>
                                    <td>مشاهدة فيديو عن التوائم الرقمية.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 5.2: ورشة عمل صغيرة</td>
                                    <td>مناقشة حلول RIS للمناطق الميتة.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 5.1: تحليل حالة استخدام</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 5.2: بحث عن الأمن الكمومي</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>أسئلة وأجوبة وملخص</td>
                                    <td>فتح باب الأسئلة وتلخيص المحاضرة.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>

                    <div class="activity-task-section">
                        <h4>النشاط 5.1: فيديو توضيحي</h4>
                        <p>شاهد فيديو يشرح مفهوم التوائم الرقمية (Digital Twins) وكيف يمكن لـ 6G دعمها.</p>
                    </div>
                    <button class="mt-2 btn-toggle" onclick="openVideo('https://www.youtube.com/watch?v=G010w_y2u3g')">تشغيل الفيديو (Digital Twins)</button>
                    <div class="activity-task-section">
                        <h4>النشاط 5.2: ورشة عمل صغيرة</h4>
                        <p>ناقش كيف يمكن لـ RIS أن يحل مشكلة "المناطق الميتة" في تغطية الشبكة.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>المهمة 5.1: تحليل حالة استخدام</h4>
                        <p>اختر تطبيقًا واحدًا لـ ISAC (مثل القيادة الذاتية) واشرح كيف يمكن أن يحسن هذا التكامل الأداء والأمان.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>المهمة 5.2: بحث عن الأمن الكمومي</h4>
                        <p>ابحث عن التحديات الحالية في الأمن السيبراني وكيف يمكن للاتصالات الكمومية أن توفر حلولاً مستقبلية.</p>
                    </div>
                </div>
            </div>

            <div class="lecture-card">
                <div class="lecture-header" onclick="toggleLecture('lecture6')">
                    <h2>المحاضرة السادسة: التحديات والآفاق المستقبلية لـ 5G و 6G</h2>
                    <button class="btn-toggle" id="toggle6">+</button>
                </div>
                <div class="lecture-content" id="lecture6-content">
                    <div class="lecture-details-section">
                        <h4>الأهداف السلوكية للمحاضرة:</h4>
                        <ul class="list-disc pr-6">
                            <li>أن يحدد المتدرب التحديات الرئيسية المتعلقة بنشر وتطبيق 5G و 6G.</li>
                            <li>أن يناقش المتدرب القضايا الأمنية والخصوصية المرتبطة بهذه التقنيات.</li>
                            <li>أن يفهم المتدرب أهمية التوحيد القياسي والتنظيم في تطوير الشبكات اللاسلكية.</li>
                            <li>أن يتعرف المتدرب على خارطة الطريق والجهود العالمية نحو تحقيق 6G.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>محتويات المحاضرة:</h4>
                        <p class="font-semibold text-gray-700">1. تحديات النشر والتطبيق:</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>**البنية التحتية:** الحاجة إلى استثمارات ضخمة في البنية التحتية الجديدة (أبراج، خلايا صغيرة، ألياف بصرية).</li>
                            <li>**التكاليف:** ارتفاع تكاليف البحث والتطوير والنشر والصيانة.</li>
                            <li>**توفر الطيف الترددي:** الحاجة إلى تخصيص المزيد من الطيف الترددي، خاصة في النطاقات العالية.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">2. الأمن والخصوصية:</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>التحديات الأمنية في 5G و 6G: زيادة نقاط الهجوم بسبب تزايد الأجهزة المتصلة، تعقيد الشبكة، هجمات حجب الخدمة الموزعة (DDoS).</li>
                            <li>حلولها المحتملة: استخدام البلوك تشين، التشفير المتقدم، الأمن القائم على الذكاء الاصطناعي، الأمن الكمومي.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">3. التوحيد القياسي والتنظيم:</p>
                        <ul class="list-disc pr-6 mb-2">
                            <li>دور المنظمات الدولية: مثل 3GPP و ITU في وضع المعايير العالمية لضمان التوافقية والتشغيل البيني.</li>
                        </ul>
                        <p class="font-semibold text-gray-700">4. خارطة الطريق نحو 6G:</p>
                        <ul class="list-disc pr-6">
                            <li>الجهود البحثية العالمية: استثمارات كبيرة من الحكومات والجامعات والشركات في أبحاث 6G.</li>
                            <li>التعاون الدولي: الشراكات بين الدول والمنظمات لتطوير التقنيات وتوحيد المعايير.</li>
                            <li>الآفاق المستقبلية: التحول نحو شبكات ذكية بالكامل، متكاملة، ومستدامة تدعم جميع جوانب الحياة.</li>
                        </ul>
                    </div>
                    <div class="lecture-details-section">
                        <h4>مسار الجلسة للمحاضرة السادسة:</h4>
                        <table>
                            <thead>
                                <tr>
                                    <th>العنصر</th>
                                    <th>الوصف</th>
                                    <th>المدة المقترحة</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>مقدمة المحاضرة</td>
                                    <td>ترحيب، أهداف المحاضرة، مراجعة سريعة.</td>
                                    <td>10 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>تحديات النشر والتطبيق</td>
                                    <td>شرح البنية التحتية، التكاليف، والطيف.</td>
                                    <td>45 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>الأمن والخصوصية</td>
                                    <td>مناقشة التحديات الأمنية والحلول.</td>
                                    <td>40 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 6.1: مناقشة جماعية</td>
                                    <td>مناقشة التحديات الاقتصادية والاجتماعية.</td>
                                    <td>25 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>التوحيد القياسي والتنظيم</td>
                                    <td>دور المنظمات الدولية.</td>
                                    <td>30 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>خارطة الطريق نحو 6G</td>
                                    <td>الجهود البحثية والتعاون الدولي والآفاق.</td>
                                    <td>30 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>النشاط 6.2: تحليل أخبار</td>
                                    <td>البحث عن آخر أخبار 6G ومشاركتها.</td>
                                    <td>20 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 6.1: اقتراح سياسات</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>المهمة 6.2: رؤية شخصية</td>
                                    <td>تخصيص وقت لبدء المهمة وتوضيحها.</td>
                                    <td>15 دقيقة</td>
                                </tr>
                                <tr>
                                    <td>أسئلة وأجوبة وملخص</td>
                                    <td>فتح باب الأسئلة وتلخيص المحاضرة.</td>
                                    <td>10 دقيقة</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>

                    <div class="activity-task-section">
                        <h4>النشاط 6.1: مناقشة جماعية</h4>
                        <p>ناقش التحديات الاقتصادية والاجتماعية لنشر شبكات 6G على نطاق واسع.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>النشاط 6.2: تحليل أخبار</h4>
                        <p>ابحث عن آخر الأخبار أو المقالات حول تطورات 6G العالمية وشاركها مع المجموعة.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>المهمة 6.1: اقتراح سياسات</h4>
                        <p>اقترح ثلاث سياسات يمكن للحكومات تبنيها لتسريع نشر 6G مع ضمان الأمن والخصوصية.</p>
                    </div>
                    <div class="activity-task-section">
                        <h4>المهمة 6.2: رؤية شخصية</h4>
                        <p>اكتب فقرة قصيرة تلخص رؤيتك الشخصية لمستقبل الاتصالات اللاسلكية بعد 6G.</p>
                    </div>
                </div>
            </div>

            <div class="lecture-card">
                <div class="lecture-header" onclick="toggleLecture('final-exam')">
                    <h2>الاختبار النهائي</h2>
                    <button class="btn-toggle" id="toggle-final-exam">+</button>
                </div>
                <div class="lecture-content" id="final-exam-content">
                    <p class="mb-4">هذا هو الاختبار النهائي للحقيبة التدريبية. يرجى الإجابة على جميع الأسئلة لتقييم فهمك الشامل للمفاهيم.</p>
                    <div class="interactive-section">
                        <p class="font-bold">عنصر تفاعلي: ابدأ الاختبار</p>
                        <p>سيتضمن الاختبار أسئلة متعددة الخيارات وأسئلة مقالية قصيرة تغطي جميع المحاضرات.</p>
                        <button class="mt-2 btn-toggle">ابدأ الاختبار الآن</button>
                    </div>
                </div>
            </div>

            <section class="logistics-section">
                <h3>التحضيرات اللوجستية للحقيبة التدريبية</h3>
                <p>لضمان سير الحقيبة التدريبية بسلاسة وتحقيق أقصى استفادة، يجب مراعاة التحضيرات التالية:</p>
                <h4 class="text-right font-semibold mt-4 mb-2">قبل الحقيبة التدريبية:</h4>
                <ul class="list-disc pr-6 text-right mx-auto">
                    <li>**تجهيز القاعة:** التأكد من توفر قاعة تدريب مناسبة، مجهزة ببروجيكتور، شاشة عرض، نظام صوت، وسبورة بيضاء أو شاشة تفاعلية.</li>
                    <li>**المعدات التقنية:** توفير أجهزة حاسوب للمتدربين (إذا لزم الأمر للأنشطة العملية)، اتصال إنترنت مستقر وعالي السرعة.</li>
                    <li>**المواد التدريبية:** طباعة أو توفير نسخ رقمية من دليل المتدرب، الشرائح التقديمية، أوراق العمل، والمراجع الإضافية.</li>
                    <li>**التسجيل والتنظيم:** إتمام عملية تسجيل المتدربين، وتوزيع جدول الحقيبة التدريبية عليهم مسبقاً.</li>
                    <li>**التنسيق مع المحاضر:** التأكد من جاهزية المحاضر، ومراجعة المحتوى والأنشطة معه.</li>
                    <li>**المشروبات والضيافة:** ترتيب توفير المشروبات والوجبات الخفيفة خلال فترات الاستراحة.</li>
                </ul>
                <h4 class="text-right font-semibold mt-4 mb-2">أثناء الحقيبة التدريبية:</h4>
                <ul class="list-disc pr-6 text-right mx-auto">
                    <li>**الدعم الفني:** توفير دعم فني مستمر لمعالجة أي مشاكل تقنية قد تطرأ.</li>
                    <li>**إدارة الوقت:** الالتزام بالجدول الزمني المحدد لكل محاضرة ونشاط.</li>
                    <li>**تسهيل الأنشطة:** توجيه المتدربين خلال الأنشطة الجماعية والمهمات، وتقديم المساعدة عند الحاجة.</li>
                    <li>**جمع الملاحظات:** تشجيع المتدربين على تقديم الملاحظات الدورية.</li>
                    <li>**الراحة والبيئة:** ضمان بيئة تدريب مريحة ومحفزة للتعلم.</li>
                </ul>
                <h4 class="text-right font-semibold mt-4 mb-2">بعد الحقيبة التدريبية:</h4>
                <ul class="list-disc pr-6 text-right mx-auto">
                    <li>**جمع الاستبيانات:** التأكد من جمع جميع استبيانات التقييم من المتدربين.</li>
                    <li>**تحليل النتائج:** تحليل نتائج الاختبار النهائي والاستبيانات لتقييم فعالية الحقيبة.</li>
                    <li>**إصدار الشهادات:** إعداد وتسليم شهادات إتمام الحقيبة التدريبية للمتدربين.</li>
                    <li>**المتابعة:** تقديم أي دعم إضافي أو موارد للمتدربين بعد انتهاء الحقيبة (إذا كان ذلك جزءاً من الخطة).</li>
                </ul>
            </section>

            <section class="recommendations-section">
                <h3>توصيات للمتدربين لتحقيق الاستفادة القصوى</h3>
                <p>لضمان تحقيق أقصى استفادة من هذه الحقيبة التدريبية القيمة، يرجى الالتزام بالتوصيات التالية:</p>
                <ul class="list-disc pr-6 text-right mx-auto">
                    <li>**التحضير المسبق:** مراجعة المحتوى التمهيدي وأهداف كل محاضرة قبل بدء الجلسة.</li>
                    <li>**المشاركة الفعالة:** الانخراط بنشاط في المناقشات والأنشطة الجماعية وطرح الأسئلة.</li>
                    <li>**تدوين الملاحظات:** كتابة الملاحظات الهامة أثناء الشرح والأنشطة لتثبيت المعلومات.</li>
                    <li>**التطبيق العملي:** محاولة تطبيق المفاهيم النظرية في المهام والتمارين العملية.</li>
                    <li>**البحث الإضافي:** استكشاف المصادر الإضافية والمقالات الموصى بها للتعمق في الموضوعات.</li>
                    <li>**التفاعل مع الزملاء:** تبادل الأفكار والخبرات مع المتدربين الآخرين.</li>
                    <li>**الاستراحة الكافية:** أخذ فترات راحة منتظمة للحفاظ على التركيز والطاقة.</li>
                    <li>**تقديم الملاحظات:** لا تتردد في تقديم ملاحظاتك واقتراحاتك لتحسين الحقيبة التدريبية.</li>
                    <li>**المراجعة الدورية:** مراجعة محتويات المحاضرات بشكل دوري بعد كل جلسة.</li>
                </ul>
            </section>

            <div class="lecture-card">
                <div class="lecture-header" onclick="toggleLecture('surveys')">
                    <h2>استبيانات التقييم</h2>
                    <button class="btn-toggle" id="toggle-surveys">+</button>
                </div>
                <div class="lecture-content" id="surveys-content">
                    <p class="mb-4">ملاحظاتك قيمة جدًا لمساعدتنا في تحسين الحقيبة التدريبية والعملية التعليمية.</p>

                    <div class="activity-task-section mb-4">
                        <h4>استبيان تقييم المحاضر</h4>
                        <form class="survey-form">
                            <label>وضوح الشرح:</label>
                            <input type="radio" name="lecturer_clarity" value="5"> ممتاز
                            <input type="radio" name="lecturer_clarity" value="4"> جيد جداً
                            <input type="radio" name="lecturer_clarity" value="3"> جيد
                            <input type="radio" name="lecturer_clarity" value="2"> مقبول
                            <input type="radio" name="lecturer_clarity" value="1"> ضعيف
                            <label class="mt-2">القدرة على الإجابة على الأسئلة:</label>
                            <input type="radio" name="lecturer_answers" value="5"> ممتاز
                            <input type="radio" name="lecturer_answers" value="4"> جيد جداً
                            <input type="radio" name="lecturer_answers" value="3"> جيد
                            <input type="radio" name="lecturer_answers" value="2"> مقبول
                            <input type="radio" name="lecturer_answers" value="1"> ضعيف
                            <label class="mt-2" for="lecturer_comments">ملاحظات إضافية عن المحاضر:</label>
                            <textarea id="lecturer_comments" rows="3"></textarea>
                            <button type="submit">إرسال</button>
                        </form>
                    </div>

                    <div class="activity-task-section mb-4">
                        <h4>استبيان تقييم الحقيبة التدريبية</h4>
                        <form class="survey-form">
                            <label>شمولية المحتوى:</label>
                            <input type="radio" name="kit_comprehensiveness" value="5"> ممتاز
                            <input type="radio" name="kit_comprehensiveness" value="4"> جيد جداً
                            <input type="radio" name="kit_comprehensiveness" value="3"> جيد
                            <input type="radio" name="kit_comprehensiveness" value="2"> مقبول
                            <input type="radio" name="kit_comprehensiveness" value="1"> ضعيف
                            <label class="mt-2">سهولة الفهم والتنظيم:</label>
                            <input type="radio" name="kit_clarity" value="5"> ممتاز
                            <input type="radio" name="kit_clarity" value="4"> جيد جداً
                            <input type="radio" name="kit_clarity" value="3"> جيد
                            <input type="radio" name="kit_clarity" value="2"> مقبول
                            <input type="radio" name="kit_clarity" value="1"> ضعيف
                            <label class="mt-2" for="kit_comments">ملاحظات إضافية عن الحقيبة:</label>
                            <textarea id="kit_comments" rows="3"></textarea>
                            <button type="submit">إرسال</button>
                        </form>
                    </div>

                    <div class="activity-task-section">
                        <h4>استبيان تقييم الإعدادات اللوجستية</h4>
                        <form class="survey-form">
                            <label>جودة القاعة والتجهيزات:</label>
                            <input type="radio" name="logistics_venue" value="5"> ممتاز
                            <input type="radio" name="logistics_venue" value="4"> جيد جداً
                            <input type="radio" name="logistics_venue" value="3"> جيد
                            <input type="radio" name="logistics_venue" value="2"> مقبول
                            <input type="radio" name="logistics_venue" value="1"> ضعيف
                            <label class="mt-2">الدعم الفني:</label>
                            <input type="radio" name="logistics_support" value="5"> ممتاز
                            <input type="radio" name="logistics_support" value="4"> جيد جداً
                            <input type="radio" name="logistics_support" value="3"> جيد
                            <input type="radio" name="logistics_support" value="2"> مقبول
                            <input type="radio" name="logistics_support" value="1"> ضعيف
                            <label class="mt-2" for="logistics_comments">ملاحظات إضافية عن اللوجستيات:</label>
                            <textarea id="logistics_comments" rows="3"></textarea>
                            <button type="submit">إرسال</button>
                        </form>
                    </div>
                </div>
            </div>

            <section class="rubric-section">
                <h3>روبرك تقييم الحقيبة التدريبية</h3>
                <p>هذا الروبرك مصمم لتقييم جودة وفعالية الحقيبة التدريبية الشاملة.</p>
                <table class="rubric-table">
                    <thead>
                        <tr>
                            <th>المعيار</th>
                            <th>ممتاز (4 نقاط)</th>
                            <th>جيد (3 نقاط)</th>
                            <th>مقبول (2 نقطة)</th>
                            <th>يحتاج تحسين (1 نقطة)</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>المحتوى العلمي</td>
                            <td>المعلومات دقيقة، شاملة، وحديثة. المفاهيم معروضة بوضوح وعمق.</td>
                            <td>المعلومات دقيقة بمعظمها مع بعض التفاصيل البسيطة الناقصة.</td>
                            <td>المعلومات صحيحة بشكل عام لكنها سطحية وتفتقر للعمق.</td>
                            <td>المعلومات غير دقيقة أو قديمة.</td>
                        </tr>
                        <tr>
                            <td>الأهداف التعليمية</td>
                            <td>الأهداف (العامة والسلوكية) واضحة، قابلة للقياس، ومرتبطة بشكل مباشر بالمحتوى والأنشطة.</td>
                            <td>الأهداف واضحة بشكل عام ولكن قد تكون بعضها غير قابلة للقياس المباشر.</td>
                            <td>الأهداف موجودة ولكنها غامضة أو غير مرتبطة بشكل وثيق بالمحتوى.</td>
                            <td>الأهداف مفقودة أو غير واضحة.</td>
                        </tr>
                        <tr>
                            <td>التنظيم والهيكلة</td>
                            <td>الحقيبة منظمة بشكل منطقي ومتسلسل. التنقل بين الأقسام سهل وبديهي.</td>
                            <td>التنظيم جيد ولكن يمكن تحسين تسلسل بعض الأقسام.</td>
                            <td>التنظيم موجود ولكنه مربك في بعض الأحيان، مما يجعل التصفح صعبًا.</td>
                            <td>لا يوجد هيكل واضح، والمحتوى عشوائي.</td>
                        </tr>
                        <tr>
                            <td>الأنشطة والمهام</td>
                            <td>الأنشطة متنوعة، إبداعية، وتدعم الأهداف التعليمية بشكل مباشر. المهام عملية وتعزز التفكير النقدي.</td>
                            <td>الأنشطة والمهام جيدة ولكنها قد تكون نمطية أو لا ترتبط دائمًا بالأهداف.</td>
                            <td>الأنشطة قليلة أو بسيطة جدًا، ولا تشجع على التفاعل العميق مع المادة.</td>
                            <td>الأنشطة والمهام غير موجودة أو غير مرتبطة بالمحتوى.</td>
                        </tr>
                        <tr>
                            <td>التقييم</td>
                            <td>الاختبار النهائي والاستبيانات مصممة بشكل جيد، شاملة، وتقيس بدقة مدى تحقق الأهداف.</td>
                            <td>أدوات التقييم موجودة ومناسبة، ولكنها قد تحتاج إلى بعض التحسين لتكون أكثر شمولية.</td>
                            <td>التقييم يغطي بعض جوانب المادة فقط أو أن الأسئلة غير واضحة.</td>
                            <td>أدوات التقييم غير موجودة أو غير فعالة.</td>
                        </tr>
                        <tr>
                            <td>التصميم والجودة البصرية</td>
                            <td>تصميم احترافي وجذاب. استخدام متناسق للألوان والخطوط. واجهة المستخدم سهلة وبديهية.</td>
                            <td>التصميم جيد بشكل عام ولكن هناك بعض العيوب البسيطة في التنسيق أو الألوان.</td>
                            <td>التصميم أساسي ويفتقر إلى الجاذبية البصرية. قد يكون النص صعب القراءة في بعض الأماكن.</td>
                            <td>تصميم ضعيف، غير احترافي، ويصعب استخدامه.</td>
                        </tr>
                    </tbody>
                </table>
            </section>

            <section class="conclusion-section">
                <h3>الخلاصة والاستنتاجات والخاتمة</h3>
                <p>لقد قدمت هذه الحقيبة التدريبية رحلة شاملة في عالم الاتصالات اللاسلكية، بدءًا من أساسيات الجيل الخامس (5G) وتقنياته المبتكرة، وصولاً إلى الرؤى المستقبلية الطموحة للجيل السادس (6G) والتقنيات الناشئة التي ستقوده. استكشفنا كيف أن 5G، بركائزه الثلاث (eMBB, URLLC, mMTC)، قد أحدث ثورة في الاتصال، ممكّنًا تطبيقات لم تكن ممكنة من قبل في مجالات مثل المدن الذكية، الرعاية الصحية، والصناعة 4.0. تعلمنا عن تقنيات مثل Massive MIMO، وتشكيل الحزمة، وموجات المليمتر التي تدعم الأداء الفائق لـ 5G، وكيف أن مفاهيم مثل تقسيم الشبكة والحوسبة الطرفية قد غيرت طريقة إدارة الشبكات وتقديم الخدمات.</p>
                <p>بالانتقال إلى 6G، رأينا أن الطموح يتجاوز مجرد السرعة وزمن الانتقال، ليشمل دمج الذكاء الاصطناعي في كل جانب من جوانب الشبكة، واستخدام نطاقات ترددية غير مسبوقة مثل التيراهرتز، وتطوير تقنيات ثورية مثل الأسطح الذكية القابلة لإعادة التكوين (RIS) والاتصالات الكمومية. هذه التقنيات تعد بتمكين عوالم افتراضية غامرة، وتوائم رقمية دقيقة، وإنترنت حسي يربط البشر بالبيئة الرقمية بطرق غير مسبوقة.</p>
                <p>في الختام، تتجلى أهمية هذه الأجيال الجديدة من الشبكات في قدرتها على تشكيل مستقبلنا الرقمي، ليس فقط من خلال توفير اتصال أسرع وأكثر موثوقية، بل من خلال تمكين الابتكارات التي ستعيد تعريف الصناعات، وتحسين جودة الحياة، وتفتح آفاقًا جديدة للبحث والتطوير. التحديات لا تزال قائمة، خاصة فيما يتعلق بالبنية التحتية، الأمن، والتوحيد القياسي، ولكن الجهود البحثية والتعاون الدولي يبشران بمستقبل مشرق للاتصالات اللاسلكية.</p>
            </section>

            <section class="acknowledgement-section">
                <h3>كلمة شكر وتقدير</h3>
                <p>نتقدم بجزيل الشكر والامتنان إلى جميع المتدربين والمنضمين الكرام لهذه الدورة التدريبية على اهتمامهم ومشاركتهم الفعالة، والتي أثرت المحتوى وأغنت النقاشات. كما نتوجه بخالص الشكر إلى قسم التعليم المستمر في الجامعة المستنصرية على إتاحة هذه الفرصة القيمة لتنظيم وتقديم هذه الحقيبة التدريبية، ودعمهم المتواصل الذي كان له الأثر الأكبر في نجاح هذا العمل.</p>
                <p>ولا يفوتنا أن نعرب عن عميق تقديرنا للسادة المدربين الأفاضل الذين لم يبخلوا علينا بالدعم والمساعدة، وبخبراتهم القيمة التي ساهمت في إثراء هذه الحقيبة. وأخيراً، الشكر موصول لكل من شارك وساهم في إنجاز هذا العمل الرائع، سائلين المولى عز وجل أن يكون هذا الجهد قد حقق الفائدة المرجوة للجميع.</p>
            </section>

            <section class="external-links-section">
                <h3>الروابط الخارجية (المصادر العلمية)</h3>
                <p>للمزيد من التعمق في الموضوعات التي تناولتها هذه الحقيبة التدريبية، نوصي بالاطلاع على المصادر العلمية والتقنية التالية:</p>
                <ul class="list-disc pr-6 text-right mx-auto">
                    <li><a href="https://www.itu.int/en/ITU-R/study-groups/rsg5/rwp5d/Pages/IMT-2020.aspx" target="_blank">ITU-R IMT-2020 (5G) Standards</a></li>
                    <li><a href="https://www.3gpp.org/" target="_blank">3GPP Official Website (5G and beyond)</a></li>
                    <li><a href="https://www.ericsson.com/en/5g" target="_blank">Ericsson: What is 5G?</a></li>
                    <li><a href="https://www.nokia.com/networks/6g/" target="_blank">Nokia: Towards 6G</a></li>
                    <li><a href="https://www.qualcomm.com/5g/what-is-5g" target="_blank">Qualcomm: What is 5G?</a></li>
                    <li><a href="https://www.ieee.org/" target="_blank">IEEE Xplore Digital Library (for research papers)</a></li>
                    <li><a href="https://www.nature.com/collections/qgqgqg" target="_blank">Nature: Quantum Communications</a></li>
                    <li><a href="https://www.gsma.com/futurenetworks/wiki/what-is-network-slicing/" target="_blank">GSMA: What is Network Slicing?</a></li>
                    <li><a href="https://www.techtarget.com/searchnetworking/definition/edge-computing" target="_blank">TechTarget: Edge Computing Definition</a></li>
                </ul>
            </section>
        </main>
    </div>

    <script>
        function toggleLecture(lectureId) {
            const content = document.getElementById(lectureId + '-content');
            
            let toggleButtonId;
            if (lectureId.startsWith('lecture')) {
                toggleButtonId = 'toggle' + lectureId.replace('lecture', '');
            } else {
                toggleButtonId = 'toggle-' + lectureId;
            }
            const toggleButton = document.getElementById(toggleButtonId);

            if (!content || !toggleButton) {
                console.error(`Error: Could not find content element with ID "${lectureId}-content" or toggle button with ID "${toggleButtonId}".`);
                return;
            }

            if (content.classList.contains('open')) {
                content.classList.remove('open');
                toggleButton.textContent = '+';
            } else {
                document.querySelectorAll('.lecture-content.open').forEach(item => {
                    item.classList.remove('open');
                    
                    let otherToggleButtonId;
                    const otherLectureId = item.id.replace('-content', '');
                    if (otherLectureId.startsWith('lecture')) {
                        otherToggleButtonId = 'toggle' + otherLectureId.replace('lecture', '');
                    } else {
                        otherToggleButtonId = 'toggle-' + otherLectureId;
                    }
                    const otherToggleButton = document.getElementById(otherToggleButtonId);
                    
                    if (otherToggleButton) {
                        otherToggleButton.textContent = '+';
                    } else {
                        console.warn(`Warning: Could not find other toggle button with ID "${otherToggleButtonId}".`);
                    }
                });

                content.classList.add('open');
                toggleButton.textContent = '-';
            }
        }

        function openVideo(url) {
            window.open(url, '_blank');
        }

        document.addEventListener('DOMContentLoaded', function() {
            toggleLecture('lecture1');
        });
    </script>
</body>
</html>
# raed-ibrahim-khaleel-almsari
