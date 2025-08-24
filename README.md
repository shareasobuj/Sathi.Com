 Sathi.Com
<html lang="bn">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Sathi.com</title>
  <meta name="description" content="একটি সম্পূর্ণ ফ্রন্টএন্ড ই-কমার্স সাইট: সাইনআপ/লগইন, প্রডাক্ট, কার্ট, চেকআউট, অর্ডার হিস্ট্রি, অ্যাডমিন প্যানেল — সব এক ফাইলে।"/>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0b0f14; --card:#121822; --muted:#778; --text:#e7ecf3; --brand:#22c55e; --brand-2:#10b981; --accent:#60a5fa; --danger:#ef4444; --warn:#f59e0b;
      --ring: 0 0 0 3px rgba(34,197,94,.35);
    }
    *{box-sizing:border-box}
    html,body{margin:0;font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial,"Noto Sans","Apple Color Emoji","Segoe UI Emoji";background:linear-gradient(120deg,orchid 0%,#0f172a 80%);color:var(--text)}
    a{color:inherit;text-decoration:none}
    img{max-width:100%;display:block}
    .container{max-width:1200px;margin:0 auto;padding:24px}
    .btn{display:inline-flex;align-items:center;gap:8px;border:0;border-radius:14px;padding:12px 16px;background:var(--brand);color:#04110a;font-weight:700;cursor:pointer;transition:.2s box-shadow,.2s transform}
    .btn:hover{box-shadow:var(--ring);transform:translateY(-1px)}
    .btn.ghost{background:transparent;color:var(--text);border:1px solid #243245}
    .btn.muted{background:#1f2937;color:#cbd5e1}
    .btn.danger{background:var(--danger);color:#fff}
    .btn.warn{background:var(--warn);color:#04110a}
    .input,select,textarea{width:100%;padding:12px 14px;border-radius:12px;border:1px solid #2a384f;background:#0f1520;color:var(--text);outline:none}
    .input:focus,select:focus,textarea:focus{box-shadow:var(--ring);border-color:#284}
    .grid{display:grid;gap:20px}
    .grid.cols-2{grid-template-columns:repeat(2,minmax(0,1fr))}
    .grid.cols-3{grid-template-columns:repeat(3,minmax(0,1fr))}
    .grid.cols-4{grid-template-columns:repeat(4,minmax(0,1fr))}
    @media(max-width:1024px){.grid.cols-4{grid-template-columns:repeat(3,1fr)}}
    @media(max-width:768px){.grid.cols-3,.grid.cols-4,.grid.cols-2{grid-template-columns:1fr}}
    .card{background:rgba(18,24,34,.85);backdrop-filter:blur(8px);border:1px solid #1e2a3f;border-radius:18px;padding:18px}
    header.nav{position:sticky;top:0;z-index:50;background:rgba(11,15,20,.8);backdrop-filter:blur(10px);border-bottom:1px solid #1e2a3f}
    .brand{display:flex;align-items:center;gap:10px;font-weight:900;letter-spacing:.2px}
    .brand .logo{width:34px;height:34px;border-radius:10px;background:conic-gradient(from 120deg,var(--brand),#34d399,var(--accent));display:grid;place-content:center;color:#08130c;font-weight:900}
    .nav-links{display:flex;gap:10px;flex-wrap:wrap}
    .nav-links .btn{padding:10px 12px;border-radius:12px}
    .hero{padding:40px 0}
    .hero-wrap{display:grid;grid-template-columns:1.1fr .9fr;gap:24px;align-items:center}
    @media(max-width:900px){.hero-wrap{grid-template-columns:1fr}}
    .hero h1{font-size:44px;line-height:1.1;margin:0 0 12px}
    .hero p{color:#b6c3d6}
    .pill{display:inline-flex;gap:8px;align-items:center;background:#112033;border:1px solid #1f324e;color:#c7d2fe;padding:6px 10px;border-radius:999px;font-size:12px}
    .badge{font-size:12px;padding:4px 8px;border-radius:10px;background:#142033;border:1px solid #24324b;color:#a5b4fc}
    .price{font-weight:800;font-size:18px}
    .strike{color:#7f8ea8;text-decoration:line-through;margin-left:6px;font-size:13px}
    .product{display:flex;flex-direction:column;gap:10px}
    .product .thumb{position:relative;border-radius:16px;overflow:hidden;background:#0b1220;height:190px;border:1px solid #1e2a3f}
    .product .thumb .tag{position:absolute;top:10px;left:10px}
    .product .thumb .img{width:100%;height:100%;object-fit:cover}
    .qty{display:flex;align-items:center;gap:8px}
    .qty button{width:32px;height:32px;border-radius:10px;border:1px solid #2a384f;background:#0f1520;color:#d1e0ee}
    .toolbar{display:flex;gap:10px;flex-wrap:wrap}
    .flex{display:flex;gap:12px;align-items:center}
    .spacer{flex:1}
    .hidden{display:none !important}
    .tabs{display:flex;gap:6px;flex-wrap:wrap}
    .tab{padding:8px 12px;border-radius:12px;border:1px solid #273449;background:#0f1623;color:#cbd5e1;cursor:pointer}
    .tab.active{background:var(--brand);color:#04110a;border-color:#2a7}
    .table{width:100%;border-collapse:collapse}
    .table th,.table td{padding:12px 10px;border-bottom:1px solid #223148;text-align:left}
    .kpi{display:grid;grid-template-columns:repeat(4,1fr);gap:12px}
    @media(max-width:900px){.kpi{grid-template-columns:1fr 1fr}}
    .kpi .box{background:#0f1623;border:1px solid #223148;border-radius:16px;padding:16px}
    .snackbar{position:fixed;bottom:20px;left:50%;transform:translateX(-50%);background:#101b2a;border:1px solid #264062;color:#e6f0ff;padding:12px 16px;border-radius:12px;box-shadow:0 10px 30px rgba(0,0,0,.45);opacity:0;pointer-events:none;transition:.3s}
    .snackbar.show{opacity:1;pointer-events:auto}
    footer{margin-top:40px;border-top:1px solid #1e2a3f;color:#94a3b8}
    .footer-grid{display:grid;grid-template-columns:2fr 1fr 1fr;gap:20px;padding:24px 0}
    @media(max-width:900px){.footer-grid{grid-template-columns:1fr}}
  </style>
</head>
<body>
  <header class="nav">
    <div class="container" style="display:flex;align-items:center;gap:14px;flex-wrap:wrap">
      <div class="brand">
        <div class="logo">S</div>
        <div>Sathi<span style="color:var(--brand)">.com</span></div>
      </div>
      <div class="spacer"></div>
      <div class="nav-links">
        <button class="btn ghost" data-route="home">হোম</button>
        <button class="btn ghost" data-route="shop">শপ</button>
        <button class="btn ghost" data-route="cart">কার্ট</button>
        <button class="btn ghost" data-route="orders">অর্ডার</button>
        <button class="btn ghost" data-route="admin">অ্যাডমিন</button>
        <span id="authArea"></span>
      </div>
    </div>
  </header>

  <main class="container">
    <!-- HERO / HOME -->
    <section id="view-home" class="hero">
      <div class="hero-wrap">
        <div>
          <span class="pill">⚡ দ্রুত • নিরাপদ • রেসপন্সিভ</span>
          <h1>সাথী.কম <span style="color:var(--brand)">ই-কমার্স</span> সলিউশন</h1>
          <p> অর্ডার করার জন্য সাইনআপ অথবা লগইন করুন , ধন্যবাদ । </p>
          <div style="margin-top:14px" class="toolbar">
            <button class="btn" data-route="shop">এখনই কেনাকাটা করুন</button>
            <button class="btn ghost" data-route="admin">প্রডাক্ট যোগ করুন</button>
          </div>
          <div style="margin-top:14px;display:flex;gap:10px;flex-wrap:wrap">
            <span class="badge">কোনও ব্যাকএন্ড ছাড়াই লোকালস্টোরেজ</span>
            <span class="badge">🔍 সার্চ/ফিল্টার</span>
            <span class="badge">🛒 কার্ট ও চেকআউট</span>
            <span class="badge">📦 অর্ডার হিস্ট্রি</span>
            <span class="badge">📄 CSV ডাউনলোড</span>
          </div>
        </div>
        <div>
          <div class="card">
            <div class="kpi">
              <div class="box"><div style="color:#9fb5cc">মোট প্রডাক্ট</div><div id="kpi-products" style="font-size:28px;font-weight:800">0</div></div>
              <div class="box"><div style="color:#9fb5cc">মোট অর্ডার</div><div id="kpi-orders" style="font-size:28px;font-weight:800">0</div></div>
              <div class="box"><div style="color:#9fb5cc">কার্ট আইটেম</div><div id="kpi-cart" style="font-size:28px;font-weight:800">0</div></div>
              <div class="box"><div style="color:#9fb5cc">লগইন ইউজার</div><div id="kpi-user" style="font-size:28px;font-weight:800">—</div></div>
            </div>
          </div>
          <div style="margin-top:12px" class="card">
            <h3 style="margin-top:0">দ্রুত স্টোর সেটআপ</h3>
            <ol style="line-height:1.9;color:#bcd">
              <li>Sign Up করে লগইন করুন</li>
              <li>Admin ট্যাবে প্রডাক্ট যোগ করুন</li>
              <li>Shop থেকে কার্টে যোগ করে Checkout</li>
              <li>Orders পেজ থেকে CSV এক্সপোর্ট করুন</li>
            </ol>
          </div>
        </div>
      </div>
    </section>

    <!-- AUTH -->
    <section id="view-auth" class="card hidden">
      <div class="tabs" style="margin-bottom:12px">
        <button class="tab active" data-auth-tab="login">লগইন</button>
        <button class="tab" data-auth-tab="signup">সাইনআপ</button>
      </div>
      <div id="auth-login">
        <div class="grid cols-2">
          <div>
            <label>ইমেইল</label>
            <input id="login-email" class="input" type="email" placeholder="you@example.com"/>
          </div>
          <div>
            <label>পাসওয়ার্ড</label>
            <input id="login-pass" class="input" type="password" placeholder="••••••••"/>
          </div>
        </div>
        <div style="margin-top:12px" class="toolbar">
          <button class="btn" id="btn-login">লগইন</button>
          <button class="btn muted" data-auth-tab="signup">একাউন্ট নেই? সাইনআপ</button>
        </div>
      </div>
      <div id="auth-signup" class="hidden">
        <div class="grid cols-2">
          <div>
            <label>নাম</label>
            <input id="su-name" class="input" placeholder="আপনার নাম"/>
          </div>
          <div>
            <label>মোবাইল</label>
            <input id="su-phone" class="input" placeholder="01XXXXXXXXX"/>
          </div>
          <div>
            <label>ইমেইল</label>
            <input id="su-email" class="input" type="email" placeholder="you@example.com"/>
          </div>
          <div>
            <label>পাসওয়ার্ড</label>
            <input id="su-pass" class="input" type="password" placeholder="কমপক্ষে 6 অক্ষর"/>
          </div>
        </div>
        <div style="margin-top:12px" class="toolbar">
          <button class="btn" id="btn-signup">সাইনআপ সম্পন্ন</button>
          <span class="badge">নোট: প্রথম সাইনআপ করা ইউজার স্বয়ংক্রিয়ভাবে অ্যাডমিন</span>
        </div>
      </div>
    </section>

    <!-- SHOP -->
    <section id="view-shop" class="hidden">
      <div class="card">
        <div class="toolbar">
          <input id="q" class="input" placeholder="🔎 প্রডাক্ট সার্চ... (নাম, ক্যাটাগরি)"/>
          <select id="cat">
            <option value="">সব ক্যাটাগরি</option>
          </select>
          <select id="sort">
            <option value="pop">সাজান: জনপ্রিয়</option>
            <option value="lh">দাম: কম থেকে বেশি</option>
            <option value="hl">দাম: বেশি থেকে কম</option>
            <option value="az">A-Z</option>
          </select>
          <div class="spacer"></div>
          <button class="btn" id="btn-reset">রিসেট</button>
        </div>
      </div>
      <div id="shop-grid" class="grid cols-4" style="margin-top:16px"></div>
    </section>

    <!-- CART -->
    <section id="view-cart" class="hidden">
      <div class="grid cols-3">
        <div class="card" style="grid-column:span 2">
          <h3 style="margin-top:0">আপনার কার্ট</h3>
          <table class="table" id="cart-table"></table>
        </div>
        <div class="card">
          <h3 style="margin-top:0">সামারি</h3>
          <div id="cart-summary"></div>
          <div style="margin-top:12px" class="toolbar">
            <button class="btn" id="btn-checkout">চেকআউট</button>
            <button class="btn muted" id="btn-clear-cart">কার্ট ক্লিয়ার</button>
          </div>
        </div>
      </div>
    </section>

    <!-- ORDERS -->
    <section id="view-orders" class="hidden">
      <div class="card">
        <div class="toolbar">
          <h3 style="margin:0">অর্ডার হিস্ট্রি</h3>
          <div class="spacer"></div>
          <button class="btn" id="btn-export-orders">CSV এক্সপোর্ট</button>
        </div>
        <table class="table" id="orders-table"></table>
      </div>
    </section>

    <!-- ADMIN -->
    <section id="view-admin" class="hidden">
      <div class="grid cols-2">
        <div class="card">
          <h3 style="margin-top:0">প্রডাক্ট যোগ/আপডেট</h3>
          <div class="grid cols-2">
            <div>
              <label>প্রডাক্ট নাম</label>
              <input id="p-name" class="input" />
            </div>
            <div>
              <label>ক্যাটাগরি</label>
              <input id="p-cat" class="input" placeholder="ইলেকট্রনিক্স, ফ্যাশন..."/>
            </div>
            <div>
              <label>দাম (৳)</label>
              <input id="p-price" class="input" type="number" min="0" step="0.01" />
            </div>
            <div>
              <label>স্টক</label>
              <input id="p-stock" class="input" type="number" min="0" />
            </div>
            <div style="grid-column:span 2">
              <label>ইমেজ URL (ঐচ্ছিক)</label>
              <input id="p-img" class="input" placeholder="https://..."/>
            </div>
            <div style="grid-column:span 2">
              <label>বিবরণ</label>
              <textarea id="p-desc" class="input" rows="3" placeholder="সংক্ষিপ্ত বিবরণ"></textarea>
            </div>
          </div>
          <div class="toolbar" style="margin-top:12px">
            <button class="btn" id="btn-save-product">সেভ</button>
            <button class="btn muted" id="btn-reset-product">রিসেট</button>
            <span class="badge">সম্পাদনা মোড: <span id="edit-mode">নেই</span></span>
          </div>
        </div>
        <div class="card">
          <h3 style="margin-top:0">সব প্রডাক্ট</h3>
          <table class="table" id="admin-products"></table>
        </div>
      </div>
    </section>
  </main>

  <footer class="container">
    <div class="footer-grid">
      <div>
        <div class="brand" style="margin-bottom:8px"><div class="logo">B</div>Sathi<span style="color:var(--brand)">.com</span></div>
        <p>Thanks for The Visit Sathi.com E-comerce Website</p>
      </div>
      <div>
        <h4>হেল্প</h4>
        <ul style="list-style:none;padding:0;line-height:2">
          <li><a href="#" data-route="auth">লগইন/সাইনআপ</a></li>
          <li><a href="#" data-route="shop">শপ</a></li>
          <li><a href="#" data-route="cart">কার্ট</a></li>
          <li><a href="#" data-route="orders">অর্ডার</a></li>
        </ul>
      </div>
      <div>
        <h4>বৈশিষ্ট্য</h4>
        <ul style="list-style:none;padding:0;line-height:2">
          <li>🔐 অথেন্টিকেশন</li>
          <li>🛍️ প্রডাক্ট CRUD</li>
          <li>🛒 কার্ট/চেকআউট</li>
          <li>📦 অর্ডার হিস্ট্রি</li>
          <li>📄 CSV এক্সপোর্ট</li>
        </ul>
      </div>
    </div>
    <div style="padding:14px 0;color:#738199">© <span id="year"></span> Sathi.com — সব অধিকার সংরক্ষিত</div>
  </footer>

  <div id="snackbar" class="snackbar">Saved</div>

  <script>
  // ===== Utilities =====
  const $ = (q,root=document)=>root.querySelector(q);
  const $$ = (q,root=document)=>Array.from(root.querySelectorAll(q));
  const fmt = n=> new Intl.NumberFormat('bn-BD',{style:'currency',currency:'BDT',maximumFractionDigits:0}).format(n||0).replace('BDT','৳');
  const uid = ()=> Math.random().toString(36).slice(2,9);
  const nowISO = ()=> new Date().toISOString();
  const toast = (msg)=>{ const s=$('#snackbar'); s.textContent=msg; s.classList.add('show'); setTimeout(()=>s.classList.remove('show'),1600); };

  const LS = {
    get(key, def){ try{ return JSON.parse(localStorage.getItem(key)) ?? def }catch{ return def } },
    set(key, val){ localStorage.setItem(key, JSON.stringify(val)); },
    del(key){ localStorage.removeItem(key) }
  };

  // ===== Data Keys =====
  const K = {
    users: 'shop_users',
    current: 'shop_current_user',
    products: 'shop_products',
    orders: (email)=> `shop_orders_${email}`,
    cart: (email)=> `shop_cart_${email}`
  };

  // ===== Seed Data (once) =====
  function seed(){
    if(!LS.get(K.products)){
      const sample=[
        {id:uid(),name:'ওয়্যারলেস ইয়ারবাড',cat:'ইলেকট্রনিক্স',price:1490,stock:50,desc:'ব্লুটুথ 5.3, নোইজ ক্যান্সেল, 24h ব্যাটারি',img:'https://images.unsplash.com/photo-1590658268037-6bf12165a8df?q=80&w=1200&auto=format&fit=crop'},
        {id:uid(),name:'স্মার্ট ঘড়ি',cat:'ইলেকট্রনিক্স',price:2290,stock:32,desc:'হার্ট রেট, SpO2, IP68',img:'https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?q=80&w=1200&auto=format&fit=crop'},
        {id:uid(),name:'ক্যাজুয়াল টি-শার্ট',cat:'ফ্যাশন',price:590,stock:100,desc:'১০০% কটন, কমফোর্ট ফিট',img:'https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?q=80&w=1200&auto=format&fit=crop'},
        {id:uid(),name:'কফি মেকার',cat:'হোম & কিচেন',price:3290,stock:12,desc:'ড্রিপ কফি, অটো-অফ, 1.2L',img:'https://images.unsplash.com/photo-1502462041640-b3d7e50d0660?q=80&w=1200&auto=format&fit=crop'}
      ];
      LS.set(K.products, sample);
    }
    if(!LS.get(K.users)){
      LS.set(K.users, []);
    }
  }

  // ===== Auth =====
  function users(){ return LS.get(K.users,[]) }
  function setUsers(u){ LS.set(K.users,u) }
  function current(){ return LS.get(K.current,null) }
  function setCurrent(u){ LS.set(K.current,u); renderAuthArea(); renderKPIs(); }
  function signup(name,phone,email,pass){
    const list=users();
    if(list.find(u=>u.email===email)) throw new Error('এই ইমেইলে একাউন্ট আছে');
    const role = list.length===0? 'admin' : 'customer';
    const u={id:uid(),name,phone,email,pass,role,joined:nowISO()};
    list.push(u); setUsers(list); setCurrent({email,name,role}); toast('সাইনআপ সম্পন্ন');
  }
  function login(email,pass){
    const u = users().find(u=>u.email===email && u.pass===pass);
    if(!u) throw new Error('ইমেইল/পাসওয়ার্ড মিলেনি');
    setCurrent({email:u.email,name:u.name,role:u.role}); toast('লগইন সফল');
  }
  function logout(){ setCurrent(null); toast('লগআউট'); route('home'); }

  // ===== Products =====
  function allProducts(){ return LS.get(K.products,[]) }
  function setProducts(ps){ LS.set(K.products,ps); renderKPIs(); }
  function upsertProduct(p){
    const list=allProducts();
    const i=list.findIndex(x=>x.id===p.id);
    if(i>-1) list[i]=p; else list.unshift(p);
    setProducts(list); renderShop(); renderAdminTable(); toast('প্রডাক্ট সেভড');
  }
  function deleteProduct(id){
    setProducts(allProducts().filter(p=>p.id!==id)); renderShop(); renderAdminTable(); toast('ডিলিটেড');
  }

  // ===== Cart =====
  function cart(){ const u=current(); if(!u) return []; return LS.get(K.cart(u.email),[]) }
  function setCart(items){ const u=current(); if(!u) return; LS.set(K.cart(u.email),items); renderCart(); renderKPIs(); }
  function addToCart(p,qty=1){
    const items=cart();
    const i=items.findIndex(x=>x.id===p.id);
    if(i>-1) items[i].qty+=qty; else items.push({id:p.id,name:p.name,price:p.price,img:p.img,qty});
    setCart(items); toast('কার্টে যোগ হয়েছে');
  }

  // ===== Orders =====
  function myOrders(){ const u=current(); if(!u) return []; return LS.get(K.orders(u.email),[]) }
  function setOrders(os){ const u=current(); if(!u) return; LS.set(K.orders(u.email),os); renderOrders(); renderKPIs(); }
  function placeOrder(){
    const u=current(); if(!u) return toast('লগইন করুন');
    const items=cart(); if(items.length===0) return toast('কার্ট খালি');
    const total = items.reduce((s,x)=>s+x.price*x.qty,0);
    const order={id:uid(),date:nowISO(),items,total,status:'প্রসেসিং'};
    const os=myOrders(); os.unshift(order); setOrders(os); setCart([]); toast('অর্ডার সম্পন্ন');
  }

  // ===== CSV Export =====
  function toCSV(rows){ return rows.map(r=> r.map(v=>`"${String(v).replace(/"/g,'\"')}"`).join(',')).join('\n') }
  function download(name,content){ const a=document.createElement('a'); a.href=URL.createObjectURL(new Blob([content],{type:'text/csv'})); a.download=name; a.click(); }

  // ===== Routing & Views =====
  function show(id){ $$('#view-home,#view-auth,#view-shop,#view-cart,#view-orders,#view-admin').forEach(el=>el.classList.add('hidden')); $(id).classList.remove('hidden'); }
  function route(name){
    if(name==='auth') show('#view-auth');
    else if(name==='shop'){ show('#view-shop'); renderShop(); }
    else if(name==='cart'){ show('#view-cart'); renderCart(); }
    else if(name==='orders'){ show('#view-orders'); renderOrders(); }
    else if(name==='admin'){ show('#view-admin'); renderAdminTable(); }
    else show('#view-home');
    window.scrollTo({top:0,behavior:'smooth'});
  }

  // ===== Renderers =====
  function renderAuthArea(){
    const a=$('#authArea'); a.innerHTML='';
    const u=current();
    if(u){
      const sp=document.createElement('span');
      sp.innerHTML = `<span class="badge">👤 ${u.name} (${u.role})</span>`;
      const lo=document.createElement('button'); lo.className='btn muted'; lo.textContent='লগআউট'; lo.onclick=logout;
      a.append(sp,lo);
    }else{
      const btn=document.createElement('button'); btn.className='btn'; btn.textContent='লগইন'; btn.dataset.route='auth'; a.append(btn);
    }
  }

  function renderKPIs(){
    $('#kpi-products').textContent = allProducts().length
    $('#kpi-orders').textContent = current()? myOrders().length : 0
    $('#kpi-cart').textContent = current()? cart().reduce((s,x)=>s+x.qty,0) : 0
    $('#kpi-user').textContent = current()? current().name : '—'
  }

  function renderShop(){
    const grid=$('#shop-grid'); grid.innerHTML='';
    const q=$('#q').value.trim().toLowerCase();
    const cat=$('#cat').value; const sort=$('#sort').value;
    let list=[...allProducts()];
    if(q) list=list.filter(p=> (p.name+p.cat).toLowerCase().includes(q));
    if(cat) list=list.filter(p=> p.cat===cat);
    if(sort==='lh') list.sort((a,b)=>a.price-b.price);
    else if(sort==='hl') list.sort((a,b)=>b.price-a.price);
    else if(sort==='az') list.sort((a,b)=> a.name.localeCompare(b.name,'bn'));
    list.forEach(p=>{
      const card=document.createElement('div'); card.className='product card';
      card.innerHTML=`
        <div class="thumb">
          <span class="badge tag">${p.cat}</span>
          <img class="img" src="${p.img||'https://picsum.photos/seed/'+p.id+'/600/400'}" alt="${p.name}"/>
        </div>
        <div style="display:flex;align-items:start;gap:8px">
          <div style="font-weight:700;font-size:16px">${p.name}</div>
          <div class="spacer"></div>
          <div class="price">${fmt(p.price)}</div>
        </div>
        <div style="color:#9fb5cc">${p.desc||''}</div>
        <div class="toolbar">
          <button class="btn" data-add="${p.id}">কার্টে যোগ</button>
          <button class="btn muted" data-detail="${p.id}">বিস্তারিত</button>
        </div>
      `;
      grid.append(card);
    });

    // Categories
    const cats=[...new Set(allProducts().map(p=>p.cat))];
    const sel=$('#cat'); sel.innerHTML='<option value="">সব ক্যাটাগরি</option>'+cats.map(c=>`<option>${c}</option>`).join('');

    // Events
    $$('[data-add]').forEach(b=> b.onclick=()=> addToCart(allProducts().find(p=>p.id===b.dataset.add)) );
    $$('[data-detail]').forEach(b=> b.onclick=()=> alertDetail(b.dataset.detail));
  }

  function alertDetail(id){
    const p=allProducts().find(x=>x.id===id); if(!p) return;
    alert(`${p.name}\nক্যাটাগরি: ${p.cat}\nদাম: ${fmt(p.price)}\nস্টক: ${p.stock}\n\n${p.desc||''}`);
  }

  function renderCart(){
    const table=$('#cart-table'); const items=cart();
    if(!current()){ table.innerHTML='<tr><td>লগইন করুন</td></tr>'; $('#cart-summary').innerHTML=''; return; }
    if(items.length===0){ table.innerHTML='<tr><td>কার্ট খালি</td></tr>'; $('#cart-summary').innerHTML=''; return; }
    const rows=items.map(it=>`
      <tr>
        <td style="width:60px"><img src="${it.img}" style="width:60px;height:60px;object-fit:cover;border-radius:10px;border:1px solid #223148"/></td>
        <td>${it.name}</td>
        <td>${fmt(it.price)}</td>
        <td>
          <div class="qty">
            <button data-dec="${it.id}">−</button>
            <div>${it.qty}</div>
            <button data-inc="${it.id}">+</button>
          </div>
        </td>
        <td>${fmt(it.price*it.qty)}</td>
        <td><button class="btn danger" data-del="${it.id}">রিমুভ</button></td>
      </tr>
    `).join('');
    table.innerHTML = `<tr><th></th><th>প্রডাক্ট</th><th>দাম</th><th>পরিমাণ</th><th>মোট</th><th></th></tr>${rows}`;

    // Summary
    const sub = items.reduce((s,x)=>s+x.price*x.qty,0);
    const ship = sub>3000? 0 : 80;
    const vat = Math.round(sub*0.05);
    const total=sub+ship+vat;
    $('#cart-summary').innerHTML = `
      <div style="display:grid;gap:8px">
        <div class="flex"><div>সাব টোটাল</div><div class="spacer"></div><strong>${fmt(sub)}</strong></div>
        <div class="flex"><div>ভ্যাট (৫%)</div><div class="spacer"></div><strong>${fmt(vat)}</strong></div>
        <div class="flex"><div>শিপিং</div><div class="spacer"></div><strong>${ship?fmt(ship):'ফ্রি'}</strong></div>
        <div class="flex" style="border-top:1px solid #223148;padding-top:8px"><div>সর্বমোট</div><div class="spacer"></div><strong style="font-size:18px">${fmt(total)}</strong></div>
      </div>
    `;

    // Events
    $$('[data-inc]').forEach(b=> b.onclick=()=> qtyChange(b.dataset.inc, +1));
    $$('[data-dec]').forEach(b=> b.onclick=()=> qtyChange(b.dataset.dec, -1));
    $$('[data-del]').forEach(b=> b.onclick=()=> removeFromCart(b.dataset.del));
  }
  function qtyChange(id,delta){ const items=cart(); const i=items.findIndex(x=>x.id===id); if(i>-1){ items[i].qty=Math.max(1,items[i].qty+delta); setCart(items);} }
  function removeFromCart(id){ setCart(cart().filter(x=>x.id!==id)); }

  function renderOrders(){
    const table=$('#orders-table'); const os=myOrders();
    if(!current()){ table.innerHTML='<tr><td>লগইন করুন</td></tr>'; return }
    if(os.length===0){ table.innerHTML='<tr><td>কোন অর্ডার নেই</td></tr>'; return }
    table.innerHTML = `
      <tr><th>অর্ডার আইডি</th><th>তারিখ</th><th>আইটেম</th><th>টোটাল</th><th>স্ট্যাটাস</th></tr>
      ${os.map(o=>`<tr>
        <td>#${o.id}</td>
        <td>${new Date(o.date).toLocaleString('bn-BD')}</td>
        <td>${o.items.map(i=>`${i.name} × ${i.qty}`).join('<br>')}</td>
        <td>${fmt(o.total)}</td>
        <td><span class="badge">${o.status}</span></td>
      </tr>`).join('')}
    `;
  }

  function renderAdminTable(){
    const u=current();
    if(!u || u.role!=='admin'){ $('#view-admin').innerHTML='<div class="card">শুধু অ্যাডমিন প্রবেশ করতে পারবে</div>'; return; }
    const table=$('#admin-products');
    const list=allProducts();
    table.innerHTML = `
      <tr><th>প্রডাক্ট</th><th>ক্যাটাগরি</th><th>দাম</th><th>স্টক</th><th></th></tr>
      ${list.map(p=>`<tr>
        <td>${p.name}</td>
        <td>${p.cat}</td>
        <td>${fmt(p.price)}</td>
        <td>${p.stock}</td>
        <td>
          <button class="btn warn" data-edit="${p.id}">এডিট</button>
          <button class="btn danger" data-delp="${p.id}">ডিলিট</button>
        </td>
      </tr>`).join('')}
    `;
    $$('[data-edit]').forEach(b=> b.onclick=()=> loadProduct(b.dataset.edit));
    $$('[data-delp]').forEach(b=> b.onclick=()=> confirm('ডিলিট করবেন?')&& deleteProduct(b.dataset.delp));
  }

  function loadProduct(id){
    const p=allProducts().find(x=>x.id===id); if(!p) return;
    $('#p-name').value=p.name; $('#p-cat').value=p.cat; $('#p-price').value=p.price; $('#p-stock').value=p.stock; $('#p-img').value=p.img||''; $('#p-desc').value=p.desc||'';
    $('#edit-mode').textContent=p.id; $('#btn-save-product').dataset.id=p.id; route('admin');
  }

  // ===== Event Bindings =====
  function bind(){
    // routing buttons
    $$('[data-route]').forEach(b=> b.onclick=()=> route(b.dataset.route));

    // auth tabs
    $$('[data-auth-tab]').forEach(t=> t.onclick=(e)=>{
      $$('.tab').forEach(x=>x.classList.remove('active')); e.target.classList.add('active');
      const v=t.dataset.authTab; $('#auth-login').classList.toggle('hidden', v!=='login'); $('#auth-signup').classList.toggle('hidden', v!=='signup');
    });

    // auth actions
    $('#btn-signup').onclick=()=>{
      const n=$('#su-name').value.trim(), ph=$('#su-phone').value.trim(), em=$('#su-email').value.trim(), pw=$('#su-pass').value;
      if(n.length<2) return toast('সঠিক নাম দিন'); if(!/^[\w-.]+@([\w-]+\.)+[\w-]{2,4}$/.test(em)) return toast('সঠিক ইমেইল দিন'); if(pw.length<6) return toast('পাসওয়ার্ড কমপক্ষে ৬ অক্ষর');
      try{ signup(n,ph,em,pw); route('shop'); }catch(err){ toast(err.message) }
    };
    $('#btn-login').onclick=()=>{
      try{ login($('#login-email').value.trim(), $('#login-pass').value); route('shop'); }catch(err){ toast(err.message) }
    };

    // shop controls
    ['#q','#cat','#sort'].forEach(s=> $(s).addEventListener('input', renderShop));
    $('#btn-reset').onclick=()=>{ $('#q').value=''; $('#cat').value=''; $('#sort').value='pop'; renderShop(); };

    // cart actions
    $('#btn-checkout').onclick=placeOrder;
    $('#btn-clear-cart').onclick=()=> setCart([]);

    // orders export
    $('#btn-export-orders').onclick=()=>{
      const os=myOrders(); if(os.length===0) return toast('কিছু নেই');
      const rows=[["OrderID","Date","Items","Total(BDT)","Status"]];
      os.forEach(o=> rows.push([o.id,new Date(o.date).toLocaleString(), o.items.map(i=>`${i.name}x${i.qty}`).join('; '), o.total, o.status]));
      download('orders.csv', toCSV(rows));
      toast('CSV ডাউনলোড হয়েছে');
    };

    // admin save/reset
    $('#btn-save-product').onclick=()=>{
      const id=$('#btn-save-product').dataset.id || uid();
      const p={ id, name:$('#p-name').value.trim(), cat:$('#p-cat').value.trim(), price:+$('#p-price').value, stock:+$('#p-stock').value, img:$('#p-img').value.trim(), desc:$('#p-desc').value.trim() };
      if(!p.name||!p.cat||!(p.price>=0)) return toast('ফর্ম পূরণ করুন');
      upsertProduct(p); $('#edit-mode').textContent='নেই'; $('#btn-save-product').dataset.id='';
    };
    $('#btn-reset-product').onclick=()=>{ ['#p-name','#p-cat','#p-price','#p-stock','#p-img','#p-desc'].forEach(s=> $(s).value=''); $('#edit-mode').textContent='নেই'; $('#btn-save-product').dataset.id=''; };

    // keyboard quick nav
    window.addEventListener('keydown',e=>{
      if(e.key==='/' && document.activeElement.tagName!=='INPUT' && document.activeElement.tagName!=='TEXTAREA'){ e.preventDefault(); $('#q').focus(); }
    });
  }

  // ===== Init =====
  function init(){
    seed(); bind(); renderAuthArea(); renderKPIs(); route('home');
    $('#year').textContent=new Date().getFullYear();
  }
  init();
  </script>
