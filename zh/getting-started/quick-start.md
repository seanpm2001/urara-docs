# 快速開始

## 分叉

你可以在 GitHub 使用此模板而無需下載到本地。

訪問 [importantimport/urara](https://github.com/importantimport/urara) 存儲庫，并點擊下面的 GitHub, Vercel 或 Netlify 部署按鈕。

## 本地下載

### Node.js

在下載前你必須先檢查你的電腦是否已經安裝 Node.js。

```bash
node --version
```

如果你的電腦未安裝 Node.js，則需要[下載並完成安裝](https://nodejs.org/zh-tw/download)。

> 對於 Windows 用戶：請確保勾選 **Add to PATH** 選項（默認已勾選）

### pnpm

本項目默認使用 [pnpm](https://pnpm.io/zh) 包管理器。

通過 npx 安裝：

```bash
npx pnpm add -g pnpm
```

其他安裝方式請參考[官方文檔](https://pnpm.io/zh/installation)。

### @antfu/ni

本項目建議使用 [@antfu/ni](https://github.com/antfu/ni) 以簡化輸入：

```bash
pnpm i -g @antfu/ni
```

如果不使用此工具，則需要輸入更多字符。例如：

```bash
# nx degit importantimport/urara
pnpm dlx degit importantimport/urara

# nr dev --host 0.0.0.0 --port 3001
pnpm run dev -- --host 0.0.0.0 --port 3001

# nr build
pnpm run build

# nu
pnpm upgrade
```

### degit

使用 `degit` 下載模板，并安裝依賴包：

```bash
nx degit importantimport/urara # 下載到當前目錄
# 或者
nx degit importantimport/urara my-blog && cd my-blog # 在當前目錄新建 my-blog 并下載到該文件夾，然後進入

ni # 安裝依賴包
```

## 運行

### 開發

使用 `nr dev` 運行開發服務器：

```bash
nr dev # http://localhost:3000
nr dev --host 0.0.0.0 # http://0.0.0.0:3000
nr dev --host 0.0.0.0 --port 8080 # http://0.0.0.0:8080
```

### 部署

此模板默認使用 `adapter-auto`，當未檢測到兼容環境時自動回退到 `adapter-static`。

使用 `nr build` 生成部署文件：

```bash
nr build
```

或强制使用特定的適配器：

```bash
VERCEL=true nr build # adapter-vercel
CF_PAGES=true # adapter-cloudflare-pages
NETLIFY=true nr build # adapter-netlify
```