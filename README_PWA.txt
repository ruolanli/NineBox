# Day11 词汇 PWA 资源包

文件包含：
- /icons/ 目录：180/192/256/384/512 尺寸的应用图标（含 apple-icon-180.png）
- manifest.json：Web App Manifest
- sw.js：最小 Service Worker（离线缓存）

## 接入步骤
1. 把 `icons/`、`manifest.json`、`sw.js` 放到站点根目录（或你的 index.html 同目录）。
2. 在 HTML <head> 中加入：
   <link rel="manifest" href="./manifest.json" />
   <meta name="theme-color" content="#0e1021" />
   <link rel="apple-touch-icon" href="./icons/apple-icon-180.png" />
   <meta name="apple-mobile-web-app-capable" content="yes" />
   <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />
3. 在 HTML 末尾注册 Service Worker（只需一次）：
   <script>
     if ('serviceWorker' in navigator) {
       window.addEventListener('load', () => navigator.serviceWorker.register('./sw.js'));
     }
   </script>
4. 确保通过 HTTPS 访问（或 http://localhost）。
5. 用 iPad 的 Safari 打开页面 → 分享按钮 → “添加到主屏幕”。

## 更新
- 替换 sw.js 中的 CACHE 名称（例如 v2）以触发缓存刷新。
