@import url('https://fonts.googleapis.com/css2?family=Barlow+Condensed:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,600;1,700&family=Manrope:wght@400;500;600;700;800&display=swap');
@import "tailwindcss";
@import "tw-animate-css";

@custom-variant dark (&:is(.dark *));

:root { --black:#090909; --near-black:#101010; --panel:#171717; --panel-light:#202020; --red:#e2261d; --red-dark:#a91812; --white:#f7f5f1; --muted:#aaa8a2; --line:rgba(247,245,241,.14); --radius:0px; --background:var(--black); --foreground:var(--white); --card:var(--panel); --card-foreground:var(--white); --primary:var(--red); --primary-foreground:var(--white); --border:rgba(247,245,241,.14); --ring:var(--red); }
* { box-sizing:border-box; }
html { scroll-behavior:smooth; background:var(--black); }
body { margin:0; font-family:"Manrope",sans-serif; background:var(--black); color:var(--white); overflow-x:hidden; }
a { color:inherit; text-decoration:none; }
button { font:inherit; }
.site-shell { min-height:100vh; background:var(--black); overflow:hidden; }
.page-width { width:min(100% - 40px, 1200px); margin:0 auto; }

/* Header */
.site-header { position:fixed; z-index:50; inset:0 0 auto; color:var(--white); transition:background .22s ease, box-shadow .22s ease; }
.site-header.is-scrolled { background:rgba(9,9,9,.96); box-shadow:0 1px 0 var(--line); }
.header-inner { height:76px; width:min(100% - 40px, 1200px); margin:0 auto; display:flex; align-items:center; justify-content:space-between; gap:24px; }
.wordmark { display:inline-flex; align-items:baseline; gap:8px; line-height:1; }
.wordmark-initials { font-family:"Barlow Condensed",sans-serif; font-size:30px; line-height:.8; font-weight:900; letter-spacing:-1.6px; color:var(--white); }
.wordmark-name { font-size:9px; font-weight:800; letter-spacing:2px; color:var(--white); }
.wordmark-fallback { font-family:"Barlow Condensed",sans-serif; font-size:18px; font-weight:800; letter-spacing:.1px; color:var(--white); }
.wordmark-note { font-size:6px; font-weight:800; letter-spacing:.9px; color:#9b9892; }
.official-logo { display:block; max-height:36px; max-width:145px; width:auto; object-fit:contain; object-position:left center; }
.desktop-nav { display:flex; align-items:center; gap:25px; margin-left:auto; }
.desktop-nav a { color:#d2d0cb; text-transform:uppercase; letter-spacing:1.25px; font-size:10px; font-weight:800; transition:color .18s ease; }
.desktop-nav a:hover { color:var(--red); }
.header-actions { display:flex; align-items:center; gap:14px; }
.button { min-height:44px; display:inline-flex; align-items:center; justify-content:center; gap:11px; padding:0 18px; font-size:10px; font-weight:800; letter-spacing:1.1px; text-transform:uppercase; transition:transform .16s cubic-bezier(.23,1,.32,1), background .16s ease, border-color .16s ease; white-space:nowrap; }
.button:active { transform:scale(.97); }
.button-primary { background:var(--red); border:1px solid var(--red); color:var(--white); }
.button-primary:hover { background:#f32b21; border-color:#f32b21; }
.button-outline { background:transparent; color:var(--white); border:1px solid rgba(247,245,241,.48); }
.button-outline:hover { border-color:var(--red); background:var(--red); }
.button-muted { background:rgba(247,245,241,.09); border:1px solid rgba(247,245,241,.18); color:#c2c0bb; cursor:default; }
.header-contact { min-height:39px; padding:0 13px; font-size:9px; }
.menu-toggle { width:42px; height:42px; padding:0; border:1px solid rgba(247,245,241,.22); background:transparent; color:var(--white); display:none; align-items:center; justify-content:center; }
.mobile-nav { background:#0d0d0d; padding:12px 20px 20px; border-top:1px solid var(--line); display:flex; flex-direction:column; }
.mobile-nav a:not(.button) { padding:15px 0; border-bottom:1px solid var(--line); font-family:"Barlow Condensed",sans-serif; font-size:22px; text-transform:uppercase; letter-spacing:.2px; font-weight:700; }
.mobile-direction { margin-top:20px; width:100%; }

/* Hero */
.hero { min-height:740px; height:100svh; position:relative; isolation:isolate; display:flex; align-items:flex-end; background:#111; }
.hero-image { position:absolute; inset:0; background-image:linear-gradient(90deg,rgba(0,0,0,.93) 4%,rgba(0,0,0,.70) 43%,rgba(0,0,0,.18) 100%),linear-gradient(0deg,rgba(9,9,9,.9) 0%,transparent 45%),url('/manus-storage/gb-interior_e85888ad.jpg'); background-size:cover; background-position:72% 48%; filter:grayscale(35%) contrast(1.18) brightness(.72); z-index:-2; }
.hero-noise { position:absolute; inset:0; z-index:-1; opacity:.18; pointer-events:none; background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.6'/%3E%3C/svg%3E"); }
.hero-content { padding-bottom:76px; }
.hero-eyebrow,.section-tag { display:flex; align-items:center; gap:8px; color:#d1cfca; font-size:10px; font-weight:800; letter-spacing:1.3px; text-transform:uppercase; }
.live-dot { width:7px; height:7px; display:inline-block; border-radius:50%; background:var(--red); box-shadow:0 0 0 4px rgba(226,38,29,.18); }
.hero-kicker { margin:22px 0 7px; font-family:"Barlow Condensed",sans-serif; color:var(--red); font-size:17px; line-height:1; font-weight:800; letter-spacing:.6px; text-transform:uppercase; }
h1,h2,h3,p { margin-top:0; }
h1,h2,h3 { font-family:"Barlow Condensed",sans-serif; text-transform:uppercase; }
h1 { max-width:870px; margin-bottom:22px; font-size:clamp(64px,10.8vw,165px); line-height:.76; letter-spacing:-4.5px; font-weight:900; }
h1 span { color:var(--red); }
.hero-bottom { max-width:760px; display:flex; align-items:end; gap:38px; }
.hero-copy { max-width:360px; margin:0; color:#e4e2dd; font-size:14px; line-height:1.65; }
.hero-buttons { display:flex; align-items:center; gap:24px; }
.hero-direction { border-color:var(--red); background:var(--red); }
.text-link { display:flex; align-items:center; gap:8px; color:var(--white); font-size:10px; text-transform:uppercase; letter-spacing:1px; font-weight:800; }
.hero-index { position:absolute; right:max(20px,calc((100vw - 1200px) / 2)); bottom:35px; display:flex; align-items:center; gap:10px; font-size:10px; font-weight:800; letter-spacing:1px; color:rgba(247,245,241,.68); }
.hero-index i { display:block; height:1px; width:55px; background:rgba(247,245,241,.5); }

/* Shared */
.section { padding:118px 0; position:relative; }
.section-heading h2,.copao-info h2,.drinks-copy h2,.spirits-copy h2,.tabacaria-content h2,.convenience-grid h2,.location-copy h2,.contact-strip h2 { margin:12px 0 0; font-size:clamp(48px,6.5vw,88px); line-height:.82; letter-spacing:-2.2px; font-weight:900; }
.section-heading h2 { font-size:clamp(48px,6.1vw,84px); }
.split-heading { display:flex; align-items:end; justify-content:space-between; gap:60px; margin-bottom:54px; }
.section-intro { max-width:270px; margin:0 0 7px; color:var(--muted); font-size:13px; line-height:1.75; }
.large-copy { color:#d7d4cf; max-width:375px; font-size:16px; line-height:1.7; }

/* Quick information */
.quick-bar { background:var(--red); color:var(--white); }
.quick-bar-inner { min-height:90px; display:flex; align-items:center; gap:48px; }
.quick-item { display:flex; align-items:center; gap:12px; font-size:10px; line-height:1.45; letter-spacing:.35px; }
.quick-item svg { flex:0 0 auto; }
.quick-item strong { font-size:11px; font-weight:800; }
.quick-link { margin-left:auto; display:flex; align-items:center; gap:8px; text-transform:uppercase; letter-spacing:1px; font-size:10px; font-weight:800; }

/* Categories */
.categories-section { background:#f4f2ee; color:#101010; }
.categories-section .section-tag { color:#a71d18; }
.categories-section .section-intro { color:#67645f; }
.category-grid { display:grid; grid-template-columns:repeat(3,1fr); border:1px solid #d7d3ca; }
.category-card { min-height:275px; position:relative; overflow:hidden; padding:22px; border-right:1px solid #d7d3ca; border-bottom:1px solid #d7d3ca; background:#eeece6; transition:background .2s ease,color .2s ease; }
.category-card:nth-child(3n) { border-right:0; }
.category-card:nth-last-child(-n+3) { border-bottom:0; }
.category-card::before { content:""; position:absolute; inset:auto -24px -45px auto; width:168px; height:168px; border:1px solid rgba(10,10,10,.13); border-radius:50%; transition:transform .28s cubic-bezier(.23,1,.32,1); }
.category-card::after { content:""; position:absolute; right:25px; bottom:24px; width:22px; height:22px; background:var(--red); transition:transform .28s cubic-bezier(.23,1,.32,1); }
.category-card:hover { background:#171717; color:var(--white); }
.category-card:hover::before { transform:scale(1.5); border-color:rgba(247,245,241,.16); }
.category-card:hover::after { transform:scale(1.5) rotate(45deg); }
.category-number { position:relative; z-index:1; color:#9f9c94; font-size:10px; letter-spacing:1px; font-weight:800; }
.category-card:hover .category-number { color:#c2bfba; }
.category-card-content { position:absolute; z-index:1; left:22px; bottom:22px; max-width:205px; }
.category-card h3 { font-size:29px; margin:0 0 8px; line-height:.9; letter-spacing:-.5px; font-weight:800; }
.category-card p { margin:0; font-size:11px; line-height:1.55; color:#696660; }
.category-card:hover p { color:#c4c1bb; }
.card-arrow { position:absolute; z-index:2; right:23px; top:20px; }

/* Copao */
.copao-section { background:#121212; border-top:1px solid var(--line); }
.copao-layout { display:grid; grid-template-columns:1fr 1.12fr; gap:110px; align-items:center; }
.copao-info h2 em,.contact-strip h2 em { color:var(--red); font-style:normal; }
.copao-note { display:flex; align-items:start; gap:10px; max-width:382px; margin:25px 0 30px; padding-top:17px; border-top:1px solid var(--line); color:#9e9b95; font-size:11px; line-height:1.55; }
.copao-note svg { color:var(--red); flex:none; }
.copao-list-wrap { border-top:1px solid var(--line); }
.list-label { margin:16px 0 0; color:#99968f; font-size:9px; letter-spacing:1.45px; font-weight:800; }
.copao-list { margin:15px 0 0; padding:0; list-style:none; }
.copao-list li { position:relative; display:flex; align-items:center; gap:18px; height:48px; border-bottom:1px solid var(--line); font-family:"Barlow Condensed",sans-serif; font-size:25px; font-weight:700; letter-spacing:.1px; transition:color .18s ease,padding .18s ease; }
.copao-list li span { color:var(--red); font-family:"Manrope",sans-serif; font-size:9px; letter-spacing:1px; font-weight:800; }
.copao-list li i { margin-left:auto; width:0; height:1px; background:var(--red); transition:width .18s ease; }
.copao-list li:hover { padding-left:8px; color:var(--red); }.copao-list li:hover i { width:28px; }
.availability { margin:19px 0 0; color:#a6a29b; font-size:9px; letter-spacing:1.3px; font-weight:800; }

/* Drinks */
.drinks-section { background:#0b0b0b; }
.drinks-layout { display:grid; grid-template-columns:1fr 1fr; min-height:560px; }
.shop-photo { background-size:cover; background-position:center; position:relative; min-height:520px; }
.photo-left { background-image:linear-gradient(0deg,rgba(9,9,9,.35),rgba(9,9,9,.1)),url('/manus-storage/gb-front_dad85524.jpg'); filter:grayscale(20%) contrast(1.05); }
.shop-photo::before { content:""; position:absolute; inset:15px; border:1px solid rgba(247,245,241,.35); }
.photo-label { position:absolute; bottom:31px; left:31px; font-size:9px; letter-spacing:1.1px; font-weight:800; line-height:1.5; text-transform:uppercase; }
.drinks-copy { background:#1a1a1a; display:flex; flex-direction:column; align-items:start; justify-content:center; padding:65px; }
.drinks-copy > p:not(.section-tag) { max-width:350px; margin:20px 0 30px; color:#b8b5af; font-size:14px; line-height:1.7; }
.chip-list { display:flex; flex-wrap:wrap; gap:8px; margin-bottom:33px; max-width:405px; }
.chip-list span,.tabacaria-tags span { border:1px solid rgba(247,245,241,.24); padding:8px 10px; font-size:9px; letter-spacing:.7px; text-transform:uppercase; font-weight:800; }

/* Spirits */
.spirits-section { background:var(--red); color:var(--white); padding:95px 0; }
.spirits-layout { display:grid; grid-template-columns:.7fr 1.3fr; gap:50px; align-items:center; }
.spirits-copy .section-tag { color:rgba(247,245,241,.77); }
.spirits-copy h2 { font-size:clamp(49px,6.4vw,90px); }
.spirits-copy p:not(.section-tag) { max-width:300px; margin:17px 0 0; font-size:13px; line-height:1.65; }
.spirits-cloud { min-height:240px; position:relative; }
.spirit { position:absolute; padding:10px 14px; color:#191919; background:var(--white); font-family:"Barlow Condensed",sans-serif; font-size:26px; line-height:.8; font-weight:800; text-transform:uppercase; box-shadow:6px 6px 0 rgba(0,0,0,.15); }
.spirit-1{left:4%;top:13%;transform:rotate(-4deg)}.spirit-2{left:36%;top:2%;transform:rotate(3deg)}.spirit-3{right:3%;top:17%;transform:rotate(-3deg)}.spirit-4{left:20%;top:45%;transform:rotate(5deg)}.spirit-5{left:51%;top:43%;transform:rotate(-6deg)}.spirit-6{right:8%;bottom:5%;transform:rotate(2deg)}.spirit-7{left:1%;bottom:4%;transform:rotate(-2deg)}

/* Tabacaria */
.tabacaria-section { min-height:600px; display:flex; align-items:center; isolation:isolate; padding:105px 0; }
.tabacaria-image { position:absolute; inset:0; z-index:-2; background:url('/manus-storage/gb-interior_e85888ad.jpg') center/cover; filter:grayscale(100%) contrast(1.25) brightness(.65); }
.tabacaria-overlay { position:absolute; inset:0; z-index:-1; background:linear-gradient(90deg,#090909 0%,rgba(9,9,9,.84) 42%,rgba(9,9,9,.15) 100%); }
.tabacaria-content { max-width:1200px; }
.tabacaria-content > p:not(.section-tag) { max-width:420px; margin:20px 0 29px; color:#d3d0c9; font-size:14px; line-height:1.7; }
.tabacaria-tags { max-width:500px; display:flex; flex-wrap:wrap; gap:8px; }

/* Convenience */
.convenience-section { padding:97px 0; border-bottom:1px solid var(--line); }
.convenience-grid { display:grid; grid-template-columns:1.1fr .85fr .62fr; gap:50px; align-items:end; }
.convenience-grid h2 { font-size:clamp(39px,4.6vw,66px); }
.convenience-list { columns:2; border-left:1px solid var(--line); padding-left:25px; }
.convenience-list span { display:block; margin:0 0 13px; font-family:"Barlow Condensed",sans-serif; color:#e7e4de; text-transform:uppercase; font-weight:700; font-size:23px; line-height:1; }
.convenience-stamp { padding:24px; border:1px solid var(--red); color:#d8d5cf; font-size:11px; line-height:1.6; }
.convenience-stamp svg { color:var(--red); }.convenience-stamp p { margin:12px 0 0; }

/* Contact & map */
.contact-strip { background:#e6e3dc; color:#111; padding:72px 0; }
.contact-strip-inner { display:flex; align-items:end; justify-content:space-between; gap:70px; }
.section-tag-dark { color:#a71d18; }
.contact-strip h2 { font-size:clamp(44px,5.7vw,78px); }
.contact-strip h2 em { color:var(--red); }
.contact-strip-actions { max-width:310px; }.contact-strip-actions p { color:#585550; margin:0 0 23px; font-size:12px; line-height:1.7; }.dark-direction { color:#111; border-color:#111; }.dark-direction:hover{color:#fff;}
.location-section { background:#111; }.location-grid { display:grid; grid-template-columns:.75fr 1.25fr; gap:75px; align-items:center; }.location-name { margin:22px 0 8px; font-family:"Barlow Condensed",sans-serif; color:var(--red); font-size:27px; font-weight:700; text-transform:uppercase; }.location-copy address { font-style:normal; color:#cac7c0; font-size:14px; line-height:1.8; }.hours { display:flex; align-items:center; gap:8px; margin:22px 0 29px; color:#b4b0a9; font-size:11px; }.hours svg{color:var(--red)}.map-card { min-height:430px; position:relative; display:block; overflow:hidden; background:#dedbd3; color:#121212; }.map-grid { position:absolute; inset:0; opacity:.43; background-image:linear-gradient(90deg,transparent 49%,#aaa69c 50%,transparent 51%),linear-gradient(0deg,transparent 49%,#aaa69c 50%,transparent 51%); background-size:58px 58px; }.map-road { position:absolute; background:#faf8f3; box-shadow:0 0 0 1px #bcb8ae; transform-origin:center; }.road-one{width:130%;height:42px;left:-15%;top:37%;transform:rotate(-31deg)}.road-two{width:115%;height:28px;left:6%;to
(Content truncated due to size limit. Use line ranges to read remaining content)
