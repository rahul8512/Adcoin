<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#101510">
  <meta name="description" content="ADcoin (ADCN), a fixed-supply BEP-20 token on BNB Smart Chain.">
  <title>ADcoin | ADCN</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      color-scheme: dark;
      --ink: #101510;
      --panel: #171d17;
      --paper: #f0f2e9;
      --muted: #a7afa1;
      --line: #354034;
      --lime: #c6f36a;
      --orange: #ff8059;
      --mono: "DM Mono", monospace;
      --sans: "Space Grotesk", sans-serif;
    }

    * { box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      background: var(--ink);
      color: var(--paper);
      font-family: var(--sans);
    }

    a { color: inherit; }

    button, a { -webkit-tap-highlight-color: transparent; }

    .wrap {
      width: min(1120px, calc(100% - 48px));
      margin: 0 auto;
    }

    .topbar {
      position: sticky;
      top: 0;
      z-index: 5;
      border-bottom: 1px solid rgb(240 242 233 / 10%);
      background: rgb(16 21 16 / 92%);
      backdrop-filter: blur(14px);
    }

    .nav {
      min-height: 76px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
    }

    .brand {
      display: inline-flex;
      align-items: center;
      gap: 11px;
      text-decoration: none;
      font-size: 19px;
      font-weight: 700;
      letter-spacing: 0;
    }

    .brand svg { width: 36px; height: 36px; }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 25px;
    }

    .nav-links a {
      color: var(--muted);
      font-size: 13px;
      text-decoration: none;
      transition: color .2s ease;
    }

    .nav-links a:hover { color: var(--lime); }

    .nav-links .nav-cta {
      padding: 11px 15px;
      border: 1px solid var(--line);
      border-radius: 4px;
      color: var(--paper);
    }

    .menu-button {
      display: none;
      width: 42px;
      height: 42px;
      border: 1px solid var(--line);
      border-radius: 4px;
      background: transparent;
      color: var(--paper);
      font-size: 20px;
      cursor: pointer;
    }

    .hero {
      min-height: 590px;
      display: grid;
      grid-template-columns: 1.1fr .9fr;
      align-items: center;
      gap: 42px;
      padding: 72px 0 90px;
    }

    .eyebrow, .mono {
      color: var(--lime);
      font: 12px var(--mono);
      letter-spacing: .08em;
      text-transform: uppercase;
    }

    .hero h1 {
      max-width: 700px;
      margin: 18px 0;
      font-size: clamp(52px, 8vw, 96px);
      line-height: .96;
      letter-spacing: 0;
    }

    .hero h1 span { color: var(--lime); }

    .hero-copy {
      max-width: 490px;
      color: var(--muted);
      font-size: 17px;
      line-height: 1.7;
    }

    .actions {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 30px;
    }

    .button {
      display: inline-flex;
      min-height: 48px;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 0 17px;
      border: 1px solid var(--lime);
      border-radius: 4px;
      background: var(--lime);
      color: var(--ink);
      font: 600 14px var(--sans);
      text-decoration: none;
      cursor: pointer;
    }

    .button.secondary {
      border-color: var(--line);
      background: transparent;
      color: var(--paper);
    }

    .button:hover { filter: brightness(1.07); }

    .visual {
      position: relative;
      display: grid;
      min-height: 390px;
      place-items: center;
      overflow: hidden;
      border: 1px solid var(--line);
      border-radius: 6px;
      background:
        linear-gradient(135deg, transparent 49.8%, rgb(198 243 106 / 12%) 50%, transparent 50.2%),
        linear-gradient(45deg, transparent 49.8%, rgb(198 243 106 / 8%) 50%, transparent 50.2%),
        radial-gradient(ellipse at center, #273326 0%, #171d17 67%);
    }

    .visual::before, .visual::after {
      position: absolute;
      width: 280px;
      height: 280px;
      border: 1px solid rgb(198 243 106 / 20%);
      border-radius: 50%;
      content: "";
    }

    .visual::after { width: 360px; height: 360px; }

    .coin {
      z-index: 1;
      display: grid;
      width: 190px;
      aspect-ratio: 1;
      place-items: center;
      border: 1px solid var(--lime);
      border-radius: 50%;
      background: linear-gradient(145deg, #d5ff85, #96c63e);
      box-shadow: 0 0 80px rgb(198 243 106 / 18%);
      color: var(--ink);
      font-size: 68px;
      font-weight: 700;
    }

    .visual-tag {
      position: absolute;
      z-index: 2;
      padding: 8px 10px;
      border: 1px solid var(--line);
      border-radius: 3px;
      background: var(--ink);
      color: var(--muted);
      font: 11px var(--mono);
    }

    .tag-one { top: 18%; left: 8%; }
    .tag-two { right: 7%; bottom: 20%; color: var(--lime); }

    section { scroll-margin-top: 90px; }

    .section {
      padding: 88px 0;
      border-top: 1px solid rgb(240 242 233 / 10%);
    }

    .section-heading {
      display: flex;
      align-items: end;
      justify-content: space-between;
      gap: 25px;
      margin-bottom: 32px;
    }

    .section h2 {
      margin: 9px 0 0;
      font-size: clamp(32px, 5vw, 50px);
      letter-spacing: 0;
    }

    .section-intro {
      max-width: 440px;
      margin: 0;
      color: var(--muted);
      line-height: 1.7;
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 18px;
    }

    .about-block {
      min-height: 190px;
      padding: 25px;
      border: 1px solid var(--line);
      border-radius: 4px;
      background: var(--panel);
    }

    .about-block .index {
      color: var(--orange);
      font: 12px var(--mono);
    }

    .about-block h3 { margin: 20px 0 8px; font-size: 21px; }
    .about-block p { margin: 0; color: var(--muted); line-height: 1.65; }

    .token-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      border-top: 1px solid var(--line);
      border-left: 1px solid var(--line);
    }

    .token-item {
      min-height: 130px;
      padding: 22px;
      border-right: 1px solid var(--line);
      border-bottom: 1px solid var(--line);
    }

    .token-item span {
      display: block;
      margin-bottom: 13px;
      color: var(--muted);
      font: 11px var(--mono);
      text-transform: uppercase;
    }

    .token-item strong { font-size: 19px; font-weight: 500; }
    .token-item .supply { color: var(--lime); }

    .contract-box {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 18px;
      padding: 24px;
      border: 1px solid var(--line);
      border-left: 3px solid var(--lime);
      background: var(--panel);
    }

    .contract-box p { margin: 0 0 10px; color: var(--muted); font-size: 13px; }
    .address { overflow-wrap: anywhere; font: 14px var(--mono); }

    .notice {
      margin: 16px 0 0;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.6;
    }

    .steps {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 14px;
      counter-reset: step;
    }

    .step {
      min-height: 190px;
      padding: 22px;
      border-top: 1px solid var(--lime);
      background: var(--panel);
      counter-increment: step;
    }

    .step::before {
      content: "0" counter(step);
      color: var(--orange);
      font: 12px var(--mono);
    }

    .step h3 { margin: 20px 0 8px; font-size: 18px; }
    .step p { margin: 0; color: var(--muted); font-size: 14px; line-height: 1.6; }

    .roadmap {
      border-top: 1px solid var(--line);
    }

    .milestone {
      display: grid;
      grid-template-columns: 110px 1fr auto;
      align-items: center;
      gap: 18px;
      padding: 20px 10px;
      border-bottom: 1px solid var(--line);
    }

    .milestone .phase { color: var(--lime); font: 12px var(--mono); }
    .milestone h3 { margin: 0; font-size: 17px; }
    .status { color: var(--muted); font: 11px var(--mono); text-transform: uppercase; }

    .contact-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      padding: 25px 0;
      border-top: 1px solid var(--line);
      border-bottom: 1px solid var(--line);
    }

    .contact-row p { max-width: 540px; margin: 0; color: var(--muted); line-height: 1.6; }

    footer {
      padding: 24px 0 34px;
      color: var(--muted);
      font-size: 12px;
      line-height: 1.6;
    }

    footer .footer-top {
      display: flex;
      justify-content: space-between;
      gap: 20px;
      margin-bottom: 16px;
      color: var(--paper);
    }

    @media (max-width: 760px) {
      .wrap { width: min(100% - 32px, 560px); }
      .menu-button { display: block; }
      .nav-links {
        position: absolute;
        top: 75px;
        right: 0;
        left: 0;
        display: none;
        align-items: stretch;
        padding: 14px 20px 20px;
        border-bottom: 1px solid var(--line);
        background: var(--ink);
      }
      .nav-links.open { display: flex; flex-direction: column; gap: 0; }
      .nav-links a { padding: 13px 4px; }
      .nav-links .nav-cta { margin-top: 8px; text-align: center; }
      .hero { min-height: 0; grid-template-columns: 1fr; padding: 60px 0; }
      .visual { min-height: 320px; }
      .section { padding: 65px 0; }
      .section-heading { align-items: start; flex-direction: column; }
      .token-grid { grid-template-columns: repeat(2, 1fr); }
      .steps { grid-template-columns: 1fr; }
      .step { min-height: 0; }
      .contract-box, .contact-row { align-items: stretch; flex-direction: column; }
      .milestone { grid-template-columns: 70px 1fr; }
      .milestone .status { grid-column: 2; }
    }

    @media (max-width: 420px) {
      .about-grid { grid-template-columns: 1fr; }
      .token-grid { grid-template-columns: 1fr 1fr; }
      .token-item { padding: 16px 12px; }
      .token-item strong { font-size: 16px; }
      .footer-top { flex-direction: column; }
      .address { font-size: 12px; }
    }

    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        scroll-behavior: auto !important;
        transition-duration: .01ms !important;
      }
    }
  </style>
