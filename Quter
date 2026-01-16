<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quter 搜索 - 轻量极简搜索体验</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Microsoft YaHei", sans-serif;
        }
        body {
            background-color: #f5f5f5;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }
        header {
            padding: 1.2rem 2rem;
            background-color: #fff;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
        }
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #4285f4;
        }
        .main {
            flex: 1;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 2rem;
        }
        .search-box {
            width: 100%;
            max-width: 600px;
            margin-top: 2rem;
            position: relative;
        }
        .search-input {
            width: 100%;
            padding: 1rem 1.5rem;
            border: 1px solid #ddd;
            border-radius: 30px;
            font-size: 1.1rem;
            outline: none;
            transition: box-shadow 0.3s;
        }
        .search-input:focus {
            box-shadow: 0 0 5px rgba(66, 133, 244, 0.5);
            border-color: #4285f4;
        }
        .search-btn {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            background: none;
            border: none;
            color: #4285f4;
            font-size: 1.2rem;
            cursor: pointer;
        }
        .engine-switch {
            margin-top: 1.5rem;
            display: flex;
            gap: 1.5rem;
        }
        .engine-btn {
            padding: 0.5rem 1rem;
            border: 1px solid #ddd;
            border-radius: 20px;
            background-color: #fff;
            color: #333;
            cursor: pointer;
            transition: all 0.3s;
        }
        .engine-btn.active {
            background-color: #4285f4;
            color: #fff;
            border-color: #4285f4;
        }
        footer {
            text-align: center;
            padding: 1.5rem;
            color: #666;
            font-size: 0.9rem;
        }
        @media (max-width: 768px) {
            .search-box {
                max-width: 90%;
            }
            .engine-switch {
                flex-wrap: wrap;
                justify-content: center;
                gap: 0.8rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="logo">Quter 搜索</div>
    </header>
    <div class="main">
        <h1 style="color: #4285f4; font-size: 3rem;">Quter</h1>
        <div class="search-box">
            <input type="text" class="search-input" id="searchInput" placeholder="输入关键词开始搜索...">
            <button class="search-btn" id="searchBtn">🔍</button>
        </div>
        <div class="engine-switch">
            <button class="engine-btn active" data-engine="baidu">百度</button>
            <button class="engine-btn" data-engine="bing">必应</button>
            <button class="engine-btn" data-engine="google">谷歌</button>
        </div>
    </div>
    <footer>
        <p>© 2025 Quter 浏览器 版权所有</p>
    </footer>

    <script>
        // 获取元素
        const searchInput = document.getElementById('searchInput');
        const searchBtn = document.getElementById('searchBtn');
        const engineBtns = document.querySelectorAll('.engine-btn');
        let currentEngine = 'baidu';

        // 切换搜索引擎
        engineBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                engineBtns.forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
                currentEngine = btn.dataset.engine;
            });
        });

        // 搜索功能
        function doSearch() {
            const keyword = searchInput.value.trim();
            if (!keyword) return;

            let searchUrl = '';
            switch(currentEngine) {
                case 'baidu':
                    searchUrl = `https://www.baidu.com/s?wd=${encodeURIComponent(keyword)}`;
                    break;
                case 'bing':
                    searchUrl = `https://cn.bing.com/search?q=${encodeURIComponent(keyword)}`;
                    break;
                case 'google':
                    searchUrl = `https://www.google.com/search?q=${encodeURIComponent(keyword)}`;
                    break;
            }
            window.open(searchUrl, '_blank');
        }

        // 绑定事件
        searchBtn.addEventListener('click', doSearch);
        searchInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') doSearch();
        });
    </script>
</body>
</html>
