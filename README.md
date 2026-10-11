# Registration-form-
Hostel form
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hostel Admission Portal</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,wght@0,500;0,600;0,700;1,500&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
<style>
  :root{
    --navy:#1B2A4A;
    --cream:#F5F0E6;
    --brick:#B5533C;
    --gold:#C9A227;
    --ink:#2E2E2A;
    --paper:#FBF8F1;
    --line: rgba(27,42,74,0.18);
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  
  body.login-bg {
    font-family:'Inter', sans-serif;
    color:var(--ink);
    min-height:100vh;
    background: linear-gradient(rgba(15, 23, 42, 0.4), rgba(15, 23, 42, 0.6)),
                url('https://images.unsplash.com/photo-1562774053-701939374585?q=80&w=1920&auto=format&fit=crop') no-repeat center center fixed;
    background-size: cover;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:20px;
  }

  body.app-bg {
    font-family:'Inter', sans-serif;
    color:var(--ink);
    min-height:100vh;
    background: var(--navy);
    background-image:
      radial-gradient(circle at 10% 10%, rgba(201,162,39,0.08), transparent 40%),
      radial-gradient(circle at 90% 90%, rgba(181,83,60,0.10), transparent 40%);
    display:flex;
    align-items:flex-start;
    justify-content:center;
    padding:48px 16px 80px;
  }

  .hidden {
    display: none !important;
  }

  .login-wrapper {
    width: 100%;
    max-width: 1100px;
    display: flex;
    justify-content: center;
  }
  .login-card {
    width: 100%;
    max-width: 380px;
    background: rgba(251, 248, 241, 0.95);
    backdrop-filter: blur(8px);
    border-radius: 8px;
    padding: 32px 28px;
    box-shadow: 0 20px 40px rgba(0,0,0,0.4);
    border: 1px solid rgba(255,255,255,0.3);
  }
  .login-header h2 {
    font-family: 'Fraunces', serif;
    font-size: 24px;
    color: var(--navy);
    margin: 0 0 6px;
  }
  .login-header p {
    font-size: 13px;
    color: #5b5b52;
    margin: 0 0 24px;
  }

  .sheet{
    width:100%;
    max-width:720px;
    background:var(--paper);
    border-radius:4px;
    box-shadow:0 30px 60px rgba(0,0,0,0.35);
    position:relative;
    overflow:hidden;
  }

  .sheet::before{
    content:"";
    position:absolute;
    top:0; left:0; right:0;
    height:10px;
    background-image: radial-gradient(circle, var(--navy) 3px, transparent 3.5px);
    background-size: 20px 20px;
    background-position: 8px -6px;
    background-color: var(--paper);
  }

  header.form-head{
    padding:44px 48px 28px;
    border-bottom:2px solid var(--navy);
    display:flex;
    justify-content:space-between;
    align-items:flex-end;
    gap:20px;
  }

  .brand-block .eyebrow{
    font-family:'JetBrains Mono', monospace;
    font-size:11px;
    letter-spacing:0.14em;
    text-transform:uppercase;
    color:var(--brick);
    margin:0 0 10px;
  }

  .brand-block h1{
    font-family:'Fraunces', serif;
    font-weight:700;
    font-size:32px;
    line-height:1.05;
    margin:0 0 8px;
    color:var(--navy);
  }

  .brand-block p{
    margin:0;
    font-size:14px;
    color:#5b5b52;
  }

  .stamp{
    font-family:'JetBrains Mono', monospace;
    font-size:11px;
    text-align:right;
    color:var(--navy);
    border:1.5px solid var(--navy);
    border-radius:3px;
    padding:10px 14px;
    transform:rotate(-3deg);
    white-space:nowrap;
  }
  .stamp span{display:block; color:var(--brick); font-weight:600; letter-spacing:0.05em;}

  form.app-form{padding:36px 48px 48px;}

  .section-label{
    font-family:'JetBrains Mono', monospace;
    font-size:11px;
    letter-spacing:0.12em;
    text-transform:uppercase;
    color:var(--navy);
    display:flex;
    align-items:center;
    gap:10px;
    margin:34px 0 18px;
  }
  .section-label:first-of-type{margin-top:0;}
  .section-label::after{
    content:"";
    flex:1;
    height:1px;
    background:var(--line);
  }

  .grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:18px 20px;
  }

  .field{display:flex; flex-direction:column; gap:6px;}
  .field.span-2{grid-column:1 / -1;}

  label{
    font-size:12.5px;
    font-weight:600;
    color:var(--navy);
  }
  label .req{color:var(--brick); margin-left:2px;}

  input, select, textarea{
    font-family:'Inter', sans-serif;
    font-size:14.5px;
    color:var(--ink);
    background:#fff;
    border:1.5px solid var(--line);
    border-radius:3px;
    padding:10px 12px;
    outline:none;
    transition:border-color .15s ease, box-shadow .15s ease;
  }
  input:focus, select:focus, textarea:focus{
    border-color:var(--navy);
    box-shadow:0 0 0 3px rgba(27,42,74,0.10);
  }
  
  .error-msg {
    color: var(--brick);
    font-size: 11.5px;
    font-weight: 500;
    display: none;
    font-family: 'JetBrains Mono', monospace;
  }
  .input-error {
    border-color: var(--brick) !important;
  }

  textarea{resize:vertical; min-height:70px;}

  fieldset{
    border:1.5px solid var(--line);
    border-radius:4px;
    padding:14px 16px;
    margin:0;
  }
  fieldset legend{
    font-size:12.5px;
    font-weight:600;
    color:var(--navy);
    padding:0 6px;
  }
  .radio-row{display:flex; flex-wrap:wrap; gap:16px; margin-top:4px;}
  .radio-row label{
    display:flex; align-items:center; gap:6px;
    font-weight:500; font-size:14px; color:var(--ink);
    cursor:pointer;
  }
  .radio-row input{width:auto; padding:0; cursor:pointer;}

  .declaration{
    margin-top:32px;
    padding:16px 18px;
    background:rgba(27,42,74,0.045);
    border-left:3px solid var(--gold);
    border-radius:0 4px 4px 0;
    font-size:13px;
    color:#4a4a42;
    display:flex;
    gap:10px;
    align-items:flex-start;
    cursor:pointer;
  }
  .declaration input{margin-top:3px; width:auto; cursor:pointer;}

  .actions{
    margin-top:32px;
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:16px;
    flex-wrap:wrap;
  }

  .hint{font-size:12px; color:#8a8a7d; font-family:'JetBrains Mono', monospace;}

  button.submit, .btn-login{
    font-family:'Inter', sans-serif;
    font-weight:700;
    font-size:14.5px;
    letter-spacing:0.02em;
    color:var(--cream);
    background:var(--navy);
    border:none;
    border-radius:3px;
    padding:12px 30px;
    cursor:pointer;
    transition:transform .12s ease, background .15s ease, box-shadow .15s ease;
    box-shadow:0 6px 0 var(--brick);
    width: 100%;
  }
  button.submit:hover, .btn-login:hover { background: #233657; }
  button.submit:active, .btn-login:active { transform: translateY(4px); box-shadow: 0 2px 0 var(--brick); }
  
  button.submit { width: auto; }

  .success{
    display:none;
    margin-top:28px;
    padding:20px 22px;
    background:#1B2A4A;
    color:#fff;
    border-radius:4px;
    font-family:'JetBrains Mono', monospace;
    font-size:13px;
    line-height:1.7;
  }
  .success.visible{display:block;}
  .success b{color:var(--gold);}

  @media (max-width:640px){
    .grid{grid-template-columns:1fr;}
    header.form-head{flex-direction:column; align-items:flex-start;}
    form.app-form{padding:28px 24px 36px;}
    header.form-head{padding:32px 24px 22px;}
  }
</style>
</head>
<body class="login-bg" id="pageBody">

<!-- LOGIN SECTION -->
<div class="login-wrapper" id="loginWrapper">
  <div class="login-card">
    <div class="login-header">
      <h2>Hostel Portal Login</h2>
      <p>Enter your credentials to access the registration form.</p>
    </div>
    <form id="loginForm" onsubmit="handleLogin(event)">
      <div class="field" style="margin-bottom: 16px;">
        <label for="loginUserId">User ID (25ucs501 – 25ucs565)</label>
        <input type="text" id="loginUserId" placeholder="e.g. 25ucs501" required>
      </div>
      <div class="field" style="margin-bottom: 16px;">
        <label for="loginPassword">Password</label>
        <input type="password" id="loginPassword" placeholder="••••••••" required>
      </div>
      <div id="loginErrorMsg" class="error-msg" style="margin-bottom: 10px;">Invalid User ID or Password.</div>
      <button type="submit" class="btn-login">Sign In</button>
    </form>
  </div>
</div>

<!-- APPLICATION FORM SECTION -->
<div class="sheet hidden" id="applicationSheet">
  <header class="form-head">
    <div class="brand-block">
      <p class="eyebrow">Office of Student Housing</p>
      <h1>Hostel Admission<br>Application</h1>
      <p>Academic Year 2026–27 · Complete all required fields marked with *</p>
    </div>
    <div class="stamp">FORM NO.<span id="formNo">HST-202650</span></div>
  </header>

  <form class="app-form" id="hostelForm" novalidate>

    <p class="section-label">Applicant details</p>
    <div class="grid">
      <div class="field span-2">
        <label>Full name <span class="req">*</span></label>
        <input type="text" id="fullName" name="fullName" placeholder="Letters and dots only (No numbers)" required>
        <span class="error-msg" id="err-fullName">Numbers and special characters (except dot) are not allowed.</span>
      </div>
      <div class="field">
        <label>Roll / registration no. <span class="req">*</span></label>
        <input type="text" id="rollNo" name="rollNo" readonly style="background:#f0ebd8; cursor:not-allowed;">
      </div>
      <div class="field">
        <label>Date of birth <span class="req">*</span></label>
        <input type="date" id="dob" name="dob" required>
        <span class="error-msg" id="err-dob">This field is required.</span>
      </div>
      <div class="field">
        <label>Course / branch <span class="req">*</span></label>
        <input type="text" id="course" name="course" placeholder="e.g. B.Tech CSE" required>
        <span class="error-msg" id="err-course">This field is required.</span>
      </div>
      <div class="field">
        <label>Year of study <span class="req">*</span></label>
        <select id="year" name="year" required>
          <option value="" disabled selected>Select year</option>
          <option value="1st Year">1st Year</option>
          <option value="2nd Year">2nd Year</option>
          <option value="3rd Year">3rd Year</option>
          <option value="4th Year">4th Year</option>
          <option value="Postgraduate">Postgraduate</option>
        </select>
        <span class="error-msg" id="err-year">This field is required.</span>
      </div>
    </div>

    <p class="section-label">Contact information</p>
    <div class="grid">
      <div class="field">
        <label>Mobile number <span class="req">*</span></label>
        <input type="text" id="mobile" name="mobile" placeholder="10-digit mobile number" required>
        <span class="error-msg" id="err-mobile">Mobile number must be exactly 10 digits.</span>
      </div>
      <div class="field">
        <label>Email address <span class="req">*</span></label>
        <input type="email" id="email" name="email" placeholder="username@gmail.com" required>
        <span class="error-msg" id="err-email">This field is required.</span>
      </div>
      <div class="field span-2">
        <label>Permanent address (Max 50 chars) <span class="req">*</span></label>
        <textarea id="address" name="address" maxlength="50" placeholder="House no., street, city (Max 50 characters)" required></textarea>
        <span class="error-msg" id="err-address">Maximum 50 characters allowed.</span>
      </div>
      <div class="field">
        <label>Parent / guardian name <span class="req">*</span></label>
        <input type="text" id="guardianName" name="guardianName" placeholder="Letters and dots only (No numbers)" required>
        <span class="error-msg" id="err-guardianName">Numbers and special characters (except dot) are not allowed.</span>
      </div>
      <div class="field">
        <label>Guardian contact number <span class="req">*</span></label>
        <input type="text" id="guardianMobile" name="guardianMobile" placeholder="10-digit mobile number" required>
        <span class="error-msg" id="err-guardianMobile">Must be exactly 10 digits.</span>
      </div>
    </div>

    <p class="section-label">Accommodation preference</p>
    <div class="grid">
      <fieldset id="fs-roomType">
        <legend>Room type <span class="req">*</span></legend>
        <div class="radio-row">
          <label><input type="radio" name="roomType" value="Single" required> Single</label>
          <label><input type="radio" name="roomType" value="Double sharing"> Double sharing</label>
          <label><input type="radio" name="roomType" value="Triple sharing"> Triple sharing</label>
        </div>
      </fieldset>
      <fieldset id="fs-mess">
        <legend>Mess plan <span class="req">*</span></legend>
        <div class="radio-row">
          <label><input type="radio" name="mess" value="Veg" required> Vegetarian</label>
          <label><input type="radio" name="mess" value="Non-veg"> Non-vegetarian</label>
        </div>
      </fieldset>
      <div class="field span-2">
        <label>Medical conditions (Max 70 chars) <span class="req">*</span></label>
        <textarea id="medical" name="medical" maxlength="70" placeholder="Type 'None' or 'No' if not applicable" required></textarea>
        <span class="error-msg" id="err-medical">Maximum 70 characters allowed.</span>
      </div>
    </div>

    <label class="declaration">
      <input type="checkbox" id="declaration" name="declaration" required>
      <span>I declare that the information provided above is true to the best of my knowledge.</span>
    </label>

    <div class="actions">
      <span class="hint" id="statusHint">All required fields must be completed.</span>
      <button type="submit" class="submit">Submit application</button>
    </div>

    <div class="success" id="successBox">
      <div>&#10003; <b>Application received successfully.</b></div>
    </div>
  </form>
</div>

<script>
  // Login Handler
  function handleLogin(e) {
    e.preventDefault();
    const userIdInput = document.getElementById('loginUserId').value.trim().toLowerCase();
    const passwordInput = document.getElementById('loginPassword').value.trim();
    const errorMsg = document.getElementById('loginErrorMsg');

    const match = userIdInput.match(/^25ucs5(\d{2})$/);
    let isValidUser = false;

    if (match) {
      const num = parseInt(match[1], 10);
      if (num >= 1 && num <= 65) {
        isValidUser = true;
      }
    }

    if (isValidUser && passwordInput === "12345678") {
      const bodyTag = document.getElementById('pageBody');
      bodyTag.classList.remove('login-bg');
      bodyTag.classList.add('app-bg');

      document.getElementById('loginWrapper').classList.add('hidden');
      document.getElementById('applicationSheet').classList.remove('hidden');
      
      document.getElementById('rollNo').value = userIdInput.toUpperCase();
    } else {
      errorMsg.style.display = 'block';
      if (!isValidUser && passwordInput !== "12345678") {
        errorMsg.textContent = 'Invalid User ID and Password.';
      } else if (!isValidUser) {
        errorMsg.textContent = 'User ID must be between 25ucs501 and 25ucs565.';
      } else {
        errorMsg.textContent = 'Incorrect Password.';
      }
    }
  }

  // Field Restrictions Logic (Names: No Numbers allowed, Dots & Letters allowed)
  function enforceRestriction(id, type, maxLength, errorId) {
    const el = document.getElementById(id);
    const err = document.getElementById(errorId);

    if(!el) return;

    el.addEventListener('input', function() {
      let val = this.value;

      if (type === 'name') {
        // எண்கள் (0-9) அல்லது அனுமதிக்கப்படாத ஸ்பெஷல் கேரக்டர்கள் உள்ளதா என சோதித்தல்
        if (/[0-9]/.test(val)) {
          err.textContent = "Numbers are not allowed in names.";
          err.style.display = 'block';
          this.classList.add('input-error');
        } else if (/[^A-Za-z\.\s]/.test(val)) {
          err.textContent = "Special characters (except dot) are not allowed.";
          err.style.display = 'block';
          this.classList.add('input-error');
        } else {
          err.style.display = 'none';
          this.classList.remove('input-error');
        }
      }

      if (type === 'phone') {
        if (/[^0-9]/.test(val)) {
          val = val.replace(/[^0-9]/g, '');
          this.value = val;
        }
        if (val.length > 10) {
          this.value = val.slice(0, 10);
        }
        if (val.length !== 10 && val.length > 0) {
          err.style.display = 'block';
          this.classList.add('input-error');
        } else {
          err.style.display = 'none';
          this.classList.remove('input-error');
        }
      }

      if (type === 'text' && maxLength) {
        if (val.length >= maxLength) {
          err.style.display = 'block';
          this.classList.add('input-error');
        } else {
          err.style.display = 'none';
          this.classList.remove('input-error');
        }
      }
    });
  }

  // Apply Validations for Names
  enforceRestriction('fullName', 'name', null, 'err-fullName');
  enforceRestriction('guardianName', 'name', null, 'err-guardianName');
  enforceRestriction('mobile', 'phone', 10, 'err-mobile');
  enforceRestriction('guardianMobile', 'phone', 10, 'err-guardianMobile');
  enforceRestriction('address', 'text', 50, 'err-address');
  enforceRestriction('medical', 'text', 70, 'err-medical');

  // Application Form Submit Handler with Empty Validation Check
  document.getElementById('hostelForm').addEventListener('submit', (e) => {
    e.preventDefault();
    const form = e.target;

    // காலியாக உள்ள ஃபீல்டுகளைச் சரிபார்த்தல்
    if (!form.checkValidity()) {
      const invalidElements = form.querySelectorAll(':invalid');
      
      invalidElements.forEach(el => {
        let errorSpan = document.getElementById('err-' + el.id);
        if (!errorSpan && el.parentElement) {
          errorSpan = el.parentElement.querySelector('.error-msg');
        }
        if (errorSpan) {
          if (el.value === "" || !el.value) {
            errorSpan.textContent = "This field is required.";
          }
          errorSpan.style.display = 'block';
          el.classList.add('input-error');
        }
      });

      // முதல் பிழை இருக்கும் இடத்திற்கு ஸ்க்ரோல் செய்தல்
      if (invalidElements.length > 0) {
        invalidElements[0].focus();
        invalidElements[0].scrollIntoView({ behavior: 'smooth', block: 'center' });
      }
      return;
    }

    // அனைத்து விவரங்களும் சரியாக இருந்தால் சக்சஸ் மெசேஜ் காட்டுதல்
    document.getElementById('successBox').classList.add('visible');
    window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' });
  });
</script>

</body>
</html>