</head>
<body>
  <header class="topbar">
    <nav class="nav wrap" aria-label="Main navigation">
      <a class="brand" href="#home" aria-label="ADcoin home">
        <svg viewBox="0 0 40 40" role="img" aria-label="ADcoin logo">
          <rect x="1" y="1" width="38" height="38" rx="8" fill="#c6f36a"/>
          <path d="M10 29 18.5 10h3L30 29h-5l-1.6-4h-7L15 29zm8.1-8h3.8L20 16.2z" fill="#101510"/>
        </svg>
        <span>ADcoin</span>
      </a>
      <button class="menu-button" id="menuButton" type="button" aria-label="Open menu" aria-expanded="false">☰</button>
      <div class="nav-links" id="navLinks">
        <a href="#about">About</a>
        <a href="#tokenomics">Tokenomics</a>
        <a href="#contract">Contract</a>
        <a href="#buy">How to buy</a>
        <a href="#roadmap">Roadmap</a>
        <a href="#contact">Contact</a>
        <a class="nav-cta" href="#contract">View contract ↗</a>
      </div>
    </nav>
  </header>

  <main>
    <section class="hero wrap" id="home">
      <div>
        <div class="eyebrow">BNB SMART CHAIN · BEP-20</div>
        <h1>A fixed supply.<br><span>ADcoin.</span></h1>
        <p class="hero-copy">
          Meet ADCN, a fixed-supply token built on BNB Smart Chain.
          Explore the token details and verify the contract before interacting.
        </p>
        <div class="actions">
          <a class="button" href="#tokenomics">Explore ADCN <span aria-hidden="true">↓</span></a>
          <a class="button secondary" href="#contract">Check contract <span aria-hidden="true">↗</span></a>
        </div>
      </div>
      <div class="visual" aria-label="ADcoin token artwork">
        <span class="visual-tag tag-one">ADCN / BSC</span>
        <div class="coin" aria-hidden="true">A</div>
        <span class="visual-tag tag-two">50,000,000 ADCN</span>
      </div>
    </section>

    <section class="section" id="about">
      <div class="wrap">
        <div class="section-heading">
          <div>
            <div class="eyebrow">01 / About</div>
            <h2>Introducing ADcoin</h2>
          </div>
          <p class="section-intro">
            ADcoin is presented as a fixed-supply BEP-20 token on BNB Smart Chain.
            Use the verified on-chain contract as the source of truth for token data.
          </p>
        </div>
        <div class="about-grid">
          <article class="about-block">
            <span class="index">01 — NETWORK</span>
            <h3>Built for BNB Smart Chain</h3>
            <p>ADCN uses the BEP-20 token standard. Confirm the selected network before making any transaction.</p>
          </article>
          <article class="about-block">
            <span class="index">02 — SUPPLY</span>
            <h3>Fixed supply by design</h3>
            <p>The project-provided details state that the total supply is 50 million ADCN and minting is disabled. Verify this on-chain.</p>
          </article>
        </div>
      </div>
    </section>

    <section class="section" id="tokenomics">
      <div class="wrap">
        <div class="section-heading">
          <div>
            <div class="eyebrow">02 / Tokenomics</div>
            <h2>Token details</h2>
          </div>
          <p class="section-intro">The values below are supplied project information, not an independent audit or guarantee.</p>
        </div>
        <div class="token-grid">
          <div class="token-item"><span>Token name</span><strong>ADcoin</strong></div>
          <div class="token-item"><span>Symbol</span><strong>ADCN</strong></div>
          <div class="token-item"><span>Network</span><strong>BNB Smart Chain</strong></div>
          <div class="token-item"><span>Standard</span><strong>BEP-20</strong></div>
          <div class="token-item"><span>Total supply</span><strong class="supply">50,000,000 ADCN</strong></div>
          <div class="token-item"><span>Decimals</span><strong>18</strong></div>
          <div class="token-item"><span>Token type</span><strong>Fixed supply</strong></div>
          <div class="token-item"><span>Minting</span><strong>Disabled (project-provided)</strong></div>
          <div class="token-item"><span>Allocation</span><strong>Not specified</strong></div>
        </div>
      </div>
    </section>

    <section class="section" id="contract">
      <div class="wrap">
        <div class="section-heading">
          <div>
            <div class="eyebrow">03 / Contract</div>
            <h2>Verify before you trade</h2>
          </div>
          <p class="section-intro">Compare the address shown here with the official BscScan page before connecting a wallet or swapping.</p>
        </div>
        <div class="contract-box">
          <div>
            <p>ADCN contract · BNB Smart Chain</p>
            <div class="address" id="contractAddress">0x32EE6dB598E7F0Fa7c47D4601f8AB695d17Fe560</div>
          </div>
          <button class="button" id="copyButton" type="button">Copy address</button>
        </div>
        <p class="notice">
          Contract details are project-provided and have not been independently verified by this page.
          Check the address and token information on BscScan before interacting.
        </p>
        <div class="actions">
          <a class="button secondary" href="https://bscscan.com/token/0x32EE6dB598E7F0Fa7c47D4601f8AB695d17Fe560" target="_blank" rel="noopener noreferrer">
            Open BscScan ↗
          </a>
        </div>
      </div>
    </section>

    <section class="section" id="buy">
      <div class="wrap">
        <div class="section-heading">
          <div>
            <div class="eyebrow">04 / How to buy</div>
            <h2>Take your time</h2>
          </div>
          <p class="section-intro">A general guide only. Availability, fees, and supported networks can change. Never share your recovery phrase.</p>
        </div>
        <div class="steps">
          <article class="step">
            <h3>Set up a wallet</h3>
            <p>Use a wallet that supports BNB Smart Chain. Secure your recovery phrase offline and never give it to anyone.</p>
          </article>
          <article class="step">
            <h3>Fund the right network</h3>
            <p>Acquire BNB through a trusted provider and make sure it is on BNB Smart Chain. Keep some BNB for network fees.</p>
          </article>
          <article class="step">
            <h3>Check the swap route</h3>
            <p>Only proceed if Uniswap currently supports BNB Smart Chain for your swap. Verify the ADCN contract address and review every transaction before confirming.</p>
          </article>
        </div>
        <p class="notice">
          Do not use a lookalike token or a link sent by a stranger. If Uniswap does not support the network or token route,
          stop and verify official project guidance. This page does not provide investment advice.
        </p>
      </div>
    </section>

    <section class="section" id="roadmap">
      <div class="wrap">
        <div class="section-heading">
          <div>
            <div class="eyebrow">05 / Roadmap</div>
            <h2>Development plans</h2>
          </div>
          <p class="section-intro">These are editable placeholders, not confirmed promises. Replace them with approved milestones and dates before publishing.</p>
        </div>
        <div class="roadmap">
          <div class="milestone">
            <span class="phase">PHASE 01</span>
            <h3>Project foundations and token information</h3>
            <span class="status">Proposed</span>
          </div>
          <div class="milestone">
            <span class="phase">PHASE 02</span>
            <h3>Community channels and documentation</h3>
            <span class="status">Proposed</span>
          </div>
          <div class="milestone">
            <span class="phase">PHASE 03</span>
            <h3>Future ecosystem initiatives</h3>
            <span class="status">Proposed</span>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="contact">
      <div class="wrap">
        <div class="section-heading">
          <div>
            <div class="eyebrow">06 / Contact</div>
            <h2>Official channels</h2>
          </div>
        </div>
        <div class="contact-row">
          <p>Add the project’s verified support email and official social links here before launch. Do not publish unofficial support contacts.</p>
          <span class="mono">OFFICIAL CONTACT DETAILS PENDING</span>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="wrap">
      <div class="footer-top">
        <strong>ADcoin · ADCN</strong>
        <span>BNB Smart Chain · BEP-20</span>
      </div>
      <div>
        Digital assets can be risky and may lose value. Verify the network, contract address, and transaction details yourself.
        This website is informational and does not constitute financial advice.
      </div>
    </div>
  </footer>

  <script>
    const copyButton = document.querySelector("#copyButton");
    const contractAddress = document.querySelector("#contractAddress").textContent.trim();

    copyButton.addEventListener("click", async () => {
      try {
        await navigator.clipboard.writeText(contractAddress);
        copyButton.textContent = "Copied";
      } catch {
        const input = document.createElement("textarea");
        input.value = contractAddress;
        input.style.position = "fixed";
        input.style.opacity = "0";
        document.body.append(input);
        input.select();
        document.execCommand("copy");
        input.remove();
        copyButton.textContent = "Copied";
      }

      window.setTimeout(() => {
        copyButton.textContent = "Copy address";
      }, 1800);
    });

    const menuButton = document.querySelector("#menuButton");
    const navLinks = document.querySelector("#navLinks");

    menuButton.addEventListener("click", () => {
      const isOpen = navLinks.classList.toggle("open");
      menuButton.setAttribute("aria-expanded", String(isOpen));
      menuButton.setAttribute("aria-label", isOpen ? "Close menu" : "Open menu");
      menuButton.textContent = isOpen ? "×" : "☰";
    });

    navLinks.addEventListener("click", (event) => {
      if (event.target.closest("a")) {
        navLinks.classList.remove("open");
        menuButton.setAttribute("aria-expanded", "false");
        menuButton.setAttribute("aria-label", "Open menu");
        menuButton.textContent = "☰";
      }
    });
  </script>
</body>
</html>
