# maintenance-form[Uploading index-1.html…]()
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>استمارة تقييم صيدليات مستشفى الأورام</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800&family=Tajawal:wght@400;500;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #0f766e;
      --primary-dark: #134e4a;
      --primary-light: #14b8a6;
      --accent: #f59e0b;
      --bg: #f0fdfa;
      --card-bg: #ffffff;
      --text: #134e4a;
      --text-light: #6b7280;
      --border: #d1d5db;
      --success: #10b981;
      --danger: #ef4444;
      --shadow: 0 4px 6px -1px rgba(0,0,0,.1), 0 2px 4px -1px rgba(0,0,0,.06);
      --shadow-lg: 0 10px 25px -3px rgba(0,0,0,.1), 0 4px 6px -2px rgba(0,0,0,.05);
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: 'Cairo', 'Tajawal', sans-serif;
      background: linear-gradient(135deg, var(--bg) 0%, #ecfdf5 100%);
      color: var(--text);
      line-height: 1.7;
      min-height: 100vh;
      padding: 20px 10px;
    }
    .container {
      max-width: 900px;
      margin: 0 auto;
    }
    /* Header */
    .header {
      background: linear-gradient(135deg, var(--primary-dark), var(--primary));
      color: white;
      padding: 30px 25px;
      border-radius: 16px;
      margin-bottom: 25px;
      box-shadow: var(--shadow-lg);
      text-align: center;
    }
    .header h1 {
      font-size: 1.7rem;
      font-weight: 800;
      margin-bottom: 8px;
    }
    .header p {
      opacity: 0.95;
      font-size: 0.95rem;
    }
    .header .badge {
      display: inline-block;
      background: var(--accent);
      color: var(--primary-dark);
      padding: 4px 12px;
      border-radius: 20px;
      font-size: 0.75rem;
      font-weight: 700;
      margin-top: 10px;
    }
    /* Pharmacy selector */
    .pharmacy-selector {
      background: white;
      padding: 20px;
      border-radius: 12px;
      margin-bottom: 20px;
      box-shadow: var(--shadow);
      border: 2px solid var(--primary-light);
    }
    .pharmacy-selector h3 {
      color: var(--primary-dark);
      margin-bottom: 15px;
      font-size: 1.05rem;
    }
    /* Sections */
    .section {
      background: var(--card-bg);
      padding: 25px;
      border-radius: 12px;
      margin-bottom: 20px;
      box-shadow: var(--shadow);
      border-right: 5px solid var(--primary);
    }
    .section h2 {
      color: var(--primary-dark);
      font-size: 1.25rem;
      margin-bottom: 20px;
      padding-bottom: 10px;
      border-bottom: 2px dashed var(--primary-light);
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .section h2 .icon {
      background: var(--primary);
      color: white;
      width: 35px;
      height: 35px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.1rem;
    }
    /* Form fields */
    .field {
      margin-bottom: 16px;
    }
    .field label {
      display: block;
      margin-bottom: 6px;
      font-weight: 600;
      color: var(--text);
      font-size: 0.95rem;
    }
    .field label .required {
      color: var(--danger);
      margin-right: 4px;
    }
    .field input[type="text"],
    .field input[type="number"],
    .field input[type="date"],
    .field textarea,
    .field select {
      width: 100%;
      padding: 10px 14px;
      border: 1.5px solid var(--border);
      border-radius: 8px;
      font-family: inherit;
      font-size: 0.95rem;
      background: #fafafa;
      transition: all 0.2s;
    }
    .field input:focus,
    .field textarea:focus,
    .field select:focus {
      outline: none;
      border-color: var(--primary);
      background: white;
      box-shadow: 0 0 0 3px rgba(15, 118, 110, 0.1);
    }
    .field textarea {
      resize: vertical;
      min-height: 70px;
    }
    /* Radio & Checkbox groups */
    .radio-group, .check-group {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 6px;
    }
    .radio-group label, .check-group label {
      display: flex;
      align-items: center;
      gap: 6px;
      padding: 8px 14px;
      background: #f3f4f6;
      border: 1.5px solid transparent;
      border-radius: 8px;
      cursor: pointer;
      font-weight: 500;
      transition: all 0.2s;
      font-size: 0.9rem;
    }
    .radio-group label:hover, .check-group label:hover {
      background: #ecfdf5;
    }
    .radio-group input:checked + span,
    .check-group input:checked + span {
      font-weight: 700;
    }
    .radio-group label:has(input:checked),
    .check-group label:has(input:checked) {
      background: var(--primary);
      color: white;
      border-color: var(--primary-dark);
    }
    .radio-group input, .check-group input {
      accent-color: var(--primary);
    }
    /* Grid for fields */
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 14px;
    }
    /* Sub-section */
    .sub-section {
      background: #f9fafb;
      padding: 16px;
      border-radius: 10px;
      margin-bottom: 16px;
      border-right: 3px solid var(--accent);
    }
    .sub-section h4 {
      color: var(--primary-dark);
      margin-bottom: 12px;
      font-size: 1rem;
    }
    /* Submit */
    .submit-area {
      background: white;
      padding: 25px;
      border-radius: 12px;
      box-shadow: var(--shadow-lg);
      text-align: center;
      margin-bottom: 20px;
    }
    .btn-submit {
      background: linear-gradient(135deg, var(--primary), var(--primary-light));
      color: white;
      border: none;
      padding: 14px 50px;
      font-size: 1.1rem;
      font-weight: 700;
      border-radius: 10px;
      cursor: pointer;
      box-shadow: 0 4px 14px rgba(15, 118, 110, 0.4);
      transition: all 0.2s;
      font-family: inherit;
    }
    .btn-submit:hover:not(:disabled) {
      transform: translateY(-2px);
      box-shadow: 0 6px 20px rgba(15, 118, 110, 0.5);
    }
    .btn-submit:disabled {
      opacity: 0.6;
      cursor: not-allowed;
    }
    /* Status messages */
    .status {
      margin-top: 15px;
      padding: 12px;
      border-radius: 8px;
      display: none;
      font-weight: 600;
    }
    .status.success {
      background: #d1fae5;
      color: #065f46;
      display: block;
    }
    .status.error {
      background: #fee2e2;
      color: #991b1b;
      display: block;
    }
    .status.loading {
      background: #dbeafe;
      color: #1e40af;
      display: block;
    }
    /* Footer */
    .footer {
      text-align: center;
      padding: 20px;
      color: var(--text-light);
      font-size: 0.85rem;
    }
    /* Mobile */
    @media (max-width: 600px) {
      .header h1 { font-size: 1.3rem; }
      .section { padding: 18px; }
      .grid { grid-template-columns: 1fr; }
    }
    /* Hidden utility */
    .hidden { display: none !important; }
    /* Progress */
    .progress-bar {
      background: white;
      padding: 12px 20px;
      border-radius: 10px;
      margin-bottom: 20px;
      box-shadow: var(--shadow);
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 0.85rem;
      color: var(--text-light);
    }
    .progress-fill {
      height: 6px;
      background: linear-gradient(90deg, var(--primary), var(--primary-light));
      border-radius: 3px;
      transition: width 0.3s;
      margin-top: 8px;
    }
    .progress-container {
      width: 100%;
      background: #e5e7eb;
      border-radius: 3px;
      height: 6px;
      margin-top: 8px;
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Header -->
    <div class="header">
      <h1>🏥 استمارة تقييم صيدليات مستشفى الأورام</h1>
      <p>نموذج جمع بيانات الثرام والتجهيزات</p>
      <div class="badge">الإصدار 1.0</div>
    </div>

    <!-- Progress -->
    <div class="progress-bar">
      <div style="width:100%">
        <div>تقدم الاستمارة</div>
        <div class="progress-container">
          <div class="progress-fill" id="progressFill" style="width: 0%"></div>
        </div>
      </div>
      <div id="progressText">0%</div>
    </div>

    <form id="auditForm">

      <!-- Basic Info -->
      <div class="pharmacy-selector">
        <h3>📋 البيانات الأساسية</h3>
        <div class="grid">
          <div class="field">
            <label>اسم الصيدلية <span class="required">*</span></label>
            <select id="pharmacy_name" name="pharmacy_name" required>
              <option value="">-- اختر الصيدلية --</option>
              <option value="صيدلية تأمين خارجي">صيدلية تأمين خارجي</option>
              <option value="صيدلية باطنة خارجي">صيدلية باطنة خارجي</option>
              <option value="صيدلية أطفال خارجي">صيدلية أطفال خارجي</option>
              <option value="صيدلية الالم تأمين خارجي">صيدلية الالم تأمين خارجي</option>
              <option value="صيدلية الالم محاني خارجي">صيدلية الالم محاني خارجي</option>
              <option value="صيدلية باطني داخلي محاني 1">صيدلية باطني داخلي محاني 1</option>
              <option value="صيدلية باطني داخلي محاني 2">صيدلية باطني داخلي محاني 2</option>
              <option value="صيدلية باطني داخلي تأمين 1">صيدلية باطني داخلي تأمين 1</option>
              <option value="صيدلية باطني داخلي تأمين 2">صيدلية باطني داخلي تأمين 2</option>
              <option value="صيدلية باطني داخلي عمليات 1">صيدلية باطني داخلي عمليات 1</option>
              <option value="صيدلية باطني داخلي عمليات 2">صيدلية باطني داخلي عمليات 2</option>
              <option value="صيدلية الطوارئ">صيدلية الطوارئ</option>
            </select>
          </div>
          <div class="field">
            <label>تاريخ التقييم <span class="required">*</span></label>
            <input type="date" id="date" name="date" required />
          </div>
          <div class="field">
            <label>اسم المسئول <span class="required">*</span></label>
            <input type="text" id="officer" name="officer" placeholder="الاسم بالكامل" required />
          </div>
        </div>
      </div>

      <!-- Section 1: Fridge -->
      <div class="section">
        <h2><span class="icon">❄️</span> بيانات الثلاجات</h2>

        <div class="sub-section">
          <h4>الثلاجة رقم 1</h4>
          <div class="grid">
            <div class="field">
              <label>نوع الثلاجة</label>
              <input type="text" name="fridge1_type" placeholder="مثال: أفقية / رأسية" />
            </div>
            <div class="field">
              <label>السعة (لتر)</label>
              <input type="number" name="fridge1_capacity" placeholder="لتر" />
            </div>
            <div class="field">
              <label>عدد الأرفف</label>
              <input type="number" name="fridge1_shelves" placeholder="0" />
            </div>
            <div class="field">
              <label>درجة الحرارة الحالية (°C)</label>
              <input type="number" step="0.1" name="fridge1_temp" placeholder="مثال: 4.5" />
            </div>
            <div class="field">
              <label>مدى الحرارة المطلوب (°C)</label>
              <input type="text" name="fridge1_temp_range" placeholder="مثال: 2 - 8" />
            </div>
            <div class="field">
              <label>متوسط تكلفة المخزون (جنيه)</label>
              <input type="number" name="fridge1_cost" placeholder="جنيه" />
            </div>
          </div>
          <div class="field">
            <label>وجود قفل</label>
            <div class="radio-group">
              <label><input type="radio" name="fridge1_lock" value="نعم"><span>نعم</span></label>
              <label><input type="radio" name="fridge1_lock" value="لا"><span>لا</span></label>
            </div>
          </div>
          <div class="grid">
            <div class="field">
              <label>ملاءمة للعلاج الكيماوي</label>
              <div class="radio-group">
                <label><input type="radio" name="fridge1_chemo" value="نعم"><span>نعم</span></label>
                <label><input type="radio" name="fridge1_chemo" value="لا"><span>لا</span></label>
              </div>
            </div>
            <div class="field">
              <label>ملاءمة للمناعي</label>
              <div class="radio-group">
                <label><input type="radio" name="fridge1_immuno" value="نعم"><span>نعم</span></label>
                <label><input type="radio" name="fridge1_immuno" value="لا"><span>لا</span></label>
              </div>
            </div>
            <div class="field">
              <label>ملاءمة للتدعيمي</label>
              <div class="radio-group">
                <label><input type="radio" name="fridge1_support" value="نعم"><span>نعم</span></label>
                <label><input type="radio" name="fridge1_support" value="لا"><span>لا</span></label>
              </div>
            </div>
            <div class="field">
              <label>المساحة التخزينية كافية</label>
              <div class="radio-group">
                <label><input type="radio" name="fridge1_space" value="نعم"><span>نعم</span></label>
                <label><input type="radio" name="fridge1_space" value="لا"><span>لا</span></label>
              </div>
            </div>
          </div>
          <div class="grid">
            <div class="field">
              <label>حالة الثلاجة العامة</label>
              <select name="fridge1_condition">
                <option value="">-- اختر --</option>
                <option value="جيدة">جيدة</option>
                <option value="متوسطة">متوسطة</option>
                <option value="سيئة">سيئة</option>
              </select>
            </div>
            <div class="field">
              <label>درجة الاستعجال</label>
              <select name="fridge1_urgency">
                <option value="">-- اختر --</option>
                <option value="عاجل">عاجل</option>
                <option value="متوسط">متوسط</option>
                <option value="غير عاجل">غير عاجل</option>
              </select>
            </div>
          </div>
          <div class="field">
            <label>الإجراء التصحيحي</label>
            <textarea name="fridge1_action" placeholder="اكتب الإجراء المطلوب..."></textarea>
          </div>
          <div class="field">
            <label>ملاحظات</label>
            <textarea name="fridge1_notes" placeholder="أي ملاحظات إضافية..."></textarea>
          </div>
        </div>

        <div class="sub-section">
          <h4>الثلاجة رقم 2</h4>
          <div class="grid">
            <div class="field">
              <label>نوع الثلاجة</label>
              <input type="text" name="fridge2_type" placeholder="مثال: أفقية / رأسية" />
            </div>
            <div class="field">
              <label>السعة (لتر)</label>
              <input type="number" name="fridge2_capacity" placeholder="لتر" />
            </div>
            <div class="field">
              <label>عدد الأرفف</label>
              <input type="number" name="fridge2_shelves" placeholder="0" />
            </div>
            <div class="field">
              <label>درجة الحرارة الحالية (°C)</label>
              <input type="number" step="0.1" name="fridge2_temp" placeholder="مثال: 4.5" />
            </div>
            <div class="field">
              <label>مدى الحرارة المطلوب (°C)</label>
              <input type="text" name="fridge2_temp_range" placeholder="مثال: 2 - 8" />
            </div>
            <div class="field">
              <label>متوسط تكلفة المخزون (جنيه)</label>
              <input type="number" name="fridge2_cost" placeholder="جنيه" />
            </div>
          </div>
          <div class="field">
            <label>وجود قفل</label>
            <div class="radio-group">
              <label><input type="radio" name="fridge2_lock" value="نعم"><span>نعم</span></label>
              <label><input type="radio" name="fridge2_lock" value="لا"><span>لا</span></label>
            </div>
          </div>
          <div class="grid">
            <div class="field">
              <label>ملاءمة للعلاج الكيماوي</label>
              <div class="radio-group">
                <label><input type="radio" name="fridge2_chemo" value="نعم"><span>نعم</span></label>
                <label><input type="radio" name="fridge2_chemo" value="لا"><span>لا</span></label>
              </div>
            </div>
            <div class="field">
              <label>ملاءمة للمناعي</label>
              <div class="radio-group">
                <label><input type="radio" name="fridge2_immuno" value="نعم"><span>نعم</span></label>
                <label><input type="radio" name="fridge2_immuno" value="لا"><span>لا</span></label>
              </div>
            </div>
            <div class="field">
              <label>ملاءمة للتدعيمي</label>
              <div class="radio-group">
                <label><input type="radio" name="fridge2_support" value="نعم"><span>نعم</span></label>
                <label><input type="radio" name="fridge2_support" value="لا"><span>لا</span></label>
              </div>
            </div>
            <div class="field">
              <label>المساحة التخزينية كافية</label>
              <div class="radio-group">
                <label><input type="radio" name="fridge2_space" value="نعم"><span>نعم</span></label>
                <label><input type="radio" name="fridge2_space" value="لا"><span>لا</span></label>
              </div>
            </div>
          </div>
          <div class="grid">
            <div class="field">
              <label>حالة الثلاجة العامة</label>
              <select name="fridge2_condition">
                <option value="">-- اختر --</option>
                <option value="جيدة">جيدة</option>
                <option value="متوسطة">متوسطة</option>
                <option value="سيئة">سيئة</option>
              </select>
            </div>
            <div class="field">
              <label>درجة الاستعجال</label>
              <select name="fridge2_urgency">
                <option value="">-- اختر --</option>
                <option value="عاجل">عاجل</option>
                <option value="متوسط">متوسط</option>
                <option value="غير عاجل">غير عاجل</option>
              </select>
            </div>
          </div>
          <div class="field">
            <label>الإجراء التصحيحي</label>
            <textarea name="fridge2_action" placeholder="اكتب الإجراء المطلوب..."></textarea>
          </div>
          <div class="field">
            <label>ملاحظات</label>
            <textarea name="fridge2_notes" placeholder="أي ملاحظات إضافية..."></textarea>
          </div>
        </div>
      </div>

      <!-- Section 2: Room -->
      <div class="section">
        <h2><span class="icon">🌡️</span> حرارة الغرفة</h2>
        <div class="grid">
          <div class="field">
            <label>حرارة الغرفة (°C)</label>
            <input type="number" step="0.1" name="room_temp" placeholder="مثال: 22" />
          </div>
          <div class="field">
            <label>قراءة الرطوبة الحالية (%)</label>
            <input type="number" name="room_humidity" placeholder="مثال: 45" />
          </div>
          <div class="field">
            <label>مدى الحرارة المطلوب (°C)</label>
            <input type="text" name="room_temp_range" placeholder="مثال: 18 - 25" />
          </div>
          <div class="field">
            <label>مدى الرطوبة المطلوب (%)</label>
            <input type="text" name="room_humidity_range" placeholder="مثال: 30 - 60" />
          </div>
          <div class="field">
            <label>توافر ترمومتر</label>
            <div class="radio-group">
              <label><input type="radio" name="thermometer" value="نعم"><span>نعم</span></label>
              <label><input type="radio" name="thermometer" value="لا"><span>لا</span></label>
            </div>
          </div>
          <div class="field">
            <label>نوع الترمومتر</label>
            <input type="text" name="thermometer_type" placeholder="مثال: رقمي / زئبقي" />
          </div>
          <div class="field">
            <label>التكييف متوفر</label>
            <div class="radio-group">
              <label><input type="radio" name="ac_available" value="نعم"><span>نعم</span></label>
              <label><input type="radio" name="ac_available" value="لا"><span>لا</span></label>
            </div>
          </div>
          <div class="field">
            <label>نوع التكييف</label>
            <input type="text" name="ac_type" placeholder="مثال: سبليت / مركزي" />
          </div>
          <div class="field">
            <label>عدد وحدات التكييف</label>
            <input type="number" name="ac_count" placeholder="0" />
          </div>
          <div class="field">
            <label>حالة التكييف</label>
            <select name="ac_condition">
              <option value="">-- اختر --</option>
              <option value="جيدة">جيدة</option>
              <option value="متوسطة">متوسطة</option>
              <option value="سيئة">سيئة</option>
            </select>
          </div>
          <div class="field">
            <label>ملاءمة الجو</label>
            <div class="radio-group">
              <label><input type="radio" name="atmosphere" value="نعم"><span>نعم</span></label>
              <label><input type="radio" name="atmosphere" value="لا"><span>لا</span></label>
            </div>
          </div>
          <div class="field">
            <label>درجة الاستعجال</label>
            <select name="room_urgency">
              <option value="">-- اختر --</option>
              <option value="عاجل">عاجل</option>
              <option value="متوسط">متوسط</option>
              <option value="غير عاجل">غير عاجل</option>
            </select>
          </div>
          <div class="field">
            <label>العدد المطلوب</label>
            <input type="number" name="room_count_needed" placeholder="0" />
          </div>
        </div>
        <div class="field">
          <label>الإجراء التصحيحي</label>
          <textarea name="room_action" placeholder="اكتب الإجراء المطلوب..."></textarea>
        </div>
        <div class="field">
          <label>ملاحظات</label>
          <textarea name="room_notes" placeholder="أي ملاحظات إضافية..."></textarea>
        </div>
      </div>

      <!-- Section 3: Door -->
      <div class="section">
        <h2><span class="icon">🚪</span> الباب</h2>
        <div class="grid">
          <div class="field">
            <label>وصف الباب</label>
            <input type="text" name="door_desc" placeholder="مثال: خشب / حديد" />
          </div>
          <div class="field">
            <label>نوع الباب</label>
            <input type="text" name="door_type" placeholder="مثال: سحاب / عادي" />
          </div>
          <div class="field">
            <label>نوع القفل</label>
            <input type="text" name="lock_type" placeholder="مثال: كلون / مزلاج" />
          </div>
          <div class="field">
            <label>عدد الأقفال</label>
            <input type="number" name="lock_count" placeholder="0" />
          </div>
          <div class="field">
            <label>حالة الباب</label>
            <select name="door_condition">
              <option value="">-- اختر --</option>
              <option value="جيدة">جيدة</option>
              <option value="متوسطة">متوسطة</option>
              <option value="سيئة">سيئة</option>
            </select>
          </div>
          <div class="field">
            <label>حالة القفل</label>
            <select name="lock_condition">
              <option value="">-- اختر --</option>
              <option value="جيدة">جيدة</option>
              <option value="متوسطة">متوسطة</option>
              <option value="سيئة">سيئة</option>
            </select>
          </div>
          <div class="field">
            <label>التأمين/الحماية</label>
            <input type="text" name="security" placeholder="مثال: كاميرا / إنذار" />
          </div>
          <div class="field">
            <label>درجة الاستعجال</label>
            <select name="door_urgency">
              <option value="">-- اختر --</option>
              <option value="عاجل">عاجل</option>
              <option value="متوسط">متوسط</option>
              <option value="غير عاجل">غير عاجل</option>
            </select>
          </div>
          <div class="field">
            <label>العدد المطلوب</label>
            <input type="number" name="door_count_needed" placeholder="0" />
          </div>
        </div>
        <div class="field">
          <label>الإجراء التصحيحي</label>
          <textarea name="door_action" placeholder="اكتب الإجراء المطلوب..."></textarea>
        </div>
        <div class="field">
          <label>ملاحظات</label>
          <textarea name="door_notes" placeholder="أي ملاحظات إضافية..."></textarea>
        </div>
      </div>

      <!-- Section 4: Camera -->
      <div class="section">
        <h2><span class="icon">📷</span> الكاميرات</h2>
        <div class="sub-section">
          <h4>الكاميرا رقم 1</h4>
          <div class="grid">
            <div class="field">
              <label>موقع/مكان الكاميرا</label>
              <input type="text" name="cam1_location" placeholder="مثال: مدخل الصيدلية" />
            </div>
            <div class="field">
              <label>نوع الكاميرا</label>
              <input type="text" name="cam1_type" placeholder="مثال: IP / Analog" />
            </div>
            <div class="field">
              <label>زاوية التغطية</label>
              <input type="text" name="cam1_angle" placeholder="مثال: 180°" />
            </div>
            <div class="field">
              <label>الموقع ملائم؟</label>
              <div class="radio-group">
                <label><input type="radio" name="cam1_suitable" value="نعم"><span>نعم</span></label>
                <label><input type="radio" name="cam1_suitable" value="لا"><span>لا</span></label>
              </div>
            </div>
            <div class="field">
              <label>حالة الكاميرا</label>
              <select name="cam1_condition">
                <option value="">-- اختر --</option>
                <option value="تعمل">تعمل</option>
                <option value="لا تعمل">لا تعمل</option>
                <option value="جزئي">جزئي</option>
              </select>
            </div>
            <div class="field">
              <label>تخزين التسجيل</label>
              <input type="text" name="cam1_storage" placeholder="مثال: DVR / Cloud" />
            </div>
            <div class="field">
              <label>درجة الاستعجال</label>
              <select name="cam1_urgency">
                <option value="">-- اختر --</option>
                <option value="عاجل">عاجل</option>
                <option value="متوسط">متوسط</option>
                <option value="غير عاجل">غير عاجل</option>
              </select>
            </div>
            <div class="field">
              <label>العدد المطلوب</label>
              <input type="number" name="cam1_count_needed" placeholder="0" />
            </div>
          </div>
          <div class="field">
            <label>الإجراء التصحيحي</label>
            <textarea name="cam1_action" placeholder="اكتب الإجراء المطلوب..."></textarea>
          </div>
          <div class="field">
            <label>ملاحظات</label>
            <textarea name="cam1_notes" placeholder="أي ملاحظات إضافية..."></textarea>
          </div>
        </div>

        <div class="sub-section">
          <h4>الكاميرا رقم 2</h4>
          <div class="grid">
            <div class="field">
              <label>موقع/مكان الكاميرا</label>
              <input type="text" name="cam2_location" placeholder="مثال: الثلاجات" />
            </div>
            <div class="field">
              <label>نوع الكاميرا</label>
              <input type="text" name="cam2_type" placeholder="مثال: IP / Analog" />
            </div>
            <div class="field">
              <label>زاوية التغطية</label>
              <input type="text" name="cam2_angle" placeholder="مثال: 180°" />
            </div>
            <div class="field">
              <label>الموقع ملائم؟</label>
              <div class="radio-group">
                <label><input type="radio" name="cam2_suitable" value="نعم"><span>نعم</span></label>
                <label><input type="radio" name="cam2_suitable" value="لا"><span>لا</span></label>
              </div>
            </div>
            <div class="field">
              <label>حالة الكاميرا</label>
              <select name="cam2_condition">
                <option value="">-- اختر --</option>
                <option value="تعمل">تعمل</option>
                <option value="لا تعمل">لا تعمل</option>
                <option value="جزئي">جزئي</option>
              </select>
            </div>
            <div class="field">
              <label>تخزين التسجيل</label>
              <input type="text" name="cam2_storage" placeholder="مثال: DVR / Cloud" />
            </div>
            <div class="field">
              <label>درجة الاستعجال</label>
              <select name="cam2_urgency">
                <option value="">-- اختر --</option>
                <option value="عاجل">عاجل</option>
                <option value="متوسط">متوسط</option>
                <option value="غير عاجل">غير عاجل</option>
              </select>
            </div>
            <div class="field">
              <label>العدد المطلوب</label>
              <input type="number" name="cam2_count_needed" placeholder="0" />
            </div>
          </div>
          <div class="field">
            <label>الإجراء التصحيحي</label>
            <textarea name="cam2_action" placeholder="اكتب الإجراء المطلوب..."></textarea>
          </div>
          <div class="field">
            <label>ملاحظات</label>
            <textarea name="cam2_notes" placeholder="أي ملاحظات إضافية..."></textarea>
          </div>
        </div>
      </div>

      <!-- Submit -->
      <div class="submit-area">
        <button type="submit" class="btn-submit" id="submitBtn">
          📤 إرسال الاستمارة
        </button>
        <div id="status" class="status"></div>
      </div>
    </form>

    <div class="footer">
      <p>📊 البيانات تُحفظ تلقائياً في قاعدة البيانات المركزية</p>
      <p style="margin-top:5px;font-size:0.75rem">© 2026 - مستشفى الأورام - إدارة الصيدلة</p>
    </div>
  </div>

  <script>
    // ====== CONFIG: ضع هنا رابط Google Apps Script Web App ======
    const SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbxeIm2kyczKvWdcwIutdJAanm-kPsQvsZBNNCeyYFVL6wjzguczC0k-19jJ1s3zWhQQ/exec';
    // ===========================================================

    const form = document.getElementById('auditForm');
    const submitBtn = document.getElementById('submitBtn');
    const status = document.getElementById('status');
    const progressFill = document.getElementById('progressFill');
    const progressText = document.getElementById('progressText');

    // Progress tracking
    form.addEventListener('input', updateProgress);
    form.addEventListener('change', updateProgress);

    function updateProgress() {
      const total = form.querySelectorAll('input, select, textarea').length;
      const filled = Array.from(form.querySelectorAll('input, select, textarea')).filter(el => {
        if (el.type === 'radio') {
          return form.querySelector(`input[name="${el.name}"]:checked`) !== null;
        }
        return el.value.trim() !== '';
      }).length;
      const pct = Math.round((filled / total) * 100);
      progressFill.style.width = pct + '%';
      progressText.textContent = pct + '%';
    }

    // Submit
    form.addEventListener('submit', async (e) => {
      e.preventDefault();

      const pharmacy = document.getElementById('pharmacy_name').value;
      const date = document.getElementById('date').value;
      const officer = document.getElementById('officer').value;

      if (!pharmacy || !date || !officer) {
        showStatus('من فضلك املأ البيانات الأساسية (اسم الصيدلية، التاريخ، المسئول)', 'error');
        return;
      }

      // Collect form data
      const formData = new FormData(form);
      const data = {};
      for (let [key, value] of formData.entries()) {
        if (data[key] !== undefined) {
          if (!Array.isArray(data[key])) data[key] = [data[key]];
          data[key].push(value);
        } else {
          data[key] = value;
        }
      }
      data.timestamp = new Date().toISOString();

      submitBtn.disabled = true;
      showStatus('⏳ جاري الإرسال...', 'loading');

      try {
        if (SCRIPT_URL === 'PLACEHOLDER_APPS_SCRIPT_URL') {
          // Local test mode - save to console and show success
          console.log('بيانات الاستمارة:', data);
          // Save to localStorage for backup
          const all = JSON.parse(localStorage.getItem('pharmacy_submissions') || '[]');
          all.push(data);
          localStorage.setItem('pharmacy_submissions', JSON.stringify(all));
          await new Promise(r => setTimeout(r, 800));
          showStatus('✅ تم حفظ الاستمارة بنجاح! (وضع الاختبار المحلي - لم يتم النشر على Google Sheets بعد)', 'success');
          form.reset();
          updateProgress();
        } else {
          // Send to Google Apps Script
          await fetch(SCRIPT_URL, {
            method: 'POST',
            mode: 'no-cors',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(data)
          });
          showStatus('✅ تم إرسال الاستمارة بنجاح! شكراً لك', 'success');
          form.reset();
          updateProgress();
        }
      } catch (err) {
        console.error(err);
        showStatus('❌ حدث خطأ في الإرسال. حاول مرة أخرى.', 'error');
      } finally {
        submitBtn.disabled = false;
        setTimeout(() => { status.className = 'status'; }, 5000);
      }
    });

    function showStatus(msg, type) {
      status.textContent = msg;
      status.className = 'status ' + type;
    }

    // Set today's date
    document.getElementById('date').valueAsDate = new Date();
    updateProgress();
  </script>
</body>
</html>
