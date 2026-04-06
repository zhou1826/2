<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>灵刻纪元 · 无色觉醒者 | 官方概念站</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;400;500;600;700;800&family=Playfair+Display:wght@700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: #05020c;
            font-family: 'Inter', sans-serif;
            color: #edeef7;
            line-height: 1.5;
            scroll-behavior: smooth;
        }
        /* 高级灵脉动态背景 */
        .bg-aura {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 30% 20%, #0f0a24, #010004);
            z-index: -2;
        }
        .bg-aura::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background-image: radial-gradient(rgba(120, 80, 200, 0.15) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: slowDrift 60s linear infinite;
            pointer-events: none;
        }
        @keyframes slowDrift {
            0% { transform: translate(0,0);}
            100% { transform: translate(10%, 10%);}
        }
        /* 导航栏高级玻璃质感 */
        .navbar {
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(20px);
            background: rgba(8, 5, 20, 0.6);
            border-bottom: 1px solid rgba(140, 100, 220, 0.3);
            padding: 0.8rem 2rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            gap: 1rem;
        }
        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            background: linear-gradient(135deg, #fff, #b47cff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: 1px;
        }
        .nav-links {
            display: flex;
            gap: 1.5rem;
            flex-wrap: wrap;
            align-items: center;
        }
        .nav-links a {
            color: #e0d6ff;
            text-decoration: none;
            font-weight: 500;
            transition: 0.2s;
            font-size: 0.9rem;
        }
        .nav-links a:hover { color: #c195ff; text-shadow: 0 0 5px #a06eff; }
        .guide-nav-btn, .lang-nav-btn, .preorder-nav-btn {
            background: rgba(42, 31, 82, 0.8);
            border: none;
            padding: 0.4rem 1.2rem;
            border-radius: 40px;
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.25s;
            font-size: 0.85rem;
            backdrop-filter: blur(4px);
        }
        .guide-nav-btn { background: #6d44b0; }
        .preorder-nav-btn { background: #c77d1e; box-shadow: 0 0 8px #ffa047; }
        .guide-nav-btn:hover, .lang-nav-btn:hover { background: #8c5ee0; transform: scale(0.98); }
        .preorder-nav-btn:hover { background: #e6942c; box-shadow: 0 0 15px #ffb347; transform: scale(1.02); }
        
        /* 容器 */
        .container { max-width: 1300px; margin: 0 auto; padding: 2rem 2rem 4rem; }
        .section { margin: 5rem 0; scroll-margin-top: 80px; }
        .section-title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 1.8rem;
            border-left: 5px solid #a06eff;
            padding-left: 1.2rem;
            background: linear-gradient(90deg, #2e225b, transparent);
            display: inline-block;
            font-family: 'Playfair Display', serif;
        }
        /* 高级卡片网格 */
        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.8rem;
            margin-top: 1rem;
        }
        .job-card {
            background: rgba(20, 14, 42, 0.6);
            backdrop-filter: blur(8px);
            border-radius: 1.5rem;
            padding: 1.4rem;
            border: 1px solid rgba(70, 50, 130, 0.5);
            transition: all 0.35s cubic-bezier(0.2, 0.9, 0.4, 1.1);
        }
        .job-card:hover {
            transform: translateY(-8px);
            border-color: #c195ff;
            background: rgba(30, 20, 60, 0.8);
            box-shadow: 0 20px 35px -12px #000000cc, 0 0 0 1px rgba(161, 109, 255, 0.3);
        }
        .job-card h3 { font-size: 1.5rem; color: #e1ccff; margin-bottom: 0.5rem; font-weight: 600; }
        .badge {
            background: #382c6e;
            display: inline-block;
            border-radius: 30px;
            padding: 0.2rem 0.9rem;
            font-size: 0.7rem;
            font-weight: 600;
            margin-top: 0.6rem;
        }
        .info-table {
            width: 100%;
            background: rgba(10, 7, 34, 0.7);
            backdrop-filter: blur(4px);
            border-radius: 1.2rem;
            overflow: hidden;
            border-collapse: collapse;
        }
        .info-table th, .info-table td {
            padding: 0.9rem;
            border-bottom: 1px solid #332a66;
            text-align: left;
        }
        .info-table th { background: #19113d; color: #cfbaff; font-weight: 600; }
        .reward-list { display: flex; flex-wrap: wrap; gap: 0.7rem; margin: 1.2rem 0; }
        .reward-tag {
            background: #1f174e;
            border-radius: 30px;
            padding: 0.3rem 1.2rem;
            font-size: 0.8rem;
            transition: 0.2s;
        }
        .reward-tag:hover { background: #4a3790; transform: scale(1.02); }
        
        /* 攻略浮层 */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(12px);
            z-index: 1000;
            display: flex;
            align-items: center;
            justify-content: center;
            visibility: hidden;
            opacity: 0;
            transition: 0.2s;
        }
        .modal-overlay.active { visibility: visible; opacity: 1; }
        .modal-card {
            background: linear-gradient(145deg, #1f1a3c, #110c28);
            border-radius: 2rem;
            max-width: 720px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
            padding: 2rem;
            border: 1px solid #8b68da;
            box-shadow: 0 25px 50px rgba(0,0,0,0.5);
        }
        .modal-card h3 { font-size: 1.8rem; margin-bottom: 1rem; color: #e3cdff; font-family: 'Playfair Display', serif; }
        .modal-card h4 { margin: 1rem 0 0.4rem; color: #c2a2ff; }
        .close-modal {
            float: right;
            background: none;
            border: none;
            font-size: 2rem;
            color: #ccc2ff;
            cursor: pointer;
        }
        
        /* Footer 高级多栏 */
        footer {
            background: rgba(6, 3, 18, 0.8);
            backdrop-filter: blur(8px);
            border-top: 1px solid #312763;
            padding: 2.5rem 2rem 1.5rem;
            margin-top: 3rem;
        }
        .footer-inner {
            max-width: 1300px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 2rem;
        }
        .footer-col h4 { color: #e0cdff; margin-bottom: 1rem; font-size: 1.2rem; font-weight: 600; border-left: 3px solid #a06eff; padding-left: 0.8rem; }
        .footer-col p, .footer-col li { font-size: 0.85rem; color: #bcb5e6; margin-bottom: 0.5rem; list-style: none; }
        .footer-col ul { padding-left: 0; }
        .footer-col i { margin-right: 0.6rem; color: #b17eff; width: 1.4rem; }
        .copyright { grid-column: 1 / -1; text-align: center; margin-top: 2rem; font-size: 0.75rem; color: #7a70aa; border-top: 1px solid #2a2355; padding-top: 1.2rem; }
        
        /* 英雄区大图背景 + 字体 */
        .hero-section {
            text-align: center;
            margin: 1rem 0 3rem;
            position: relative;
            padding: 10rem 1rem;
            background-size: cover;
            border-radius: 2rem;
            backdrop-filter: blur(2px);
			overflow: hidden;
        }
        .hero-title {
            font-size: 4.2rem;
            font-weight: 800;
            background: linear-gradient(135deg, #FFF8E7, #dbb0ff, #9f6eff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 2px 15px rgba(0,0,0,0.5);
            font-family: 'Playfair Display', serif;
            letter-spacing: 2px;
        }
        .hero-sub {
            font-size: 1.3rem;
            color: #d9caff;
            margin-top: 0.5rem;
            font-weight: 500;
        }
        .hero-desc {
            max-width: 700px;
            margin: 1rem auto;
            color: #e0d6ff;
            font-size: 1rem;
        }
        @media (max-width: 780px) {
            .navbar { flex-direction: column; align-items: stretch; text-align: center; }
            .nav-links { justify-content: center; }
            .container { padding: 1rem; }
            .hero-title { font-size: 2.5rem; }
            .footer-inner { grid-template-columns: 1fr; }
        }
        @keyframes btnPulse {
            0% { box-shadow: 0 0 0 0 #ffa047; }
            70% { box-shadow: 0 0 0 10px rgba(255, 160, 71, 0); }
            100% { box-shadow: 0 0 0 0 rgba(255, 160, 71, 0); }
        }
        .preorder-nav-btn { animation: btnPulse 1.8s infinite; }
		
		
		/* Hero 标题流光动画 */
@keyframes shineText {
    0% { background-position: -500% 0; }
    100% { background-position: 500% 0; }
}

.hero-title {
    background: linear-gradient(90deg, #FFF8E7, #dbb0ff, #9f6eff, #FFF8E7);
    background-size: 200% 100%;
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    animation: shineText 4s linear infinite;
}

/* Section 标题淡入滑动 */
@keyframes fadeInUp {
    0% { opacity: 0; transform: translateY(20px); }
    100% { opacity: 1; transform: translateY(0); }
}

.section-title {
    opacity: 0; /* 初始隐藏 */
    animation: fadeInUp 1s ease forwards;
}

/* 滚动到标题时触发 */
.section-title.visible {
    opacity: 1;
    animation: fadeInUp 1s ease forwards;
}


.hero-section {
    position: relative;
    overflow: hidden;
}

.hero-section::before {
    content: '';
    position: absolute;
    width: 200%;
    height: 200%;
    top: -50%;
    left: -50%;
    background: radial-gradient(circle, rgba(255,255,255,0.05) 1px, transparent 1px);
    background-size: 40px 40px;
    animation: drift 120s linear infinite;
    z-index: -1;
}

@keyframes drift {
    0% { transform: translate(0,0); }
    100% { transform: translate(20%, 20%); }
}

.hero-title {
    font-size: 4.2rem;
    font-weight: 800;
    background: linear-gradient(270deg, #FFF8E7, #dbb0ff, #9f6eff, #FFF8E7);
    background-size: 600% 100%;
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    animation: shineText 6s linear infinite, glowPulse 2.5s ease-in-out infinite alternate;
    text-shadow: 0 0 15px rgba(159,110,255,0.6), 0 0 30px rgba(219,176,255,0.4);
}

@keyframes shineText {
    0% { background-position: 0% 50%; }
    100% { background-position: 100% 50%; }
}

@keyframes glowPulse {
    0% { text-shadow: 0 0 10px rgba(159,110,255,0.3); }
    100% { text-shadow: 0 0 25px rgba(219,176,255,0.8); }
}

.floating-particles {
    position: absolute;
    top:0; left:0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    background-image: radial-gradient(circle, rgba(255,255,255,0.05) 1px, transparent 1px);
    background-size: 20px 20px;
    animation: particleMove 80s linear infinite;
    z-index: -1;
}

@keyframes particleMove {
    0% { transform: translate(0,0); }
    100% { transform: translate(50px,50px); }
}

    </style>
</head>
<body>
<div class="bg-aura"></div>
<div class="navbar">
    <div class="logo"><i class="fas fa-dragon"></i> 灵刻纪元 | Chrono Inscript</div>
    <div class="nav-links">
        <a href="#story" data-i18n-key="nav_story">剧情</a>
        <a href="#classes" data-i18n-key="nav_classes">职业</a>
        <a href="#dungeons" data-i18n-key="nav_dungeons">副本&奖励</a>
        <a href="#npc" data-i18n-key="nav_npc">阵营</a>
        <a href="#features" data-i18n-key="nav_features">特色</a>
        <button class="guide-nav-btn" id="navGuideBtn"><i class="fas fa-map"></i> <span data-i18n-key="guide_btn">游戏攻略</span></button>
        <button class="lang-nav-btn" id="navLangBtn"><i class="fas fa-globe"></i> EN / 中文</button>
        <button class="preorder-nav-btn" id="preorderBtn"><i class="fas fa-crown"></i> <span data-i18n-key="preorder_btn">立即预购</span></button>
    </div>
</div>

<div class="container">
    <!-- 英雄区 带图片感背景 -->
    <div class="hero-section">
        <h1 class="hero-title" data-i18n-key="hero_title">灵刻纪元</h1>
        <p class="hero-sub" data-i18n-key="hero_sub">无色觉醒 · 灵潮将至 · 刻印万象</p>
        <p class="hero-desc" data-i18n-key="hero_desc">千年前渊眼撕裂苍穹，灵质降临。你是唯一无色灵核觉醒者，三年后灵潮再临，抉择世界命运。</p>
        <div style="display: flex; gap: 0.8rem; justify-content: center; margin-top: 1rem;">
            <span class="badge" data-i18n-key="badge1">🎮 开放世界RPG</span>
            <span class="badge" data-i18n-key="badge2">⚡ 职业融合</span>
            <span class="badge" data-i18n-key="badge3">📖 多结局</span>
        </div>
		<!-- 浮动粒子 -->
    <div class="floating-particles"></div>
    </div>

    <!-- 剧情 -->
    <div id="story" class="section">
        <div class="section-title" data-i18n-key="story_title">📜 灵潮编年史 · 主线</div>
        <div class="card-grid" id="storyGrid">
            <div class="job-card"><h3 data-i18n-key="story1_t">序章 · 无色觉醒</h3><p data-i18n-key="story1_d">渊眼教团夜袭灵刻学院，你坠入禁地触碰「源初灵刻」，无色灵核觉醒，成为零号觉醒者。</p></div>
            <div class="job-card"><h3 data-i18n-key="story2_t">第一章 · 三路试炼</h3><p data-i18n-key="story2_d">法理回廊、断剑峡谷、影渊之巢，融合法师、剑士、暗夜之力，稳定灵核并揭开千年轮回。</p></div>
            <div class="job-card"><h3 data-i18n-key="story3_t">第二章 · 灵骸之影</h3><p data-i18n-key="story3_d">灵潮异变，青梅竹马艾蕾娜濒临堕落，昔日战友成为最大威胁，人性与力量的拷问。</p></div>
            <div class="job-card"><h3 data-i18n-key="story4_t">终章 · 渊眼抉择</h3><p data-i18n-key="story4_d">关闭裂隙、维持循环或成为新法则，七种结局等待你的刻印。</p></div>
        </div>
        <p style="margin-top: 1rem; background: #0e0b23; border-radius: 1rem; padding: 0.6rem 1rem;" data-i18n-key="story_time">⭐ 主线约35小时 | 全职业融合+隐藏结局 ≈ 70小时</p>
    </div>

    <!-- 职业数据 -->
    <div id="classes" class="section">
        <div class="section-title" data-i18n-key="classes_title">⚔️ 灵刻职业 · 六道传承</div>
        <p style="margin-bottom: 1rem;" data-i18n-key="classes_note">✨ 无色灵核特性：可复制并融合任意职业技能，突破职业界限。</p>
        <h3 style="margin:1rem 0 0.5rem;" data-i18n-key="mage_title">🧙 法师系</h3>
        <div class="card-grid" id="mageGrid"></div>
        <h3 style="margin:1.5rem 0 0.5rem;" data-i18n-key="sword_title">🗡️ 剑士系</h3>
        <div class="card-grid" id="swordGrid"></div>
        <h3 style="margin:1.5rem 0 0.5rem;" data-i18n-key="other_title">🔫 枪手系 · 🥋 格斗系 · 🌙 暗夜系 · ⛪ 圣职系</h3>
        <div class="card-grid" id="otherGrid"></div>
    </div>

    <!-- 副本 -->
    <div id="dungeons" class="section">
        <div class="section-title" data-i18n-key="dungeon_title">🏛️ 灵墟副本 · 迷雾回廊</div>
        <p data-i18n-key="dungeon_desc">副本内包含迷雾探索、随机事件、耐力消耗及独特BOSS机制。通关可获得大量灵刻传承与稀有装备。</p>
        <div style="margin: 1rem 0;"><span class="badge" data-i18n-key="daily">每日重置：普通/困难</span> <span class="badge" data-i18n-key="weekly">每周重置：精英副本</span> <span class="badge" data-i18n-key="hidden">隐藏副本：特殊触发</span></div>
        <h3 style="margin: 1rem 0 0.5rem;" data-i18n-key="reward_title">🎁 副本奖励一览（核心掉落）</h3>
        <table class="info-table" id="rewardTable">
            <thead><tr><th data-i18n-key="dungeon_col">副本名称</th><th data-i18n-key="drop_col">主要掉落</th><th data-i18n-key="rare_col">稀有奖励/概率</th></tr></thead>
            <tbody id="rewardBody"></tbody>
        </table>
        <div class="reward-list" id="rewardTags"></div>
    </div>

    <!-- 阵营+NPC -->
    <div id="npc" class="section">
        <div class="section-title" data-i18n-key="npc_title">🧩 世界阵营 & 关键人物</div>
        <table class="info-table" id="npcTable"><thead><tr><th data-i18n-key="char_col">角色</th><th data-i18n-key="class_col">职业</th><th data-i18n-key="role_col">关联/剧情作用</th></tr></thead><tbody id="npcBody"></tbody></table>
        <div class="card-grid" style="margin-top:1.2rem;" id="factionGrid"></div>
    </div>

    <!-- 特色系统 -->
    <div id="features" class="section">
        <div class="section-title" data-i18n-key="feature_title">⚙️ 传说装备 & 核心特色</div>
        <div class="card-grid" id="legendaryGrid"></div>
        <div style="margin-top: 2rem;"><div class="section-title" style="font-size:1.6rem;" data-i18n-key="system_title">✨ 独创系统</div><div class="card-grid" id="systemGrid"></div></div>
    </div>
</div>

<!-- Footer 高级区块 -->
<footer>
    <div class="footer-inner">
        <div class="footer-col">
            <h4><i class="fas fa-users"></i> <span data-i18n-key="guild_title">公会机制</span></h4>
            <p data-i18n-key="guild_desc1">• 创建或加入灵刻公会，最多50人</p>
            <p data-i18n-key="guild_desc2">• 公会专属副本「灵脉远征」周常开放</p>
            <p data-i18n-key="guild_desc3">• 公会技能树：提升灵刻融合成功率</p>
            <p data-i18n-key="guild_desc4">• 公会战：灵潮争夺战，跨服排名奖励</p>
        </div>
        <div class="footer-col">
            <h4><i class="fas fa-user-friends"></i> <span data-i18n-key="friend_title">好友机制</span></h4>
            <p data-i18n-key="friend_desc1">• 双人刻印：与好友组队获得额外羁绊经验</p>
            <p data-i18n-key="friend_desc2">• 灵核共鸣：好友间可借用彼此一个技能</p>
            <p data-i18n-key="friend_desc3">• 赠送礼物系统提升灵契值，解锁表情动作</p>
            <p data-i18n-key="friend_desc4">• 跨服好友 & 实时语音协作</p>
        </div>
        <div class="footer-col">
            <h4><i class="fas fa-desktop"></i> <span data-i18n-key="spec_title">推荐配置</span></h4>
            <p data-i18n-key="spec_min"><strong>最低配置</strong> (1080p 30fps)</p>
            <p data-i18n-key="spec_min_cpu">• CPU: Intel i5-8400 / AMD R5 2600</p>
            <p data-i18n-key="spec_min_gpu">• GPU: GTX 1060 6GB / RX 580</p>
            <p data-i18n-key="spec_min_ram">• RAM: 8GB | 存储: 50GB SSD</p>
            <p data-i18n-key="spec_rec"><strong>推荐配置</strong> (2K 60fps)</p>
            <p data-i18n-key="spec_rec_cpu">• CPU: Intel i7-10700K / R7 3700X</p>
            <p data-i18n-key="spec_rec_gpu">• GPU: RTX 3060 Ti / RX 6700 XT</p>
            <p data-i18n-key="spec_rec_ram">• RAM: 16GB | 存储: 50GB NVMe SSD</p>
        </div>
        <div class="copyright">
            <p data-i18n-key="footer_copyright">© 灵刻工坊 · 愿望单即将开启 | 距离下一次灵潮：三年 | 官网持续更新</p>
        </div>
    </div>
</footer>

<!-- 攻略浮层 (双语完整) -->
<div id="guideModal" class="modal-overlay">
    <div class="modal-card">
        <button class="close-modal" id="closeModalBtn">&times;</button>
        <div id="guideContent"></div>
    </div>
</div>

<script>
    // ---------- 静态数据 ----------
    const mageData = [{name:"战斗法师",desc:"长棍/战矛 · 魔法强化自身，近战狂猛输出",tag:"武器：长棍/战矛"},{name:"魔道学者",desc:"魔法道具战斗，控制+持续伤害，兼具近战能力",tag:"控制/持续"},{name:"元素法师",desc:"光暗冰火四系，远程AOE毁灭者",tag:"高爆发·范围"},{name:"召唤师",desc:"召唤生物协同，多线操作，战术多变",tag:"操作上限高"}];
    const swordData = [{name:"狂剑士",desc:"嗜血越战越强，近战高爆发"},{name:"剑客",desc:"高机动连招，极致操作感"},{name:"魔剑士",desc:"魔法+物理混合，远程剑气"},{name:"鬼剑士",desc:"结界召唤阵，攻防兼备辅控"}];
    const otherData = [{name:"神枪手",desc:"体术+射击灵活"},{name:"弹药专家",desc:"特殊子弹控爆，惧近战"},{name:"机械师",desc:"机械大军持续输出"},{name:"枪炮师",desc:"超远程范围毁灭"},{name:"拳法家",desc:"近战爆发最强，距离短"},{name:"流氓",desc:"多控制扰乱敌人"},{name:"柔道",desc:"抓取技，控制+爆发"},{name:"气功师",desc:"内功远程，可辅可输出"},{name:"忍者",desc:"结印高爆发，暗杀术"},{name:"盗贼",desc:"陷阱+控制，机动性强"},{name:"刺客",desc:"单体秒杀，高风险高收益"},{name:"术士",desc:"咒术/召唤/持续伤害"},{name:"牧师",desc:"治疗复活，团队核心"},{name:"骑士",desc:"高防坦克，吸收伤害"},{name:"守护天使",desc:"极强保护，分担伤害"},{name:"驱魔师",desc:"符咒法术，控场输出"}];
    const rewardData = [{dungeon:"法理回廊",drops:"元素核心、法师专修书",rare:"传说法杖「灵脉咏者」、无色灵核稳定剂"},{dungeon:"影渊之巢",drops:"暗夜系刻印碎片、陷阱图纸",rare:"传说匕首「渊痕」、灵骸契约残页"},{dungeon:"断剑峡谷·英灵殿",drops:"战士/剑士灵刻、狂血药剂",rare:"鬼剑士专属结界「鬼哭之刻」、源初晶石"},{dungeon:"灵潮祭坛（精英）",drops:"传说装备胚子、高阶融合石",rare:"技能书「灵刻·万象」——可复制任意职业技能"},{dungeon:"第七封印（隐藏）",drops:"轮回记忆碎片、时空沙漏",rare:"唯一道具「创世刻印」→ 触发隐藏结局"}];
    const rewardTags = ["✨ 源初灵刻碎片","⚙️ 职业融合石","📖 远古记忆残章","💎 灵质精髓(强化无色核)","🏆 传说套装「灵骸仲裁者」"];
    const npcData = [{name:"艾蕾娜",class:"守护天使",role:"青梅竹马，后期可能堕为灵骸，影响关键结局"},{name:"卡恩",class:"狂剑士",role:"竞争对手→战友，力量至上主义者"},{name:"维奥拉",class:"魔道学者",role:"学院导师，渊眼教团卧底但对你抱有真情"},{name:"“灰”",class:"刺客",role:"灵骸猎团成员，揭示灵骸仍存意识"},{name:"老院长",class:"刻印贤者",role:"创造你的存在，千年前封印渊眼之人"}];
    const factions = [{name:"⚜️ 灵刻学院",desc:"中立最高学府，培养觉醒者，暗中平衡世界"},{name:"🌙 渊眼教团",desc:"崇拜灵质，视灵潮为进化，渗透各国"},{name:"⚔️ 灵骸猎团",desc:"压制灵核，猎杀失控灵骸，灰色地带游走"}];
    const legendary = [{name:"碎星武僧·长棍",desc:"战斗法师技能「灵棍裂地」追加三段冲击波"},{name:"因果罗盘",desc:"魔道学者持续伤害延长50%，随机重置控制技CD"},{name:"无色之瞳·项链",desc:"唯一传说，逆灵刻值累积速度降低30%"},{name:"不朽壁垒·盾",desc:"骑士「最后的堡垒」为全队附加50%最大生命护盾"}];
    const systems = [{name:"灵刻融合",desc:"双职业技能组合，创造上千种原创战技",icon:"fa-fusion"},{name:"逆灵刻值系统",desc:"过度使用无色之力将堕为灵骸，风险与回报并存",icon:"fa-skull"},{name:"羁绊刻印",desc:"NPC好感影响结局，解锁特殊融合技",icon:"fa-hand-holding-heart"},{name:"灵骸化变身",desc:"逆灵值爆发时临时进入暴走形态，战力暴涨但失控",icon:"fa-dragon"}];
    
    function renderStatic() {
        document.getElementById('mageGrid').innerHTML = mageData.map(d => `<div class="job-card"><h3>${d.name}</h3><p>${d.desc}</p><div class="badge">${d.tag||''}</div></div>`).join('');
        document.getElementById('swordGrid').innerHTML = swordData.map(d => `<div class="job-card"><h3>${d.name}</h3><p>${d.desc}</p></div>`).join('');
        document.getElementById('otherGrid').innerHTML = otherData.map(d => `<div class="job-card"><h3>${d.name}</h3><p>${d.desc}</p></div>`).join('');
        document.getElementById('rewardBody').innerHTML = rewardData.map(r => `<tr><td>${r.dungeon}</td><td>${r.drops}</td><td>${r.rare}</td>`).join('');
        document.getElementById('rewardTags').innerHTML = rewardTags.map(t => `<span class="reward-tag">${t}</span>`).join('');
        document.getElementById('npcBody').innerHTML = npcData.map(n => `<tr><td>${n.name}</td><td>${n.class}</td><td>${n.role}</td>`).join('');
        document.getElementById('factionGrid').innerHTML = factions.map(f => `<div class="job-card"><h3>${f.name}</h3><p>${f.desc}</p></div>`).join('');
        document.getElementById('legendaryGrid').innerHTML = legendary.map(l => `<div class="job-card"><h3>${l.name}</h3><p>${l.desc}</p></div>`).join('');
        document.getElementById('systemGrid').innerHTML = systems.map(s => `<div class="job-card"><i class="fas ${s.icon}"></i> <strong>${s.name}</strong> — ${s.desc}</div>`).join('');
    }
    renderStatic();

    // 攻略双语内容
    const guideText = {
        zh: `<h3><i class="fas fa-book-atlas"></i> 无色觉醒者攻略·灵潮秘典</h3>
            <h4>🔰 开局/职业融合建议</h4><p>✔ 初期推荐优先融合「骑士」或「牧师」提升容错，无色灵核先复制防御/治疗技能降低逆灵刻风险。<br>✔ 战斗法师+柔道：利用近战魔法强化+抓取技形成连控，完美克制精英怪。</p>
            <h4>⚡ 灵核稳定技巧</h4><p>⭐ 收集「源初灵刻碎片」——完成三路试炼后前往隐藏副本「勒芒的回忆」，每集齐3块可永久降低逆灵刻值。与艾蕾娜好感度达到“羁绊”后触发净化仪式，获得特殊被动「灵光护体」。</p>
            <h4>📌 关键BOSS对策</h4><p>▪ 法理回廊·元素悖论：使用魔剑士远程切换元素破盾，或召唤师分散仇恨。<br>▪ 影渊之巢·暗影编织者：刺客潜行+弹药专家闪光弹打断全屏大招，推荐携带驱魔师符咒解诅咒。<br>▪ 最终渊眼守卫：必须使用融合技能「光暗调和」破除无敌，推荐提前学习守护天使+术士咒术组合。</p>
            <h4>🌀 隐藏结局「无色之王」触发条件</h4><p>① 集齐七块「源初灵刻残片」；② 至少掌握六个不同职业的最终技能；③ 将“灰”好感度提升至满级并完成他的个人剧情；④ 在最终渊眼前选择「撕毁剧本，走出循环」。即可打破第四面墙，成为法则本身。</p>
            <h4>🎁 速刷资源小贴士</h4><p>每日重置副本「灵脉矿洞」掉落大量灵质结晶，可在学院兑换传说装备图纸；周常「精英·元素祭坛」必掉职业融合石。</p>`,
        en: `<h3><i class="fas fa-book-atlas"></i> Colorless Awakener Guide · Aether Tome</h3>
            <h4>🔰 Early Game / Class Fusion Tips</h4><p>✔ Start by fusing "Knight" or "Priest" for survivability. Copy defensive/healing skills to lower Reverse-Inscript risk.<br>✔ Battle Mage + Judo: Use melee magic enhancement + grapple to control elites.</p>
            <h4>⚡ Core Stabilization</h4><p>⭐ Collect "Primordial Inscript Fragments" — after the three trials, go to hidden dungeon "Reminiscence of Lemang". Every 3 fragments permanently reduce Reverse-Inscript value. Reach max bond with Erena to trigger purification and gain passive "Aether Guard".</p>
            <h4>📌 Key Boss Strategies</h4><p>▪ Mage Corridor - Elemental Paradox: Use Spellblade's ranged element break or Summoner's distraction.<br>▪ Shadow Nest - Weavebreaker: Assassin stealth + Munitions Expert flashbang to interrupt ultimate; bring Exorcist seals to remove curses.<br>▪ Final Abyss Guardian: Must use fusion skill "Light & Dark Harmony" to break invincibility; learn Guardian Angel + Warlock combo.</p>
            <h4>🌀 Hidden Ending "Colorless King" Conditions</h4><p>① Collect 7 Primordial Inscript Fragments; ② Master final skills from at least 6 different classes; ③ Max out "Grey" bond and complete his personal quest; ④ At the final choice, select "Break the script, step out of the cycle" to become the law itself.</p>
            <h4>🎁 Resource Farming Tips</h4><p>Daily dungeon "Aether Vein Mine" drops Aether Crystals for legendary blueprints. Weekly elite "Elemental Altar" guarantees class fusion stones.</p>`
    };
    document.getElementById('guideContent').innerHTML = guideText.zh;

    // 国际化完整映射
    const i18n = {
        zh: { nav_story:"剧情", nav_classes:"职业", nav_dungeons:"副本&奖励", nav_npc:"阵营", nav_features:"特色", guide_btn:"游戏攻略", preorder_btn:"立即预购", hero_title:"灵刻纪元", hero_sub:"无色觉醒 · 灵潮将至 · 刻印万象", hero_desc:"千年前渊眼撕裂苍穹，灵质降临。你是唯一无色灵核觉醒者，三年后灵潮再临，抉择世界命运。", badge1:"🎮 开放世界RPG", badge2:"⚡ 职业融合", badge3:"📖 多结局", story_title:"📜 灵潮编年史 · 主线", story1_t:"序章 · 无色觉醒", story1_d:"渊眼教团夜袭灵刻学院，你坠入禁地触碰「源初灵刻」，无色灵核觉醒，成为零号觉醒者。", story2_t:"第一章 · 三路试炼", story2_d:"法理回廊、断剑峡谷、影渊之巢，融合法师、剑士、暗夜之力，稳定灵核并揭开千年轮回。", story3_t:"第二章 · 灵骸之影", story3_d:"灵潮异变，青梅竹马艾蕾娜濒临堕落，昔日战友成为最大威胁，人性与力量的拷问。", story4_t:"终章 · 渊眼抉择", story4_d:"关闭裂隙、维持循环或成为新法则，七种结局等待你的刻印。", story_time:"⭐ 主线约35小时 | 全职业融合+隐藏结局 ≈ 70小时", classes_title:"⚔️ 灵刻职业 · 六道传承", classes_note:"✨ 无色灵核特性：可复制并融合任意职业技能，突破职业界限。", mage_title:"🧙 法师系", sword_title:"🗡️ 剑士系", other_title:"🔫 枪手系 · 🥋 格斗系 · 🌙 暗夜系 · ⛪ 圣职系", dungeon_title:"🏛️ 灵墟副本 · 迷雾回廊", dungeon_desc:"副本内包含迷雾探索、随机事件、耐力消耗及独特BOSS机制。通关可获得大量灵刻传承与稀有装备。", daily:"每日重置：普通/困难", weekly:"每周重置：精英副本", hidden:"隐藏副本：特殊触发", reward_title:"🎁 副本奖励一览（核心掉落）", dungeon_col:"副本名称", drop_col:"主要掉落", rare_col:"稀有奖励/概率", npc_title:"🧩 世界阵营 & 关键人物", char_col:"角色", class_col:"职业", role_col:"关联/剧情作用", feature_title:"⚙️ 传说装备 & 核心特色", system_title:"✨ 独创系统", guild_title:"公会机制", guild_desc1:"• 创建或加入灵刻公会，最多50人", guild_desc2:"• 公会专属副本「灵脉远征」周常开放", guild_desc3:"• 公会技能树：提升灵刻融合成功率", guild_desc4:"• 公会战：灵潮争夺战，跨服排名奖励", friend_title:"好友机制", friend_desc1:"• 双人刻印：与好友组队获得额外羁绊经验", friend_desc2:"• 灵核共鸣：好友间可借用彼此一个技能", friend_desc3:"• 赠送礼物系统提升灵契值，解锁表情动作", friend_desc4:"• 跨服好友 & 实时语音协作", spec_title:"推荐配置", spec_min:"最低配置", spec_min_cpu:"• CPU: Intel i5-8400 / AMD R5 2600", spec_min_gpu:"• GPU: GTX 1060 6GB / RX 580", spec_min_ram:"• RAM: 8GB | 存储: 50GB SSD", spec_rec:"推荐配置", spec_rec_cpu:"• CPU: Intel i7-10700K / R7 3700X", spec_rec_gpu:"• GPU: RTX 3060 Ti / RX 6700 XT", spec_rec_ram:"• RAM: 16GB | 存储: 50GB NVMe SSD", footer_copyright:"© 灵刻工坊 · 愿望单即将开启 | 距离下一次灵潮：三年 | 官网持续更新" },
        en: { nav_story:"Story", nav_classes:"Classes", nav_dungeons:"Dungeons", nav_npc:"Factions", nav_features:"Features", guide_btn:"Guide", preorder_btn:"Pre-order Now", hero_title:"Chrono Inscript", hero_sub:"Colorless Awakening · Aether Tide · Infinite Runes", hero_desc:"A thousand years ago, the Abyss Eye tore the sky. You are the only Colorless Core Awakener. The next Aether Tide comes in three years.", badge1:"🎮 Open-world RPG", badge2:"⚡ Class Fusion", badge3:"📖 Multiple Endings", story_title:"📜 Chronicle of Aether · Main Story", story1_t:"Prologue · Colorless Awakening", story1_d:"The Abyss Cult attacks the Academy. You fall into the Forbidden area and touch the Primordial Inscription — the Colorless Core awakens.", story2_t:"Chapter I · Three Trials", story2_d:"Mage Corridor, Sword Canyon, Shadow Nest — fuse three class systems to stabilize your core.", story3_t:"Chapter II · Remnant Shadow", story3_d:"The Aether Tide mutates, and your childhood friend Erena is on the verge of falling.", story4_t:"Final Chapter · Abyss Choice", story4_d:"Close the rift, sustain the cycle, or become the new law — seven endings.", story_time:"⭐ Main Story ~35h | 100% completion ~70h", classes_title:"⚔️ Classes · Six Branches", classes_note:"✨ Colorless Core: Copy and fuse any class skills, break the boundaries.", mage_title:"🧙 Mage Branch", sword_title:"🗡️ Swordsman Branch", other_title:"🔫 Gunner · 🥋 Fighter · 🌙 Nightblade · ⛪ Cleric", dungeon_title:"🏛️ Dungeons · Mist Corridors", dungeon_desc:"Fog exploration, random events, stamina & unique boss mechanics. Obtain rare inscriptions and gear.", daily:"Daily reset: Normal/Hard", weekly:"Weekly reset: Elite", hidden:"Hidden: special trigger", reward_title:"🎁 Dungeon Rewards (Core Drops)", dungeon_col:"Dungeon", drop_col:"Main Drops", rare_col:"Rare Rewards", npc_title:"🧩 Factions & Key NPCs", char_col:"Character", class_col:"Class", role_col:"Role / Plot", feature_title:"⚙️ Legendary Gear & Core Features", system_title:"✨ Unique Systems", guild_title:"Guild System", guild_desc1:"• Create/join guild, max 50 members", guild_desc2:"• Exclusive guild dungeon 'Aether Expedition' weekly", guild_desc3:"• Guild skill tree: increase fusion success rate", guild_desc4:"• Guild Wars: Aether Tide clash, cross-server ranking", friend_title:"Friendship System", friend_desc1:"• Dual Inscription: bonus bond XP when playing together", friend_desc2:"• Core Resonance: borrow one skill from a friend", friend_desc3:"• Gift system to increase bond, unlock emotes", friend_desc4:"• Cross-server friends & real-time voice", spec_title:"System Requirements", spec_min:"Minimum (1080p 30fps)", spec_min_cpu:"• CPU: Intel i5-8400 / AMD R5 2600", spec_min_gpu:"• GPU: GTX 1060 6GB / RX 580", spec_min_ram:"• RAM: 8GB | Storage: 50GB SSD", spec_rec:"Recommended (2K 60fps)", spec_rec_cpu:"• CPU: Intel i7-10700K / R7 3700X", spec_rec_gpu:"• GPU: RTX 3060 Ti / RX 6700 XT", spec_rec_ram:"• RAM: 16GB | Storage: 50GB NVMe SSD", footer_copyright:"© Lingke Studio · Wishlist soon | Next Aether Tide: 3 years | Official site" }
    };
    function setLanguage(lang) {
        const dict = i18n[lang];
        document.querySelectorAll('[data-i18n-key]').forEach(el => { const key = el.getAttribute('data-i18n-key'); if(dict[key]) el.innerText = dict[key]; });
        document.getElementById('guideContent').innerHTML = guideText[lang];
        // 职业双语
        const mageNames = lang==='en'?["Battle Mage","Arcane Scholar","Elementalist","Summoner"]:mageData.map(d=>d.name);
        const mageDescs = lang==='en'?["Staff/Spear · magic self-buff, melee powerhouse","Magic tool combat, control+DoT","Light/Dark/Ice/Fire, ranged AOE","Summon creatures, multi-unit tactics"]:mageData.map(d=>d.desc);
        document.querySelectorAll('#mageGrid .job-card').forEach((c,i)=>{ c.querySelector('h3').innerText=mageNames[i]; c.querySelector('p').innerText=mageDescs[i]; });
        const swordNames = lang==='en'?["Berserker","Swordsman","Spellblade","Ghostblade"]:swordData.map(d=>d.name);
        const swordDescs = lang==='en'?["Bloodthirsty, stronger over time","High mobility, fluid combos","Magic+physical hybrid","Barrier+summon array"]:swordData.map(d=>d.desc);
        document.querySelectorAll('#swordGrid .job-card').forEach((c,i)=>{ c.querySelector('h3').innerText=swordNames[i]; c.querySelector('p').innerText=swordDescs[i]; });
        const otherNames = lang==='en'?["Gunslinger","Munitions Expert","Mechanist","Cannonneer","Fist Master","Rogue","Judo Master","Qi Master","Ninja","Thief","Assassin","Warlock","Priest","Knight","Guardian Angel","Exorcist"]:otherData.map(d=>d.name);
        const otherDescs = lang==='en'?["Acrobatics+shooting","Special bullets, control+burst","Robot swarm, sustained DPS","Ultra-long range AOE","Highest melee burst, short range","Crowd control","Grapple+burst","Internal energy ranged","High burst seals","Traps+control","Single-target assassination","Curse/DoT","Heal/revive","High defense tank","Damage sharing","Seals+control"]:otherData.map(d=>d.desc);
        document.querySelectorAll('#otherGrid .job-card').forEach((c,i)=>{ c.querySelector('h3').innerText=otherNames[i]; c.querySelector('p').innerText=otherDescs[i]; });
        // 副本表格
        const dnNames=lang==='en'?["Mage Corridor","Shadow Nest","Broken Sword Canyon","Aether Altar","Seventh Seal"]:rewardData.map(r=>r.dungeon);
        const dropsEn=lang==='en'?["Elemental Core, Mage Tome","Nightshade Fragments, Trap Blueprint","Warrior/Sword Inscription","Legendary Base, Fusion Stone","Memory Fragment, Hourglass"]:rewardData.map(r=>r.drops);
        const rareEn=lang==='en'?["Staff 'Aether Walker', Stabilizer","Dagger 'Abyss Scar'","Spectral Seal","Tome 'Omni-Inscript'","Unique 'Creation Seal'"]:rewardData.map(r=>r.rare);
        document.querySelectorAll('#rewardBody tr').forEach((r,i)=>{ r.cells[0].innerText=dnNames[i]; r.cells[1].innerText=dropsEn[i]; r.cells[2].innerText=rareEn[i]; });
        // NPC
        const npcNames=lang==='en'?["Erena","Karn","Viola","Grey","Headmaster"]:npcData.map(n=>n.name);
        const npcClasses=lang==='en'?["Guardian Angel","Berserker","Arcane Scholar","Assassin","Runic Sage"]:npcData.map(n=>n.class);
        const npcRoles=lang==='en'?["Childhood friend, may fall","Rival→ally","Mentor, cult spy","Remnant Hunter","Your creator"]:npcData.map(n=>n.role);
        document.querySelectorAll('#npcBody tr').forEach((r,i)=>{ r.cells[0].innerText=npcNames[i]; r.cells[1].innerText=npcClasses[i]; r.cells[2].innerText=npcRoles[i]; });
        // 阵营
        const facNames=lang==='en'?["⚜️ Lingke Academy","🌙 Abyss Eye Cult","⚔️ Remnant Hunter Corps"]:factions.map(f=>f.name);
        const facDescs=lang==='en'?["Neutral highest institution","Worship Aether, seek evolution","Suppress cores, hunt Remnants"]:factions.map(f=>f.desc);
        document.querySelectorAll('#factionGrid .job-card').forEach((c,i)=>{ c.querySelector('h3').innerText=facNames[i]; c.querySelector('p').innerText=facDescs[i]; });
        // 传说装备
        const legNames=lang==='en'?["Meteor Breaker Staff","Causal Compass","Colorless Eye Pendant","Immortal Bulwark"]:legendary.map(l=>l.name);
        const legDescs=lang==='en'?["Adds 3 shockwaves","+50% DoT duration, reset CD","-30% Reverse-Inscript gain","+50% HP shield for party"]:legendary.map(l=>l.desc);
        document.querySelectorAll('#legendaryGrid .job-card').forEach((c,i)=>{ c.querySelector('h3').innerText=legNames[i]; c.querySelector('p').innerText=legDescs[i]; });
        // 系统
        const sysNames=lang==='en'?["Inscript Fusion","Reverse-Inscript Value","Bond Rune","Remnant Transformation"]:systems.map(s=>s.name);
        const sysDescs=lang==='en'?["Combine two class skills","Risk of becoming Remnant","Affinity affects endings","Berserk mode when over limit"]:systems.map(s=>s.desc);
        document.querySelectorAll('#systemGrid .job-card').forEach((c,i)=>{ const strong=c.querySelector('strong'); if(strong) strong.innerText=sysNames[i]; c.childNodes.forEach(n=>{ if(n.nodeType===3 && n.textContent.includes('—')) n.textContent = ` — ${sysDescs[i]}`; }); });
    }
    let curLang = 'zh';
    document.getElementById('navLangBtn').addEventListener('click',()=>{ curLang = curLang === 'zh' ? 'en' : 'zh'; setLanguage(curLang); document.getElementById('navLangBtn').innerHTML = `<i class="fas fa-globe"></i> ${curLang === 'zh' ? 'EN / 中文' : '中文 / EN'}`; });
    document.getElementById('preorderBtn').addEventListener('click',()=>alert("感谢您的关注！《灵刻纪元》即将开启预购，届时将获得限定灵刻外观。"));
    const modal = document.getElementById('guideModal');
    document.getElementById('navGuideBtn').addEventListener('click',()=>modal.classList.add('active'));
    document.getElementById('closeModalBtn').addEventListener('click',()=>modal.classList.remove('active'));
    modal.addEventListener('click',(e)=>{if(e.target===modal) modal.classList.remove('active');});
	
	
	const sectionTitles = document.querySelectorAll('.section-title');

function revealTitles() {
    const triggerBottom = window.innerHeight * 0.85;
    sectionTitles.forEach(title => {
        const top = title.getBoundingClientRect().top;
        if (top < triggerBottom) {
            title.classList.add('visible');
        }
    });
}

window.addEventListener('scroll', revealTitles);
window.addEventListener('load', revealTitles);
</script>
</body>
</html>
