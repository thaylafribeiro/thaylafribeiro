<!DOCTYPE html>
<html lang="pt-BR" class="scroll-smooth">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Thayla Ribeiro — Desenvolvedora Back-end & Scrum Master</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg-primary: #090d16;
      --bg-secondary: #0f1623;
      --bg-card: #131c2e;
      --bg-card-hover: #182338;
      --border-color: #1f2d47;
      --border-highlight: #3b82f6;
      --text-primary: #f1f5f9;
      --text-secondary: #94a3b8;
      --text-muted: #64748b;
      --accent-blue: #3b82f6;
      --accent-blue-glow: rgba(59, 130, 246, 0.25);
      --accent-purple: #8b5cf6;
      --accent-emerald: #10b981;
      --accent-amber: #f59e0b;
      --accent-rose: #ef4444;
      --font-sans: 'Inter', system-ui, -apple-system, sans-serif;
      --font-mono: 'JetBrains Mono', monospace;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: var(--bg-primary);
      color: var(--text-primary);
      font-family: var(--font-sans);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* Background Grid Subtle */
    body::before {
      content: "";
      position: fixed;
      inset: 0;
      background-image: 
        linear-gradient(to right, rgba(31, 45, 71, 0.22) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(31, 45, 71, 0.22) 1px, transparent 1px);
      background-size: 48px 48px;
      pointer-events: none;
      z-index: -1;
    }

    .container {
      max-width: 1140px;
      margin: 0 auto;
      padding: 0 1.5rem;
    }

    /* Navbar */
    header {
      position: sticky;
      top: 0;
      z-index: 50;
      background: rgba(9, 13, 22, 0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border-color);
    }

    .nav-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 70px;
    }

    .brand {
      font-family: var(--font-mono);
      font-weight: 600;
      font-size: 1rem;
      color: var(--text-primary);
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .brand span {
      color: var(--accent-blue);
    }

    nav ul {
      display: flex;
      list-style: none;
      gap: 2rem;
    }

    nav a {
      color: var(--text-secondary);
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 500;
      transition: color 0.2s;
    }

    nav a:hover {
      color: var(--text-primary);
    }

    /* Hero Section */
    .hero {
      padding: 5.5rem 0 4.5rem;
      display: grid;
      grid-template-columns: 1.25fr 0.75fr;
      gap: 3rem;
      align-items: center;
    }

    .badges-row {
      display: flex;
      flex-wrap: wrap;
      gap: 0.75rem;
      margin-bottom: 1.5rem;
    }

    .badge {
      font-family: var(--font-mono);
      font-size: 0.78rem;
      padding: 0.35rem 0.85rem;
      border-radius: 999px;
      border: 1px solid var(--border-color);
      background: var(--bg-secondary);
      color: var(--text-secondary);
      display: inline-flex;
      align-items: center;
      gap: 0.45rem;
    }

    .badge.status {
      border-color: rgba(16, 185, 129, 0.35);
      background: rgba(16, 185, 129, 0.1);
      color: #34d399;
    }

    .status-dot {
      width: 8px;
      height: 8px;
      background: #10b981;
      border-radius: 50%;
      box-shadow: 0 0 8px #10b981;
    }

    .hero h1 {
      font-size: clamp(2.4rem, 4.5vw, 3.6rem);
      font-weight: 800;
      line-height: 1.1;
      letter-spacing: -0.03em;
      margin-bottom: 0.5rem;
    }

    .hero .subtitle {
      font-size: clamp(1.25rem, 2.2vw, 1.65rem);
      font-weight: 600;
      background: linear-gradient(90deg, #60a5fa, #a78bfa);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      margin-bottom: 1.5rem;
    }

    .hero p {
      color: var(--text-secondary);
      font-size: 1.08rem;
      max-width: 600px;
      margin-bottom: 2rem;
    }

    .hero strong {
      color: var(--text-primary);
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.5rem;
      padding: 0.85rem 1.5rem;
      border-radius: 10px;
      font-weight: 600;
      font-size: 0.95rem;
      text-decoration: none;
      cursor: pointer;
      transition: all 0.2s ease;
      border: 1px solid transparent;
    }

    .btn-primary {
      background: linear-gradient(135deg, #2563eb, #7c3aed);
      color: #fff;
      box-shadow: 0 8px 24px rgba(37, 99, 235, 0.25);
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 12px 28px rgba(37, 99, 235, 0.35);
    }

    .btn-secondary {
      background: var(--bg-card);
      color: var(--text-primary);
      border-color: var(--border-color);
    }

    .btn-secondary:hover {
      background: var(--bg-card-hover);
      border-color: var(--accent-blue);
    }

    /* Hero Terminal Card */
    .terminal-card {
      background: var(--bg-secondary);
      border: 1px solid var(--border-color);
      border-
