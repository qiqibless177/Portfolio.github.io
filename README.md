<!DOCTYPE html>
<html lang="zh-CN" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minimalist Portfolio | 个人作品集</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #ffffff;
            color: #1a1a1a;
        }
        .glass {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(0, 0, 0, 0.05);
        }
        .hero-title {
            font-size: clamp(3rem, 10vw, 8rem);
            line-height: 0.9;
            letter-spacing: -0.05em;
        }
        /* 弹窗动画 */
        .modal-enter {
            opacity: 0;
            transform: translateY(30px);
        }
        .modal-enter-active {
            opacity: 1;
            transform: translateY(0);
            transition: opacity 0.5s cubic-bezier(0.16, 1, 0.3, 1), transform 0.5s cubic-bezier(0.16, 1, 0.3, 1);
        }
        /* 自定义滚动条 - 极简样式 */
        #modalScrollContainer::-webkit-scrollbar {
            width: 6px;
        }
        #modalScrollContainer::-webkit-scrollbar-thumb {
            background: rgba(255, 255, 255, 0.3);
            border-radius: 10px;
        }
        /* 隐藏滚动条但保留功能 */
        .no-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .no-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
    </style>
</head>
<body class="antialiased">

    <!-- 顶部固定导航栏 -->
    <nav class="fixed top-0 w-full z-50 transition-all duration-300 glass">
        <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
            <a href="#" class="text-xl font-extrabold tracking-tighter">DESIGNER.</a>
            <div class="hidden md:flex space-x-12 text-sm font-medium tracking-wide">
                <a href="#work" class="hover:opacity-50 transition-opacity">WORK</a>
                <a href="#about" class="hover:opacity-50 transition-opacity">ABOUT</a>
                <a href="#contact" class="hover:opacity-50 transition-opacity">CONTACT</a>
            </div>
            <button class="md:hidden" aria-label="Toggle Menu">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="3" y1="12" x2="21" y2="12"></line><line x1="3" y1="6" x2="21" y2="6"></line><line x1="3" y1="18" x2="21" y2="18"></line></svg>
            </button>
        </div>
    </nav>

    <!-- Hero 区域 -->
    <section class="min-h-screen flex flex-col justify-center px-6 pt-20">
        <div class="max-w-7xl mx-auto w-full">
            <span class="text-sm font-semibold tracking-[0.2em] text-gray-400 mb-8 block uppercase">Available for freelance</span>
            <h1 class="hero-title font-extrabold mb-12">
                CREATIVE<br/>
                <span class="text-gray-300">VISIONARY</span>
            </h1>
            <p class="max-w-xl text-xl text-gray-500 leading-relaxed font-light">
                专注于构建极简主义的数字体验。通过有目的的设计与精致的细节，连接品牌与用户。
            </p>
        </div>
    </section>

    <!-- 作品展示区域 (Work) -->
    <section id="work" class="py-32 px-6">
        <div class="max-w-7xl mx-auto">
            <div class="flex items-end justify-between mb-20">
                <h2 class="text-4xl font-extrabold tracking-tight">SELECTED WORKS</h2>
                <span class="text-gray-400 text-sm mb-1 tracking-widest"></span>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-10">
                
                <!-- 项目 1 -->
                <div class="group cursor-pointer" onclick="openModal('P1.png')">
                    <div class="aspect-[4/3] w-full overflow-hidden rounded-2xl mb-6 bg-gray-100 relative">
                        <img src="web_01.png" alt="[项目封面 01]" class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-700 ease-out">
                    </div>
                    <div class="space-y-1">
                        <h3 class="text-xl font-extrabold mb-1 group-hover:text-gray-500 transition-colors">简拼数字人</h3>
                        <p class="text-gray-400 tracking-wider text-sm">AI Video Creation Platform</p>
                    </div>
                </div>

                <!-- 项目 2 -->
                <div class="group cursor-pointer" onclick="openModal('P2.png')">
                    <div class="aspect-[4/3] w-full overflow-hidden rounded-2xl mb-6 bg-gray-100 relative">
                        <img src="sc_02.png" alt="[项目封面 02]" class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-700 ease-out">
                    </div>
                    <div class="space-y-1">
                        <h3 class="text-xl font-extrabold mb-1 group-hover:text-gray-500 transition-colors">soulchill改版升级</h3>
                        <p class="text-gray-400 tracking-wider text-sm">Soulchill Revamped And Upgraded</p>
                    </div>
                </div>

                <!-- 项目 3 -->
                <div class="group cursor-pointer" onclick="openModal('P3.png')">
                    <div class="aspect-[4/3] w-full overflow-hidden rounded-2xl mb-6 bg-gray-100 relative">
                        <img src="ren_03.png" alt="[项目封面 03]" class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-700 ease-out">
                    </div>
                    <div class="space-y-1">
                        <h3 class="text-xl font-extrabold mb-1 group-hover:text-gray-500 transition-colors">人人讲</h3>
                        <p class="text-gray-400 tracking-wider text-sm">MRenrenjiang APPh</p>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- 关于区域 -->
    <section id="about" class="py-32 px-6 bg-gray-50">
        <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-16">
            <div><h2 class="text-4xl font-extrabold mb-8">ABOUT ME</h2></div>
            <div class="space-y-6 text-xl text-gray-600 font-light leading-relaxed">
                <p>我是一名独立设计师，致力于将复杂的概念转化为清晰、直观的视觉语言。</p>
            </div>
        </div>
    </section>

    <!-- 联系区域 - 邮箱字号大幅缩小 (约原有的1/3) -->
    <section id="contact" class="py-48 px-6">
        <div class="max-w-7xl mx-auto text-center">
            <h2 class="text-sm font-bold tracking-[0.3em] text-gray-400 mb-8 uppercase">Let's connect</h2>
            <a href="mailto:hello@minimalist.design" class="text-lg md:text-xl font-bold hover:text-gray-400 transition-colors duration-300 underline underline-offset-[8px] decoration-1 tracking-wider uppercase">
                hello@minimalist.design
            </a>
            <div class="mt-32 pt-10 border-t border-gray-100 flex flex-col md:flex-row justify-between items-center text-xs text-gray-400 uppercase tracking-widest gap-4">
                <p>© 2024 All rights reserved.</p>
                <p class="cursor-pointer hover:text-black" onclick="window.scrollTo(0,0)">返回顶部 ↑</p>
            </div>
        </div>
    </section>

    <!-- 长图预览弹窗 -->
    <div id="projectModal" class="fixed inset-0 z-[100] hidden flex-col items-center justify-start overflow-hidden">
        <!-- 半透明背景遮罩 -->
        <div class="absolute inset-0 bg-black/90 backdrop-blur-md" onclick="closeModal()"></div>
        
        <!-- 右上角关闭按钮 -->
        <button onclick="closeModal()" class="fixed top-8 right-8 z-[110] bg-white/10 hover:bg-white/25 backdrop-blur-md text-white rounded-full p-3 transition-all duration-300 shadow-xl">
            <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
        </button>
        
        <!-- 图片滚动容器 -->
        <div id="modalScrollContainer" class="relative w-full max-w-5xl h-screen overflow-y-auto pt-10 pb-20 px-4 md:px-0 z-[105] no-scrollbar">
            <div id="modalContent" class="modal-enter">
                <!-- 展示长图的 img 标签 -->
                <img id="modalImg" src="" alt="[作品预览长图]" class="w-full h-auto rounded-xl shadow-2xl">
            </div>
        </div>
    </div>

    <script>
        // 导航栏滚动逻辑
        window.addEventListener('scroll', () => {
            const nav = document.querySelector('nav');
            if (window.scrollY > 50) {
                nav.classList.add('py-4');
                nav.style.backgroundColor = 'rgba(255, 255, 255, 0.9)';
            } else {
                nav.classList.remove('py-4');
                nav.style.backgroundColor = 'rgba(255, 255, 255, 0.7)';
            }
        });

        // 弹窗控制逻辑
        const modal = document.getElementById('projectModal');
        const modalContent = document.getElementById('modalContent');
        const modalImg = document.getElementById('modalImg');
        const scrollContainer = document.getElementById('modalScrollContainer');

        function openModal(longImgSrc) {
            // 设置要展示的长图路径
            modalImg.src = longImgSrc;
            
            modal.classList.remove('hidden');
            modal.classList.add('flex');
            
            // 确保每次打开都从顶部开始看
            scrollContainer.scrollTop = 0;
            
            // 触发入场动画
            setTimeout(() => {
                modalContent.classList.remove('modal-enter');
                modalContent.classList.add('modal-enter-active');
            }, 50);
            
            // 禁止背景页面滚动
            document.body.style.overflow = 'hidden';
        }

        function closeModal() {
            modalContent.classList.remove('modal-enter-active');
            modalContent.classList.add('modal-enter');
            
            setTimeout(() => {
                modal.classList.add('hidden');
                modal.classList.remove('flex');
                document.body.style.overflow = 'auto';
            }, 400);
        }

        // 支持 ESC 键关闭
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape') closeModal();
        });
    </script>
</body>
</html>
