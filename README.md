<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tamilarasan S | Web Developer & AI Engineer</title>
    <!-- Modern Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;800&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-color: #0b0514;
            --primary: #9900ff;
            --primary-glow: #b24bff;
            --secondary: #00fbff;
            --text-main: #ffffff;
            --text-muted: #a99ec0;
            --card-bg: rgba(25, 15, 45, 0.4);
            --border: rgba(153, 0, 255, 0.2);
            --border-hover: rgba(0, 251, 255, 0.5);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Outfit', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Ambient Background Orbs */
        .ambient-light {
            position: fixed;
            border-radius: 50%;
            filter: blur(120px);
            z-index: -1;
            animation: float 12s infinite alternate ease-in-out;
        }
        .light-1 { width: 400px; height: 400px; background: rgba(153, 0, 255, 0.25); top: -100px; left: -100px; }
        .light-2 { width: 350px; height: 350px; background: rgba(0, 251, 255, 0.15); bottom: -50px; right: -50px; animation-delay: -5s; }
        .light-3 { width: 500px; height: 500px; background: rgba(178, 75, 255, 0.15); top: 40%; left: 30%; animation-duration: 18s; }

        @keyframes float {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(50px, 50px) scale(1.1); }
        }

        /* Container & Layout */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
            position: relative;
            z-index: 1;
        }

        section {
            margin-bottom: 6rem;
        }

        /* Typography & Gradients */
        h1 {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 0.5rem;
            line-height: 1.1;
        }
        h2 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            display: inline-block;
            border-bottom: 2px solid var(--primary);
            padding-bottom: 0.5rem;
        }
        .gradient-text {
            background: linear-gradient(90deg, var(--secondary), var(--primary), var(--primary-glow));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-size: 200% auto;
            animation: shine 4s linear infinite;
        }
        @keyframes shine {
            to { background-position: 200% center; }
        }
        
        .subtitle {
            font-size: 1.5rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
            font-weight: 400;
        }
        .bio {
            font-size: 1.2rem;
            max-width: 800px;
            color: var(--text-muted);
            margin-bottom: 2.5rem;
            border-left: 4px solid var(--primary);
            padding-left: 1.5rem;
        }

        /* Glassmorphism Cards */
        .glass-card {
            background: var(--card-bg);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid var(--border);
            border-radius: 20px;
            padding: 2rem;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }
        .glass-card::before {
            content: '';
            position: absolute;
            top: 0; left: -150%; width: 50%; height: 100%;
            background: linear-gradient(to right, transparent, rgba(255,255,255,0.08), transparent);
            transform: skewX(-25deg);
            transition: all 0.7s ease;
        }
        .glass-card:hover::before {
            left: 150%;
        }
        .glass-card:hover {
            transform: translateY(-10px);
            border-color: var(--border-hover);
            box-shadow: 0 15px 40px rgba(153, 0, 255, 0.3), 0 0 20px rgba(0, 251, 255, 0.15);
        }

        /* Social Buttons */
        .social-links {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 3rem;
        }
        .glass-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            text-decoration: none;
            color: var(--text-main);
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid var(--border);
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }
        .glass-btn i {
            font-size: 1.2rem;
        }
        .glass-btn:hover {
            background: var(--primary);
            border-color: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 5px 20px rgba(153, 0, 255, 0.4);
            color: white;
        }

        /* Tool Images Container */
        .tools-img-wrapper {
            background: rgba(0,0,0,0.3);
            border-radius: 15px;
            padding: 1.5rem;
            display: inline-block;
            margin-bottom: 1.5rem;
            border: 1px solid var(--border);
            width: 100%;
            text-align: center;
        }
        .tools-img-wrapper img {
            max-width: 100%;
            height: auto;
        }

        /* Grids */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .stats-grid {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            align-items: center;
        }
        .stats-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.5rem;
            width: 100%;
        }
        .stat-img {
            max-width: 100%;
            border-radius: 12px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.5);
        }
        .stat-img:hover {
            transform: scale(1.03);
            box-shadow: 0 10px 25px rgba(153, 0, 255, 0.4);
        }

        /* Tags */
        .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1.5rem;
        }
        .tags span {
            background: rgba(0, 251, 255, 0.1);
            color: var(--secondary);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.85rem;
            font-family: 'Fira Code', monospace;
            border: 1px solid rgba(0, 251, 255, 0.2);
        }

        /* Experience Layout */
        .experience-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        .exp-list {
            list-style: none;
        }
        .exp-list li {
            position: relative;
            padding-left: 2rem;
            margin-bottom: 1.5rem;
        }
        .exp-list li::before {
            content: '✦';
            position: absolute;
            left: 0;
            color: var(--primary-glow);
            font-size: 1.2rem;
        }

        footer {
            text-align: center;
            padding: 3rem 0;
            border-top: 1px solid var(--border);
            color: var(--text-muted);
            margin-top: 4rem;
        }
        footer a {
            color: var(--secondary);
            text-decoration: none;
            font-weight: 600;
        }

        /* Scroll Reveal Animation Classes */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s cubic-bezier(0.5, 0, 0, 1);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            h1 { font-size: 2.5rem; }
            h2 { font-size: 2rem; }
            .container { padding: 2rem 1.5rem; }
        }
    </style>
