# 🚌 九龍巴士轉乘優惠查詢

**KMB Bus Interchange Discount Finder**

一個簡潔易用的網頁應用，幫助香港乘客快速查詢九龍巴士（KMB）的轉乘優惠計劃。

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

## ✨ 功能特色

- 🔍 **智能搜尋** - 支援按路線號碼搜尋轉乘優惠
- 📊 **分類瀏覽** - 按轉乘類別快速篩選（過海隧巴、隧道轉乘、地區轉乘等）
- 💰 **詳細資訊** - 顯示優惠金額、轉乘地點、時限及條件
- 🌓 **深色模式** - 自動適應系統主題偏好
- 📱 **響應式設計** - 完美支援手機、平板及桌面裝置
- 🎨 **美觀界面** - 採用現代化設計系統，清晰易用
- ⚡ **純前端** - 無需後端，開箱即用

## 🚀 快速開始

### 線上使用

直接訪問 GitHub Pages：**[https://sodiasm.github.io/kmb-interchange-finder](https://sodiasm.github.io/kmb-interchange-finder)**

### 本地運行

1. **克隆專案**
```bash
git clone https://github.com/sodiasm/kmb-interchange-finder.git
cd kmb-interchange-finder
```

2. **開啟應用**

直接在瀏覽器中打開 `index.html` 文件即可，無需安裝任何依賴。

或使用本地伺服器：

```bash
# 使用 Python
python -m http.server 8000

# 或使用 Node.js
npx serve
```

然後在瀏覽器訪問 `http://localhost:8000`

## 📖 使用說明

### 基本操作

1. **瀏覽所有優惠** - 頁面載入時自動顯示所有可用的轉乘優惠
2. **分類篩選** - 點擊頂部類別標籤（全部優惠、過海隧巴、隧道轉乘、地區轉乘、其他轉乘）
3. **路線搜尋** - 在搜尋框輸入路線號碼（如 `960`、`68X`）
4. **查看詳情** - 點擊結果卡片查看完整的轉乘資訊

### 支援的轉乘類別

#### 🌉 過海隧巴
- 西隧過海路線互轉
- 西隧路線轉電車（免費）
- 東隧過海路線互轉

#### 🛣️ 隧道轉乘
- 屯門公路轉車站
- 啟德隧道轉乘
- 大老山隧道轉乘
- 將軍澳隧道轉乘

#### 🏘️ 地區轉乘
- 屯門區內轉乘
- 元朗區內轉乘
- 上水粉嶺轉乘
- 沙田區內轉乘

#### 🔄 其他轉乘
- 九巴轉港鐵
- 龍運機場線轉九巴

## 💡 轉乘使用須知

- ✅ 必須使用同一張八達通卡或電子支付方式
- ⏱️ 須在指定時間內完成轉乘（一般為 90-150 分鐘）
- 🚫 兩程之間不可使用該八達通作其他交通交易
- 💳 八達通餘額必須充足以支付第二程車資
- 👥 部分優惠不適用於長者、殘疾人士或小童
- 📱 電子支付只適用於九巴及龍運路線之間

## 🛠️ 技術架構

### 技術棧

- **HTML5** - 語義化結構
- **CSS3** - 現代化樣式系統
  - CSS Variables for theming
  - Flexbox layout
  - Media queries for responsive design
- **Vanilla JavaScript** - 無框架依賴
  - ES6+ syntax
  - Event-driven architecture
  - Client-side search & filtering

### 專案結構

```
kmb-interchange-finder/
├── index.html          # 主要應用文件（含 HTML、CSS、JS）
├── README.md           # 專案文檔
└── LICENSE            # MIT 授權
```

### 設計系統

```css
/* 顏色變數 */
--color-bg-primary: 背景主色
--color-text-primary: 文字主色
--color-accent: 強調色（青色系）
--color-border: 邊框顏色

/* 深色模式自動切換 */
@media (prefers-color-scheme: dark) { ... }
```

### 資料結構

```javascript
const interchangeDatabase = {
  crossHarbour: [...],  // 過海隧巴優惠
  tunnel: [...],        // 隧道轉乘優惠
  district: [...],      // 地區轉乘優惠
  other: [...]          // 其他轉乘優惠
}
```

每個轉乘方案包含：
- `category` - 類別
- `name` - 方案名稱
- `firstRoutes` - 第一程適用路線
- `secondRoutes` - 第二程適用路線
- `discount` - 優惠金額
- `timeLimit` - 轉乘時限
- `location` - 轉乘地點
- `conditions` - 使用條件
- `description` - 詳細說明

## 🔧 開發指南

### 新增轉乘方案

在 `index.html` 的 `interchangeDatabase` 中添加新的轉乘方案：

```javascript
{
  category: "tunnel",
  name: "新隧道轉乘優惠",
  firstRoutes: ["1", "2", "3"],
  secondRoutes: ["4", "5", "6"],
  discount: "$5.0",
  timeLimit: "120分鐘",
  location: "轉乘站名稱",
  conditions: "使用條件說明",
  description: "詳細描述"
}
```

### 自訂樣式

修改 CSS Variables 以自訂主題顏色：

```css
:root {
  --color-accent: #your-color;  /* 修改強調色 */
  --color-bg-primary: #your-bg; /* 修改背景色 */
}
```

## 📊 資料來源

- **九龍巴士官方網站** - 官方轉乘優惠資訊
- **香港巴士大典** - 詳細路線及轉乘資料

> ⚠️ **免責聲明**：轉乘優惠隨時可能變更，請以九巴官方公佈為準。

## 🤝 貢獻指南

歡迎提交 Issue 或 Pull Request！

### 貢獻步驟

1. Fork 本專案
2. 創建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 開啟 Pull Request

### 貢獻建議

- 🐛 報告錯誤或資料更新
- ✨ 提議新功能
- 📝 改善文檔
- 🌐 新增其他語言支援
- 🎨 優化界面設計

## 📝 更新日誌

### v1.0.0 (2026-03-04)

- ✨ 初始版本發布
- 🎨 現代化設計系統
- 🔍 智能搜尋功能
- 📊 分類瀏覽功能
- 🌓 深色模式支援
- 📱 響應式設計
- 🚀 GitHub Pages 部署

## 📄 授權協議

本專案採用 [MIT License](LICENSE) 授權。

---

## 🔗 相關連結

- **九龍巴士官網**: [https://www.kmb.hk](https://www.kmb.hk)
- **轉乘優惠查詢**: [https://www.kmb.hk/tc/fares_and_fare_concessions/interchange_discount.html](https://www.kmb.hk/tc/fares_and_fare_concessions/interchange_discount.html)
- **GitHub Repository**: [https://github.com/sodiasm/kmb-interchange-finder](https://github.com/sodiasm/kmb-interchange-finder)

## 📧 聯絡方式

如有任何問題或建議，歡迎通過以下方式聯絡：

- GitHub Issues: [提交 Issue](https://github.com/sodiasm/kmb-interchange-finder/issues)
- Email: sodiasm@duck.com

---

<div align="center">
  <strong>Made with ❤️ in Hong Kong</strong>
  <br>
  <sub>幫助香港乘客節省交通費用 🚌💰</sub>
</div>