Step 1: Design Breakdown & Setup
Before writing code, establish your design variables and project directory structure:

Colors:

Primary / Accent: #4F46E5 (Indigo)

Secondary / Accent Hover: #4338CA

Text Dark: #1F2937

Text Muted: #4B5563

Background Light: #F9FAFB

White: #FFFFFF

Typography: Clean sans-serif font family (e.g., 'Inter', system-ui, sans-serif).

Project Directory Structure
Create a dedicated project folder with the following structure:

assignment-9.4/
├── index.html
├── style.css
└── images/
    └── hero-image.png (or place SVG/placeholder images here)

    Step 2: Boilerplate & Semantic HTML (index.html)

    <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Landing Page - Assignment 9.4</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <!-- Header / Navigation -->
  <header class="navbar">
    <div class="container nav-container">
      <a href="#" class="logo">BrandName</a>
      <nav class="nav-links">
        <a href="#features">Features</a>
        <a href="#about">About</a>
        <a href="#pricing">Pricing</a>
      </nav>
      <div class="nav-actions">
        <a href="#" class="btn btn-secondary">Log In</a>
        <a href="#" class="btn btn-primary">Get Started</a>
      </div>
    </div>
  </header>

  <main>
    <!-- Hero Section -->
    <section class="hero">
      <div class="container hero-container">
        <div class="hero-content">
          <h1 class="hero-title">Build Modern Websites Faster Than Ever</h1>
          <p class="hero-description">
            Empower your workflow with intuitive tools and modern designs. Everything you need to craft high-converting landing pages.
          </p>
          <div class="hero-buttons">
            <a href="#" class="btn btn-primary btn-lg">Start Free Trial</a>
            <a href="#" class="btn btn-secondary btn-lg">Watch Demo</a>
          </div>
        </div>
        <div class="hero-image-wrapper">
          <img src="images/hero-image.png" alt="Product Hero Showcase" class="hero-image" onerror="this.src='https://via.placeholder.com/550x400/4F46E5/FFFFFF?text=Product+Preview'">
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="features">
      <div class="container">
        <div class="section-header">
          <h2>Powerful Features</h2>
          <p>Everything you need to launch and grow your digital product.</p>
        </div>
        <div class="features-grid">
          <article class="feature-card">
            <div class="feature-icon">⚡</div>
            <h3>Lightning Fast</h3>
            <p>Optimized for peak performance to deliver sub-second loading speeds for your visitors.</p>
          </article>
          <article class="feature-card">
            <div class="feature-icon">🎨</div>
            <h3>Fully Customizable</h3>
            <p>Easily tweak components, colors, and layouts using clean CSS variables and modular code.</p>
          </article>
          <article class="feature-card">
            <div class="feature-icon">🔒</div>
            <h3>Secure & Reliable</h3>
            <p>Built with modern web standards and security best practices out of the box.</p>
          </article>
        </div>
      </div>
    </section>
  </main>

  <!-- Footer -->
  <footer class="footer">
    <div class="container footer-container">
      <p>&copy; 2026 BrandName. All rights reserved.</p>
    </div>
  </footer>

</body>
</html>

Step 3: Base & Desktop Layout CSS (style.css)

/* ==========================================================================
   1. CSS Variables & Reset
   ========================================================================== */
:root {
  --primary-color: #4F46E5;
  --primary-hover: #4338CA;
  --text-dark: #1F2937;
  --text-muted: #4B5563;
  --bg-light: #F9FAFB;
  --white: #FFFFFF;
  --border-color: #E5E7EB;
  --font-family: 'Inter', system-ui, -apple-system, sans-serif;
  --max-width: 1200px;
  --radius: 8px;
}

*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: var(--font-family);
  color: var(--text-dark);
  background-color: var(--white);
  line-height: 1.6;
}

/* ==========================================================================
   2. Utility & Base Classes
   ========================================================================== */
.container {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 2rem;
}

/* Base Buttons */
.btn {
  display: inline-block;
  padding: 0.6rem 1.25rem;
  font-weight: 600;
  text-decoration: none;
  border-radius: var(--radius);
  transition: background-color 0.2s ease, transform 0.1s ease;
}

.btn-primary {
  background-color: var(--primary-color);
  color: var(--white);
}

.btn-primary:hover {
  background-color: var(--primary-hover);
}

.btn-secondary {
  background-color: var(--bg-light);
  color: var(--text-dark);
  border: 1px solid var(--border-color);
}

.btn-secondary:hover {
  background-color: #F3F4F6;
}

.btn-lg {
  padding: 0.85rem 1.75rem;
  font-size: 1rem;
}

/* ==========================================================================
   3. Navigation Bar (Flexbox)
   ========================================================================== */
.navbar {
  border-bottom: 1px solid var(--border-color);
  background-color: var(--white);
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
}

.logo {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--primary-color);
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-links a {
  text-decoration: none;
  color: var(--text-muted);
  font-weight: 500;
}

.nav-links a:hover {
  color: var(--primary-color);
}

.nav-actions {
  display: flex;
  gap: 1rem;
}

/* ==========================================================================
   4. Hero Section (Flexbox Layout)
   ========================================================================== */
.hero {
  padding: 5rem 0;
  background-color: var(--bg-light);
}

.hero-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 3rem;
}

.hero-content {
  flex: 1;
}

.hero-title {
  font-size: 3rem;
  line-height: 1.2;
  margin-bottom: 1.25rem;
}

.hero-description {
  font-size: 1.25rem;
  color: var(--text-muted);
  margin-bottom: 2rem;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
}

.hero-image-wrapper {
  flex: 1;
  display: flex;
  justify-content: center;
}

.hero-image {
  max-width: 100%;
  height: auto;
  border-radius: var(--radius);
  box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1);
}

/* ==========================================================================
   5. Features Section (CSS Grid Layout)
   ========================================================================== */
.features {
  padding: 5rem 0;
}

.section-header {
  text-align: center;
  margin-bottom: 3.5rem;
}

.section-header h2 {
  font-size: 2.25rem;
  margin-bottom: 0.5rem;
}

.section-header p {
  color: var(--text-muted);
  font-size: 1.1rem;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.feature-card {
  padding: 2rem;
  background-color: var(--white);
  border: 1px solid var(--border-color);
  border-radius: var(--radius);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.feature-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 20px -5px rgba(0, 0, 0, 0.08);
}

.feature-icon {
  font-size: 2rem;
  margin-bottom: 1rem;
}

.feature-card h3 {
  font-size: 1.25rem;
  margin-bottom: 0.75rem;
}

.feature-card p {
  color: var(--text-muted);
}

/* ==========================================================================
   6. Footer
   ========================================================================== */
.footer {
  border-top: 1px solid var(--border-color);
  padding: 2rem 0;
  text-align: center;
  color: var(--text-muted);
}