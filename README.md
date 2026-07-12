
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>OMNI Agent X — Autonomous Intelligence Platform</title>
<script src="https://cdn.tailwindcss.com">
</script>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Inter:wght@300;400;500;600;700;800;900&family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --neon-blue: #00d4ff;
    --neon-purple: #a855f7;
    --neon-green: #00ff88;
    --neon-orange: #ff6b35;
    --dark-bg: #030712;
    --card-bg: rgba(255, 255, 255, 0.03);
  }
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  html {
    scroll-behavior: smooth;
  }
  body {
    font-family: 'Inter', sans-serif;
    background: var(--dark-bg);
    color: #e2e8f0;
    overflow-x: hidden;
  }
  ::-webkit-scrollbar {
    width: 6px;
  }
  ::-webkit-scrollbar-track {
    background: #0a0a1a;
  }
  ::-webkit-scrollbar-thumb {
    background: var(--neon-blue);
    border-radius: 3px;
  }
  .bg-grid {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: linear-gradient(rgba(0, 212, 255, 0.03) 1px, transparent 1px), linear-gradient(90deg, rgba(0, 212, 255, 0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    z-index: 0;
    pointer-events: none;
  }
  .orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.3;
    animation: float 20s infinite ease-in-out;
  }
  .orb-1 {
    width: 500px;
    height: 500px;
    background: var(--neon-blue);
    top: -100px;
    left: -200px;
    animation-delay: 0s;
  }
  .orb-2 {
    width: 400px;
    height: 400px;
    background: var(--neon-purple);
    top: 300px;
    right: -150px;
    animation-delay: -7s;
  }
  .orb-3 {
    width: 350px;
    height: 350px;
    background: var(--neon-green);
    bottom: 100px;
    left: 30%;
    animation-delay: -14s;
  }
  @keyframes float {
    0%,
    100% {
      transform: translate(0, 0) scale(1);
    }
    25% {
      transform: translate(30px, -40px) scale(1.05);
    }
    50% {
      transform: translate(-20px, 30px) scale(0.95);
    }
    75% {
      transform: translate(40px, 20px) scale(1.02);
    }
  }
  .logo-network {
    position: relative;
    width: 200px;
    height: 200px;
  }
  .logo-node {
    position: absolute;
    width: 14px;
    height: 14px;
    background: var(--neon-blue);
    border-radius: 50%;
    box-shadow: 0 0 20px var(--neon-blue), 0 0 40px rgba(0, 212, 255, 0.3);
    animation: nodePulse 2s infinite ease-in-out;
  }
  .logo-node:nth-child(1) {
    top: 10px;
    left: 50%;
    transform: translateX(-50%);
    animation-delay: 0s;
  }
  .logo-node:nth-child(2) {
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
    animation-delay: 0.3s;
  }
  .logo-node:nth-child(3) {
    top: 50%;
    left: 10px;
    transform: translateY(-50%);
    animation-delay: 0.6s;
  }
  .logo-node:nth-child(4) {
    top: 50%;
    right: 10px;
    transform: translateY(-50%);
    animation-delay: 0.9s;
  }
  .logo-node:nth-child(5) {
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 24px;
    height: 24px;
    background: var(--neon-purple);
    box-shadow: 0 0 30px var(--neon-purple), 0 0 60px rgba(168, 85, 247, 0.4);
    animation-delay: 0s;
  }
  .logo-node:nth-child(6) {
    top: 30%;
    left: 20%;
    animation-delay: 1.2s;
    background: var(--neon-green);
    box-shadow: 0 0 20px var(--neon-green);
  }
  .logo-node:nth-child(7) {
    top: 30%;
    right: 20%;
    animation-delay: 1.5s;
    background: var(--neon-green);
    box-shadow: 0 0 20px var(--neon-green);
  }
  .logo-node:nth-child(8) {
    bottom: 30%;
    left: 20%;
    animation-delay: 1.8s;
    background: var(--neon-orange);
    box-shadow: 0 0 20px var(--neon-orange);
  }
  .logo-node:nth-child(9) {
    bottom: 30%;
    right: 20%;
    animation-delay: 2.1s;
    background: var(--neon-orange);
    box-shadow: 0 0 20px var(--neon-orange);
  }
  @keyframes nodePulse {
    0%,
    100% {
      opacity: 0.7;
      transform-origin: center;
    }
    50% {
      opacity: 1;
      box-shadow: 0 0 30px currentColor;
    }
  }
  .logo-lines {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
  .logo-lines line {
    stroke: rgba(0, 212, 255, 0.2);
    stroke-width: 1;
    animation: lineGlow 3s infinite ease-in-out;
  }
  .logo-lines line:nth-child(even) {
    animation-delay: 1.5s;
  }
  @keyframes lineGlow {
    0%,
    100% {
      stroke-opacity: 0.15;
    }
    50% {
      stroke-opacity: 0.5;
    }
  }
  .glass-card {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.06);
    backdrop-filter: blur(20px);
    border-radius: 16px;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  }
  .glass-card:hover {
    background: rgba(255, 255, 255, 0.06);
    border-color: rgba(0, 212, 255, 0.2);
    transform: translateY(-4px);
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3), 0 0 40px rgba(0, 212, 255, 0.05);
  }
  .btn-neon {
    position: relative;
    padding: 14px 36px;
    border: 1px solid var(--neon-blue);
    background: transparent;
    color: var(--neon-blue);
    font-family: 'Space Grotesk', sans-serif;
    font-weight: 600;
    font-size: 15px;
    letter-spacing: 0.5px;
    border-radius: 12px;
    cursor: pointer;
    overflow: hidden;
    transition: all 0.4s;
  }
  .btn-neon::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.15), transparent);
    transition: left 0.5s;
  }
  .btn-neon:hover::before {
    left: 100%;
  }
  .btn-neon:hover {
    background: rgba(0, 212, 255, 0.1);
    box-shadow: 0 0 30px rgba(0, 212, 255, 0.2), inset 0 0 30px rgba(0, 212, 255, 0.05);
    transform: translateY(-2px);
  }
  .btn-primary {
    background: linear-gradient(135deg, var(--neon-blue), var(--neon-purple));
    border: none;
    color: #fff;
    padding: 14px 36px;
    font-family: 'Space Grotesk', sans-serif;
    font-weight: 600;
    font-size: 15px;
    letter-spacing: 0.5px;
    border-radius: 12px;
    cursor: pointer;
    transition: all 0.4s;
    position: relative;
    overflow: hidden;
  }
  .btn-primary::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: linear-gradient(135deg, var(--neon-purple), var(--neon-blue));
    opacity: 0;
    transition: opacity 0.4s;
  }
  .btn-primary:hover::before {
    opacity: 1;
  }
  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 40px rgba(0, 212, 255, 0.3), 0 0 60px rgba(168, 85, 247, 0.15);
  }
  .btn-primary span {
    position: relative;
    z-index: 1;
  }
  .folder-tree {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    line-height: 1.8;
    color: #94a3b8;
  }
  .folder-tree .folder {
    color: var(--neon-blue);
  }
  .folder-tree .subfolder {
    color: var(--neon-purple);
  }
  .folder-tree .pipe {
    color: #334155;
  }
  .reveal {
    opacity: 0;
    transform: translateY(40px);
    transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
  }
  .reveal.active {
    opacity: 1;
    transform: translateY(0);
  }
  .typewriter {
    overflow: hidden;
    border-right: 2px solid var(--neon-blue);
    white-space: nowrap;
    animation: typing 3.5s steps(40) 1s forwards, blink 0.7s step-end infinite;
    width: 0;
    max-width: fit-content;
  }
  @keyframes typing {
    from {
      width: 0
    }
    to {
      width: 100%
    }
  }
  @keyframes blink {
    50% {
      border-color: transparent
    }
  }
  .skill-bar {
    height: 4px;
    background: rgba(255, 255, 255, 0.05);
    border-radius: 2px;
    overflow: hidden;
    margin-top: 8px;
  }
  .skill-fill {
    height: 100%;
    border-radius: 2px;
    width: 0;
    transition: width 1.5s cubic-bezier(0.4, 0, 0.2, 1);
  }
  nav {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 100;
    transition: all 0.3s;
  }
  nav.scrolled {
    background: rgba(3, 7, 18, 0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
  }
  .terminal {
    background: #0a0e1a;
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    overflow: hidden;
    font-family: 'JetBrains Mono', monospace;
  }
  .terminal-header {
    padding: 12px 16px;
    background: rgba(255, 255, 255, 0.03);
    border-bottom: 1px solid rgba(255, 255, 255, 0.06);
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .terminal-dot {
    width: 12px;
    height: 12px;
    border-radius: 50%;
  }
  .terminal-body {
    padding: 20px;
    font-size: 13px;
    line-height: 1.8;
    max-height: 350px;
    overflow-y: auto;
  }
  .terminal-body .prompt {
    color: var(--neon-green);
  }
  .terminal-body .command {
    color: #e2e8f0;
  }
  .terminal-body .output {
    color: #64748b;
  }
  .terminal-body .highlight {
    color: var(--neon-blue);
  }
  #particles {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 0;
    pointer-events: none;
  }
  .marquee-container {
    overflow: hidden;
    white-space: nowrap;
  }
  .marquee-content {
    display: inline-block;
    animation: marquee 30s linear infinite;
  }
  @keyframes marquee {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-50%);
    }
  }
  .agent-card {
    position: relative;
  }
  .agent-card::before {
    content: '';
    position: absolute;
    top: -1px;
    left: -1px;
    right: -1px;
    bottom: -1px;
    background: linear-gradient(135deg, var(--neon-blue), var(--neon-purple), var(--neon-green));
    border-radius: 17px;
    opacity: 0;
    transition: opacity 0.4s;
    z-index: -1;
  }
  .agent-card:hover::before {
    opacity: 0.3;
  }
  .stat-number {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 3rem;
    font-weight: 700;
    background: linear-gradient(135deg, var(--neon-blue), var(--neon-purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .mobile-menu {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(3, 7, 18, 0.97);
    backdrop-filter: blur(20px);
    z-index: 200;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 32px;
  }
  .mobile-menu.open {
    display: flex;
  }
  .evolve-pill {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: 500;
    border: 1px solid;
    transition: all 0.3s;
  }
  .evolve-pill:hover {
    transform: scale(1.05);
  }
  @media (max-width: 768px) {
    .stat-number {
      font-size: 2rem;
    }
    .hero-title {
      font-size: 2.5rem !important;
    }
    .nav-links {
      display: none !important;
    }
    .hamburger {
      display: flex !important;
    }
  }
  @media (max-width: 480px) {
    .hero-title {
      font-size: 1.8rem !important;
    }
  }
  .hamburger {
    display: none !important;
    flex-direction: column;
    gap: 5px;
    cursor: pointer;
    z-index: 300;
  }
  .hamburger span {
    display: block;
    width: 24px;
    height: 2px;
    background: #e2e8f0;
    transition: all 0.3s;
  }
  @media (max-width: 768px) {
    .hamburger {
      display: flex !important;
    }
  }
  .shimmer-text {
    background: linear-gradient(90deg, #e2e8f0 0%, var(--neon-blue) 50%, #e2e8f0 100%);
    background-size: 200% 100%;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: shimmer 3s linear infinite;
  }
  @keyframes shimmer {
    0% {
      background-position: -200% 0;
    }
    100% {
      background-position: 200% 0;
    }
  }
  .hex-icon {
    width: 56px;
    height: 56px;
    background: linear-gradient(135deg, rgba(0, 212, 255, 0.15), rgba(168, 85, 247, 0.15));
    clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    flex-shrink: 0;
  }
  .domain-badge {
    padding: 10px 20px;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 10px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    color: var(--neon-blue);
    transition: all 0.3s;
    cursor: pointer;
  }
  .domain-badge:hover {
    background: rgba(0, 212, 255, 0.08);
    border-color: rgba(0, 212, 255, 0.3);
    transform: translateY(-2px);
    box-shadow: 0 8px 30px rgba(0, 212, 255, 0.1);
  }
  .gradient-border {
    position: relative;
  }
  .gradient-border::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--neon-blue), var(--neon-purple), transparent);
  }
</style>
</head>
<body>

  <div class="bg-grid"></div>
  <canvas id="particles"></canvas>

  <!-- Floating Orbs -->
  <div class="orb orb-1"></div>
  <div class="orb orb-2"></div>
  <div class="orb orb-3"></div>

  <!-- Navigation -->
  <nav id="navbar" class="py-4 px-6">
    <div class="max-w-7xl mx-auto flex items-center justify-between">
      <a href="#" class="flex items-center gap-3 relative z-10">
        <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-cyan-400 to-purple-500 flex items-center justify-center font-bold text-white text-sm" style="font-family:'Space Grotesk',sans-serif;">◉</div>
        <span class="text-xl font-bold tracking-tight" style="font-family:'Space Grotesk',sans-serif;">OMNI<span class="text-cyan-400">AGENT</span></span>
      </a>
      <div class="nav-links flex items-center gap-8 text-sm font-medium text-gray-400">
        <a href="#features" class="hover:text-cyan-400 transition-colors">Features</a>
        <a href="#skills" class="hover:text-cyan-400 transition-colors">Skills</a>
        <a href="#architecture" class="hover:text-cyan-400 transition-colors">Architecture</a>
        <a href="#agents" class="hover:text-cyan-400 transition-colors">Agents</a>
        <a href="#evolution" class="hover:text-cyan-400 transition-colors">Evolution</a>
        <button class="btn-neon text-xs px-5 py-2.5" onclick="scrollToSection('cta')">Get Started</button>
      </div>
      <div class="hamburger" onclick="toggleMobileMenu()">
        <span></span><span></span><span></span>
      </div>
    </div>
  </nav>

  <!-- Mobile Menu -->
  <div class="mobile-menu" id="mobileMenu">
    <button class="absolute top-6 right-6 text-3xl text-gray-400" onclick="toggleMobileMenu()">✕</button>
    <a href="#features" class="text-2xl font-semibold hover:text-cyan-400 transition" onclick="toggleMobileMenu()">Features</a>
    <a href="#skills" class="text-2xl font-semibold hover:text-cyan-400 transition" onclick="toggleMobileMenu()">Skills</a>
    <a href="#architecture" class="text-2xl font-semibold hover:text-cyan-400 transition" onclick="toggleMobileMenu()">Architecture</a>
    <a href="#agents" class="text-2xl font-semibold hover:text-cyan-400 transition" onclick="toggleMobileMenu()">Agents</a>
    <a href="#evolution" class="text-2xl font-semibold hover:text-cyan-400 transition" onclick="toggleMobileMenu()">Evolution</a>
    <button class="btn-primary mt-4" onclick="toggleMobileMenu()"><span>Get Started</span></button>
  </div>

  <!-- HERO SECTION -->
  <section class="relative min-h-screen flex items-center justify-center pt-20 px-6" style="z-index:1;">
    <div class="max-w-6xl mx-auto text-center">
      <!-- Version badge -->
      <div class="reveal inline-flex items-center gap-2 px-4 py-2 rounded-full border border-cyan-500/20 bg-cyan-500/5 text-cyan-400 text-xs font-medium mb-8 tracking-wider" style="font-family:'JetBrains Mono',monospace;">
        <span class="w-2 h-2 rounded-full bg-cyan-400 animate-pulse"></span>
        OMNI AGENT X — v1.0 AUTONOMOUS AI OS
      </div>

      <!-- Logo Network -->
      <div class="reveal flex justify-center mb-10" style="transition-delay:0.1s;">
        <div class="logo-network">
          <svg class="logo-lines" viewBox="0 0 200 200">
            <line x1="100" y1="17" x2="100" y2="88"/>
            <line x1="100" y1="112" x2="100" y2="183"/>
            <line x1="17" y1="100" x2="88" y2="100"/>
            <line x1="112" y1="100" x2="183" y2="100"/>
            <line x1="46" y1="60" x2="88" y2="88"/>
            <line x1="154" y1="60" x2="112" y2="88"/>
            <line x1="46" y1="140" x2="88" y2="112"/>
            <line x1="154" y1="140" x2="112" y2="112"/>
            <line x1="100" y1="17" x2="46" y2="60"/>
            <line x1="100" y1="17" x2="154" y2="60"/>
            <line x1="100" y1="183" x2="46" y2="140"/>
            <line x1="100" y1="183" x2="154" y2="140"/>
            <line x1="17" y1="100" x2="46" y2="60"/>
            <line x1="17" y1="100" x2="46" y2="140"/>
            <line x1="183" y1="100" x2="154" y2="60"/>
            <line x1="183" y1="100" x2="154" y2="140"/>
          </svg>
          <div class="logo-node"></div>
          <div class="logo-node"></div>
          <div class="logo-node"></div>
          <div class="logo-node"></div>
          <div class="logo-node"></div>
          <div class="logo-node"></div>
          <div class="logo-node"></div>
          <div class="logo-node"></div>
          <div class="logo-node"></div>
        </div>
      </div>

      <!-- Title -->
      <h1 class="reveal hero-title text-5xl md:text-7xl lg:text-8xl font-black tracking-tight leading-none mb-6" style="font-family:'Space Grotesk',sans-serif; transition-delay:0.2s;">
        <span class="shimmer-text">OMNI AGENT</span>
      </h1>
      <p class="reveal text-lg md:text-xl text-gray-400 font-medium mb-2" style="font-family:'Space Grotesk',sans-serif; transition-delay:0.3s;">
        Autonomous Intelligence Platform
      </p>
      <p class="reveal text-sm md:text-base text-gray-500 mb-10" style="font-family:'JetBrains Mono',monospace; transition-delay:0.4s;">
        Research &bull; Create &bull; Automate &bull; Deploy &bull; Scale
      </p>

      <!-- Tagline -->
      <div class="reveal mb-12" style="transition-delay:0.45s;">
        <p class="text-2xl md:text-3xl font-light text-gray-300" style="font-family:'Space Grotesk',sans-serif;">
          One Agent. <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 to-purple-500 font-bold">Unlimited Execution.</span>
        </p>
      </div>

      <!-- CTA Buttons -->
      <div class="reveal flex flex-col sm:flex-row items-center justify-center gap-4 mb-16" style="transition-delay:0.5s;">
        <button class="btn-primary text-base px-10 py-4 rounded-xl" onclick="launchWorkspace()">
          <span class="flex items-center gap-2">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="5,3 19,12 5,21"/></svg>
            Launch Workspace
          </span>
        </button>
        <button class="btn-neon text-base px-10 py-4" onclick="createAgent()">
          <span class="flex items-center gap-2">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
            Create Agent
          </span>
        </button>
      </div>

      <!-- Animated descriptor -->
      <div class="reveal text-center" style="transition-delay:0.6s;">
        <p class="text-xs text-gray-600 tracking-widest uppercase mb-3" style="font-family:'JetBrains Mono',monospace;">The Autonomous AI Workforce for</p>
        <p class="text-lg text-gray