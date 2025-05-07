
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tech By Sabbir</title>
    <style>
        /* RESET & BASE STYLES */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            /* Color Variables */
            --primary: #2d3142;
            --secondary: #4f5d75;
            --accent: #5c80bc;
            --light: #f5f5f5;
            --dark: #333;
            --success: #2dc653;
            --error: #e63946;
            
            /* Spacing Variables */
            --space-xs: 0.5rem;
            --space-sm: 1rem;
            --space-md: 2rem;
            --space-lg: 4rem;
            
            /* Border Variables */
            --border-radius: 4px;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background-color: var(--light);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        a {
            color: var(--accent);
            text-decoration: none;
            transition: color 0.2s ease;
        }

        a:hover {
            color: var(--secondary);
        }

        /* LAYOUT */
        .container {
            width: 90%;
            max-width: 1140px;
            margin: 0 auto;
            padding: var(--space-sm);
        }

        .row {
            display: flex;
            flex-wrap: wrap;
        }

        /* HEADER */
        header {
            background-color: var(--primary);
            color: var(--light);
            padding: var(--space-sm) 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--light);
            letter-spacing: 1px;
        }

        .logo span {
            color: var(--accent);
        }

        /* NAVIGATION */
        nav ul {
            display: flex;
            list-style: none;
        }

        nav a {
            color: var(--light);
            margin-left: var(--space-md);
            font-weight: 500;
        }

        nav a:hover {
            color: var(--accent);
        }

        nav a.active {
            border-bottom: 2px solid var(--accent);
        }

        /* HAMBURGER MENU */
        .hamburger {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--light);
            cursor: pointer;
        }

        /* MOBILE NAVIGATION */
        .mobile-nav {
            position: fixed;
            top: 0;
            right: -100%;
            width: 70%;
            height: 100vh;
            background-color: var(--primary);
            padding: var(--space-lg) var(--space-md);
            transition: right 0.3s ease;
            z-index: 200;
            box-shadow: -5px 0 15px rgba(0, 0, 0, 0.1);
        }

        .mobile-nav.active {
            right: 0;
        }

        .mobile-nav ul {
            list-style: none;
        }

        .mobile-nav li {
            margin-bottom: var(--space-md);
        }

        .mobile-nav a {
            color: var(--light);
            font-size: 1.2rem;
        }

        .close-menu {
            position: absolute;
            top: var(--space-sm);
            right: var(--space-sm);
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--light);
            cursor: pointer;
        }

        /* OVERLAY */
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: none;
            z-index: 150;
        }

        .overlay.active {
            display: block;
        }

        /* HERO SECTION */
        .hero {
            background-color: var(--primary);
            color: var(--light);
            padding: var(--space-lg) 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: var(--space-sm);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto var(--space-md);
        }

        .btn {
            display: inline-block;
            background-color: var(--accent);
            color: var(--light);
            padding: 0.75rem 1.5rem;
            border-radius: var(--border-radius);
            font-weight: 500;
            transition: background-color 0.2s ease;
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            background-color: var(--secondary);
            color: var(--light);
        }

        /* CONTENT SECTIONS */
        .section {
            padding: var(--space-lg) 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: var(--space-md);
            font-size: 2rem;
            color: var(--primary);
        }

        /* ARTICLE CARDS */
        .articles {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: var(--space-md);
        }

        .article-card {
            background-color: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .article-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .article-image {
            height: 180px;
            background-color: var(--secondary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--light);
        }

        .article-content {
            padding: var(--space-md);
        }

        .article-tag {
            display: inline-block;
            background-color: var(--accent);
            color: var(--light);
            font-size: 0.8rem;
            padding: 0.25rem 0.5rem;
            border-radius: var(--border-radius);
            margin-bottom: var(--space-xs);
        }

        .article-title {
            margin-bottom: var(--space-xs);
            font-size: 1.2rem;
        }

        .article-excerpt {
            color: var(--secondary);
            margin-bottom: var(--space-sm);
        }

        .article-meta {
            display: flex;
            justify-content: space-between;
            font-size: 0.8rem;
            color: var(--secondary);
        }

        /* LOGIN FORM */
        .login-section {
            max-width: 500px;
            margin: 0 auto;
            padding: var(--space-md);
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }

        .form-title {
            text-align: center;
            margin-bottom: var(--space-md);
            color: var(--primary);
        }

        .form-group {
            margin-bottom: var(--space-md);
        }

        .form-group label {
            display: block;
            margin-bottom: var(--space-xs);
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #ddd;
            border-radius: var(--border-radius);
            font-size: 1rem;
            transition: border-color 0.2s ease;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--accent);
            box-shadow: 0 0 0 2px rgba(92, 128, 188, 0.1);
        }

        .form-check {
            display: flex;
            align-items: center;
            margin-bottom: var(--space-md);
        }

        .form-check input {
            margin-right: var(--space-xs);
        }

        .form-links {
            display: flex;
            justify-content: space-between;
            margin-top: var(--space-sm);
            font-size: 0.9rem;
        }

        /* FOOTER */
        footer {
            background-color: var(--primary);
            color: var(--light);
            padding: var(--space-md) 0;
            margin-top: auto;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .footer-nav {
            display: flex;
            list-style: none;
        }

        .footer-nav li {
            margin-left: var(--space-md);
        }

        .footer-nav a {
            color: var(--light);
        }

        /* PAGE DISPLAY CONTROL */
        .page-content {
            display: none;
        }

        .page-content.active {
            display: block;
        }

        /* ALERT MESSAGES */
        .alert {
            padding: var(--space-sm);
            border-radius: var(--border-radius);
            margin-bottom: var(--space-md);
            color: white;
        }

        .alert-success {
            background-color: var(--success);
        }

        .alert-error {
            background-color: var(--error);
        }

        /* RESPONSIVE STYLES */
        @media (max-width: 768px) {
            nav ul {
                display: none;
            }

            .hamburger {
                display: block;
            }

            .footer-content {
                flex-direction: column;
                text-align: center;
            }

            .footer-nav {
                margin-top: var(--space-sm);
                justify-content: center;
            }

            .footer-nav li {
                margin: 0 var(--space-xs);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">Tech<span>By</span>Sabbir</div>
            <nav>
                <ul>
                    <li><a href="#home" class="nav-link active" data-page="home">Home</a></li>
                    <li><a href="#articles" class="nav-link" data-page="articles">Articles</a></li>
                    <li><a href="#tutorials" class="nav-link" data-page="tutorials">Tutorials</a></li>
                    <li><a href="#about" class="nav-link" data-page="about">About</a></li>
                    <li><a href="#login" class="nav-link" data-page="login">Login</a></li>
                </ul>
            </nav>
            <button class="hamburger" aria-label="Menu">☰</button>
        </div>
    </header>

    <!-- Mobile Navigation -->
    <div class="mobile-nav">
        <button class="close-menu" aria-label="Close menu">✕</button>
        <ul>
            <li><a href="#home" class="nav-link" data-page="home">Home</a></li>
            <li><a href="#articles" class="nav-link" data-page="articles">Articles</a></li>
            <li><a href="#tutorials" class="nav-link" data-page="tutorials">Tutorials</a></li>
            <li><a href="#about" class="nav-link" data-page="about">About</a></li>
            <li><a href="#login" class="nav-link" data-page="login">Login</a></li>
        </ul>
    </div>

    <!-- Overlay -->
    <div class="overlay"></div>

    <!-- Main Content -->
    <main>
        <!-- Home Page -->
        <div id="home" class="page-content active">
            <!-- Hero Section -->
            <section class="hero">
                <div class="container">
                    <h1>Welcome to Tech By Sabbir</h1>
                    <p>Minimalist insights into technology, programming, and digital innovation</p>
                    <a href="#articles" class="btn nav-link" data-page="articles">Explore Articles</a>
                </div>
            </section>

            <!-- Featured Articles -->
            <section class="section">
                <div class="container">
                    <h2 class="section-title">Featured Articles</h2>
                    <div class="articles">
                        <!-- Article 1 -->
                        <article class="article-card">
                            <div class="article-image">Featured Image</div>
                            <div class="article-content">
                                <span class="article-tag">AI</span>
                                <h3 class="article-title">Minimalism in UI Design</h3>
                                <p class="article-excerpt">How less becomes more in modern user interface design principles.</p>
                                <div class="article-meta">
                                    <span>May 7, 2025</span>
                                    <span>5 min read</span>
                                </div>
                            </div>
                        </article>

                        <!-- Article 2 -->
                        <article class="article-card">
                            <div class="article-image">Featured Image</div>
                            <div class="article-content">
                                <span class="article-tag">Development</span>
                                <h3 class="article-title">Clean Code Principles</h3>
                                <p class="article-excerpt">Writing maintainable code that your future self will thank you for.</p>
                                <div class="article-meta">
                                    <span>May 5, 2025</span>
                                    <span>7 min read</span>
                                </div>
                            </div>
                        </article>

                        <!-- Article 3 -->
                        <article class="article-card">
                            <div class="article-image">Featured Image</div>
                            <div class="article-content">
                                <span class="article-tag">Tools</span>
                                <h3 class="article-title">Essential Dev Tools 2025</h3>
                                <p class="article-excerpt">The minimal toolset every developer should have in their arsenal.</p>
                                <div class="article-meta">
                                    <span>May 3, 2025</span>
                                    <span>4 min read</span>
                                </div>
                            </div>
                        </article>
                    </div>
                </div>
            </section>
        </div>

        <!-- Articles Page -->
        <div id="articles" class="page-content">
            <section class="section">
                <div class="container">
                    <h2 class="section-title">All Articles</h2>
                    <div class="articles">
                        <!-- Article 1 -->
                        <article class="article-card">
                            <div class="article-image">Featured Image</div>
                            <div class="article-content">
                                <span class="article-tag">AI</span>
                                <h3 class="article-title">Minimalism in UI Design</h3>
                                <p class="article-excerpt">How less becomes more in modern user interface design principles.</p>
                                <div class="article-meta">
                                    <span>May 7, 2025</span>
                                    <span>5 min read</span>
                                </div>
                            </div>
                        </article>

                        <!-- Article 2 -->
                        <article class="article-card">
                            <div class="article-image">Featured Image</div>
                            <div class="article-content">
                                <span class="article-tag">Development</span>
                                <h3 class="article-title">Clean Code Principles</h3>
                                <p class="article-excerpt">Writing maintainable code that your future self will thank you for.</p>
                                <div class="article-meta">
                                    <span>May 5, 2025</span>
                                    <span>7 min read</span>
                                </div>
                            </div>
                        </article>

                        <!-- Article 3 -->
                        <article class="article-card">
                            <div class="article-image">Featured Image</div>
                            <div class="article-content">
                                <span class="article-tag">Tools</span>
                                <h3 class="article-title">Essential Dev Tools 2025</h3>
                                <p class="article-excerpt">The minimal toolset every developer should have in their arsenal.</p>
                                <div class="article-meta">
                                    <span>May 3, 2025</span>
                                    <span>4 min read</span>
                                </div>
                            </div>
                        </article>

                        <!-- Article 4 -->
                        <article class="article-card">
                            <div class="article-image">Featured Image</div>
                            <div class="article-content">
                                <span class="article-tag">Career</span>
                                <h3 class="article-title">Remote Work Strategies</h3>
                                <p class="article-excerpt">Effective approaches to stay productive in a remote work environment.</p>
                                <div class="article-meta">
                                    <span>May 1, 2025</span>
                                    <span>6 min read</span>
                                </div>
                            </div>
                        </article>

                        <!-- Article 5 -->
                        <article class="article-card">
                            <div class="article-image">Featured Image</div>
                            <div class="article-content">
                                <span class="article-tag">Security</span>
                                <h3 class="article-title">Web Security Essentials</h3>
                                <p class="article-excerpt">Fundamental security practices every web developer should implement.</p>
                                <div class="article-meta">
                                    <span>April 28, 2025</span>
                                    <span>8 min read</span>
                                </div>
                            </div>
                        </article>

                        <!-- Article 6 -->
                        <article class="article-card">
                            <div class="article-image">Featured Image</div>
                            <div class="article-content">
                                <span class="article-tag">Hardware</span>
                                <h3 class="article-title">Minimal Desk Setup 2025</h3>
                                <p class="article-excerpt">Creating a productive workspace with only the essentials.</p>
                                <div class="article-meta">
                                    <span>April 25, 2025</span>
                                    <span>5 min read</span>
                                </div>
                            </div>
                        </article>
                    </div>
                </div>
            </section>
        </div>

        <!-- Tutorials Page -->
        <div id="tutorials" class="page-content">
            <section class="section">
                <div class="container">
                    <h2 class="section-title">Tutorials</h2>
                    <div class="articles">
                        <!-- Tutorial 1 -->
                        <article class="article-card">
                            <div class="article-image">Tutorial Image</div>
                            <div class="article-content">
                                <span class="article-tag">JavaScript</span>
                                <h3 class="article-title">Building a Minimal SPA</h3>
                                <p class="article-excerpt">Create a single-page application without any frameworks.</p>
                                <div class="article-meta">
                                    <span>May 6, 2025</span>
                                    <span>15 min read</span>
                                </div>
                            </div>
                        </article>

                        <!-- Tutorial 2 -->
                        <article class="article-card">
                            <div class="article-image">Tutorial Image</div>
                            <div class="article-content">
                                <span class="article-tag">CSS</span>
                                <h3 class="article-title">CSS Grid Mastery</h3>
                                <p class="article-excerpt">Master CSS Grid layout with these practical examples.</p>
                                <div class="article-meta">
                                    <span>May 4, 2025</span>
                                    <span>12 min read</span>
                                </div>
                            </div>
                        </article>

                        <!-- Tutorial 3 -->
                        <article class="article-card">
                            <div class="article-image">Tutorial Image</div>
                            <div class="article-content">
                                <span class="article-tag">Performance</span>
                                <h3 class="article-title">Website Optimization</h3>
                                <p class="article-excerpt">Simple techniques to improve your website's performance.</p>
                                <div class="article-meta">
                                    <span>May 2, 2025</span>
                                    <span>10 min read</span>
                                </div>
                            </div>
                        </article>
                    </div>
                </div>
            </section>
        </div>

        <!-- About Page -->
        <div id="about" class="page-content">
            <section class="section">
                <div class="container">
                    <h2 class="section-title">About Tech By Sabbir</h2>
                    <div style="max-width: 700px; margin: 0 auto;">
                        <p style="margin-bottom: var(--space-md);">
                            Tech By Sabbir is a minimalist tech blog focused on providing clear, concise, and valuable insights into technology, 
                            programming, and digital innovation. Founded by Sabbir, a passionate technologist and developer, this blog aims to 
                            strip away the noise and focus on what truly matters in the ever-evolving tech landscape.
                        </p>
                        <p style="margin-bottom: var(--space-md);">
                            Our philosophy is simple: less is more. We believe in quality over quantity, depth over breadth, and clarity over 
                            complexity. Every article, tutorial, and resource shared here is crafted with this minimalist approach in mind.
                        </p>
                        <p style="margin-bottom: var(--space-md);">
                            Whether you're a seasoned developer, a tech enthusiast, or someone curious about the digital world, Tech By Sabbir 
                            offers valuable content that respects your time and intelligence. No fluff, no unnecessary jargon—just meaningful 
                            insights that you can apply in your work and life.
                        </p>
                        <p>
                            Thank you for being part of this journey. If you have any questions, suggestions, or just want to say hello, 
                            don't hesitate to reach out.
                        </p>
                    </div>
                </div>
            </section>
        </div>

        <!-- Login Page -->
        <div id="login" class="page-content">
            <section class="section">
                <div class="container">
                    <div class="login-section">
                        <h2 class="form-title">Login to Your Account</h2>
                        <div id="login-alert" class="alert" style="display: none;"></div>
                        <form id="login-form">
                            <div class="form-group">
                                <label for="email">Email</label>
                                <input type="email" id="email" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="password">Password</label>
                                <input type="password" id="password" class="form-control" required>
                            </div>
                            <div class="form-check">
                                <input type="checkbox" id="remember-me">
                                <label for="remember-me">Remember me</label>
                            </div>
                            <button type="submit" class="btn" style="width: 100%;">Login</button>
                            <div class="form-links">
                                <a href="#">Forgot password?</a>
                                <a href="#">Register</a>
                            </div>
                        </form>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div>&copy; 2025 Tech By Sabbir. All rights reserved.</div>
                <ul class="footer-nav">
                    <li><a href="#home" class="nav-link" data-page="home">Home</a></li>
                    <li><a href="#articles" class="nav-link" data-page="articles">Articles</a></li>
                    <li><a href="#about" class="nav-link" data-page="about">About</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Navigation
            const navLinks = document.querySelectorAll('.nav-link');
            const pages = document.querySelectorAll('.page-content');
            
            // Mobile menu elements
            const hamburger = document.querySelector('.hamburger');
            const mobileNav = document.querySelector('.mobile-nav');
            const closeMenu = document.querySelector('.close-menu');
            const overlay = document.querySelector('.overlay');
            
            // Login form
            const loginForm = document.getElementById('login-form');
            const loginAlert = document.getElementById('login-alert');

            // Handle navigation
            function navigateTo(pageId) {
                // Hide all pages
                pages.forEach(page => {
                    page.classList.remove('active');
                });
                
                // Show selected page
                document.getElementById(pageId).classList.add('active');
                
                // Update active state in navigation
                navLinks.forEach(link => {
                    if (link.dataset.page === pageId) {
                        link.classList.add('active');
                    } else {
                        link.classList.remove('active');
                    }
                });
                
                // Close mobile menu if open
                mobileNav.classList.remove('active');
                overlay.classList.remove('active');
                
                // Scroll to top
                window.scrollTo(0, 0);
            }
            
            // Add click event to all navigation links
            navLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const pageId = this.dataset.page;
                    navigateTo(pageId);
                });
            });
            
            // Mobile menu toggle
            hamburger.addEventListener('click', function() {
                mobileNav.classList.add('active');
                overlay.classList.add('active');
            });
            
            closeMenu.addEventListener('click', function() {
                mobileNav.classList.remove('active');
                overlay.classList.remove('active');
            });
            
            overlay.addEventListener('click', function() {
                mobileNav.classList.remove('active');
                overlay.classList.remove('active');
            });
            
            // Handle login form submission
            loginForm.addEventListener('submit', function(e) {
                e.preventDefault();
                
                const email = document.getElementById('email').value;
                const password = document.getElementById('password').value;
                
                // Simple validation
                if (!email || !password) {
                    showAlert('Please enter both email and password', 'error');
                    return;
                }
                
                // Simulate login (would connect to backend in real application)
                simulateLogin(email, password);
            });
            
            // Simulate login process
            function simulateLogin(email, password) {
                // Show loading state
                const submitBtn = loginForm.querySelector('button[type="submit"]');
                const originalText = submitBtn.textContent;
                submitBtn.textContent = 'Logging in...';
                submitBtn.disabled = true;
                
                // Simulate API call
                setTimeout(() => {
                    // Reset button
                    submitBtn.textContent = originalText;
                    submitBtn.disabled = false;
                    
                    if (email.includes('@') && password.length >= 6) {
                        // Success login
                        showAlert('Login successful! Redirecting...', 'success');
                        
                        // Redirect to home after short delay
                        setTimeout(() => {
                            navigateTo('home');
                        }, 1500);
                    } else {
                        // Failed login
                        showAlert('Invalid email or password', 'error');
                    }
                }, 1000);
            }
            
            // Show alert message
            function showAlert(message, type) {
                loginAlert.textContent = message;
                loginAlert.className = `alert alert-${type}`;
                loginAlert.style.display = 'block';
                
                // Hide after 3 seconds
                setTimeout(() => {
                    loginAlert.style.display = 'none';
                }, 3000);
            }
            
            // Handle URL hash for direct page access
            function checkUrlHash() {
                const hash = window.location.hash.substring(1);
                if (hash) {
                    const pageId = document.getElementById(hash) ? hash : 'home';
                    navigateTo(pageId);
                }
            }
            
            // Check hash on page load and when it changes
            checkUrlHash();
            window.addEventListener('hashchange', checkUrlHash);
        });
    </script>
</body>
</html>