</head>
<body>

    <!-- Background Orbs -->
    <div class="ambient-light light-1"></div>
    <div class="ambient-light light-2"></div>
    <div class="ambient-light light-3"></div>

    <div class="container">
        
        <!-- HERO SECTION -->
        <section class="reveal">
            <h1>Hi there, I'm <br><span class="gradient-text">TAMILARASAN S</span> 👋</h1>
            <h3 class="subtitle">Web Developer | AI & ML Engineer</h3>
            <p class="bio">
                Highly motivated Computer Science Engineer specializing in developing responsive web applications, AI-driven automation, and complex data analytics. I bridge the gap between complex data sources and user-centric interfaces.
            </p>

            <div class="social-links">
                <a href="https://linkedin.com/in/tamilarasansdeveloper/" target="_blank" class="glass-btn"><i class="fab fa-linkedin" style="color: #0077B5;"></i> LinkedIn</a>
                <a href="mailto:tamilarasanss.dev@gmail.com" class="glass-btn"><i class="fas fa-envelope" style="color: #D14836;"></i> Email</a>
                <a href="https://leetcode.com/u/tamilarasangithub/" target="_blank" class="glass-btn"><i class="fas fa-code" style="color: #FFA116;"></i> LeetCode</a>
                <a href="https://discord.gg/1288063770240876588" target="_blank" class="glass-btn"><i class="fab fa-discord" style="color: #7289DA;"></i> Discord</a>
                <a href="https://reddit.com/user/parallel_Glitch/" target="_blank" class="glass-btn"><i class="fab fa-reddit" style="color: #FF4500;"></i> Reddit</a>
            </div>
        </section>

        <!-- TOOLS & TECH SECTION -->
        <section class="reveal">
            <h2><i class="fas fa-wrench gradient-text"></i> Tools & Technologies</h2>
            
            <div class="glass-card" style="margin-bottom: 2rem;">
                <h3>Core Programming & Web Development</h3>
                <div class="tools-img-wrapper" style="margin-top: 1rem;">
                    <a href="https://skillicons.dev" target="_blank">
                        <img src="https://skillicons.dev/icons?i=py,js,dart,cpp,html,css,react,tailwind,nodejs,django,fastapi,firebase,postgres,mongodb&theme=dark" alt="Web Dev Tools" />
                    </a>
                </div>
                
                <h3 style="margin-top: 1.5rem;">AI Frameworks, Hardware & DevOps</h3>
                <div class="tools-img-wrapper" style="margin-top: 1rem; margin-bottom: 0;">
                    <a href="https://skillicons.dev" target="_blank">
                        <img src="https://skillicons.dev/icons?i=pytorch,opencv,arduino,git,github,vscode,postman,figma,wordpress,pypi&theme=dark" alt="AI Tools" />
                    </a>
                </div>
            </div>
        </section>

        <!-- ANALYTICS SECTION -->
        <section class="reveal">
            <h2><i class="fas fa-chart-line gradient-text"></i> Analytics & Metrics</h2>
            
            <div class="stats-grid">
                <img src="https://github-readme-activity-graph.vercel.app/graph?username=tamilarasangithub&bg_color=0d0d0d&color=9900ff&line=9900ff&point=00fbff&area=true&hide_border=true" alt="GitHub Activity Graph" class="stat-img" style="width: 100%;" />
                
                <div class="stats-row">
                    <img src="https://github-readme-stats.vercel.app/api?username=tamilarasangithub&theme=midnight-purple&show_icons=true&hide_border=false&count_private=true" alt="GitHub Stats" class="stat-img" />
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=tamilarasangithub&theme=midnight-purple&hide_border=false&layout=compact" alt="Top Languages" class="stat-img" />
                </div>
                
                <img src="https://nirzak-streak-stats.vercel.app/?user=tamilarasangithub&theme=midnight-purple&hide_border=false" alt="GitHub Streak Stats" class="stat-img" style="width: 100%; max-width: 800px;" />

                <a href="https://leetcode.com/u/tamilarasangithub/" target="_blank">
                    <img src="https://leetcard.jacoblin.cool/tamilarasangithub?theme=dark&font=Inter&ext=activity" alt="LeetCode Stats" class="stat-img" style="max-width: 400px;" />
                </a>
            </div>
        </section>

        <!-- PROJECTS SECTION -->
        <section class="reveal">
            <h2><i class="fas fa-rocket gradient-text"></i> Featured Projects</h2>
            
            <div class="projects-grid">
                <div class="glass-card">
                    <h3 style="font-size: 1.3rem; margin-bottom: 0.5rem; color: #fff;">Smart Wildlife Intrusion Alert System</h3>
                    <p style="color: var(--text-muted); font-size: 0.95rem;">Real-time edge detection system for monitoring wildlife anomalies.</p>
                    <div class="tags">
                        <span>TinyML</span><span>ESP32-CAM</span><span>Python</span><span>OpenCV</span><span>YOLO</span>
                    </div>
                </div>

                <div class="glass-card">
                    <h3 style="font-size: 1.3rem; margin-bottom: 0.5rem; color: #fff;">AI Snake Identification System</h3>
                    <p style="color: var(--text-muted); font-size: 0.95rem;">Mobile application built to quickly analyze and identify specific species via camera input.</p>
                    <div class="tags">
                        <span>Flutter</span><span>FastAPI</span><span>Python</span>
                    </div>
                </div>

                <div class="glass-card">
                    <h3 style="font-size: 1.3rem; margin-bottom: 0.5rem; color: #fff;">Blockchain Portfolio Analytics</h3>
                    <p style="color: var(--text-muted); font-size: 0.95rem;">Enterprise chatbot providing instant valuations and real-time market data insights.</p>
                    <div class="tags">
                        <span>Zoho Cliq</span><span>GoldRush API</span><span>CoinGecko API</span>
                    </div>
                </div>

                <div class="glass-card">
                    <h3 style="font-size: 1.3rem; margin-bottom: 0.5rem; color: #fff;">Fitness Buddy (GymBuddy)</h3>
                    <p style="color: var(--text-muted); font-size: 0.95rem;">Full-stack performance optimization engine with personalized algorithmic feedback.</p>
                    <div class="tags">
                        <span>React</span><span>Node.js</span><span>AI Core</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- EXPERIENCE SECTION -->
        <section class="reveal">
            <h2><i class="fas fa-briefcase gradient-text"></i> Experience & Achievements</h2>
            
            <div class="experience-grid">
                <div class="glass-card">
                    <h3 style="margin-bottom: 1.5rem; color: var(--secondary);"><i class="fas fa-laptop-code"></i> Professional Experience</h3>
                    <ul class="exp-list">
                        <li>
                            <strong>IBM SkillBuild Virtual Intern (AI/Cloud)</strong><br>
                            <span style="color: var(--text-muted); font-size: 0.9rem;">Developed cloud-integrated AI apps using IBM Watson Assistant and NLP models.</span>
                        </li>
                        <li>
                            <strong>TATA Forage Virtual Intern (Data Analytics)</strong><br>
                            <span style="color: var(--text-muted); font-size: 0.9rem;">Conducted performance analysis and data visualization on GenAI business models.</span>
                        </li>
                    </ul>
                </div>

                <div class="glass-card">
                    <h3 style="margin-bottom: 1.5rem; color: var(--primary-glow);"><i class="fas fa-certificate"></i> Certifications</h3>
                    <ul class="exp-list">
                        <li>🎓 <strong>Artificial Intelligence Professional</strong> — <em>Intellipaat</em></li>
                        <li>🧠 <strong>Generative AI Foundations</strong> — <em>UpGrad</em></li>
                        <li>🐍 <strong>Python (HCL & Google)</strong> — <em>GUVI</em></li>
                        <li>☁️ <strong>Journey to Cloud</strong> — <em>IBM SkillsBuild</em></li>
                    </ul>
                </div>
            </div>
        </section>

        <footer>
            <p>Made with ❤️ by <a href="https://linkedin.com/in/tamilarasansdeveloper/" target="_blank">TAMILARASAN</a></p>
        </footer>

    </div>

    <!-- Scroll Reveal JavaScript -->
    <script>
        document.addEventListener("DOMContentLoaded", () => {
            const reveals = document.querySelectorAll(".reveal");

            const revealOnScroll = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add("active");
                        // Optional: Stop observing once revealed
                        // observer.unobserve(entry.target); 
                    }
                });
            }, {
                threshold: 0.1, // Trigger when 10% of element is visible
                rootMargin: "0px 0px -50px 0px"
            });

            reveals.forEach(reveal => {
                revealOnScroll.observe(reveal);
            });
            
            // Trigger immediately for elements already in view on load
            setTimeout(() => {
                reveals.forEach(reveal => {
                    const rect = reveal.getBoundingClientRect();
                    if(rect.top < window.innerHeight) {
                        reveal.classList.add("active");
                    }
                });
            }, 100);
        });
    </script>
</body>
</html>
