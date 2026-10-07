# CV 網站部署說明

檔案：`index.html`（前台）、`admin.html`（後台）、`data.json`（所有內容）、`images/`（作品圖片，之後自動建立）。

## 部署到 GitHub Pages

1. 登入 GitHub，建立新 repo。要用 `https://<帳號>.github.io/` 網址，repo 名稱必須是 `<帳號>.github.io`；其他名稱則網址為 `https://<帳號>.github.io/<repo>/`。
2. 把本資料夾內的檔案上傳到 repo 根目錄（網頁 Add file → Upload files，或用 git push）。
3. repo → Settings → Pages → Source 選 **Deploy from a branch**，Branch 選 `main` / `(root)`，Save。約 1 分鐘後網站上線。

## 設定後台

1. GitHub → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → Generate new token。
2. Repository access 只選這個 repo；Permissions → Repository permissions → **Contents: Read and write**。
3. 開啟 `https://<你的網址>/admin.html`，填入 Owner、Repo、Branch、Token，按「從 GitHub 載入」。
4. 修改或新增內容後按「儲存到 GitHub」，約 1 分鐘後前台更新。

## 注意

- Token 只存在你瀏覽器的 localStorage，請勿在公用電腦儲存；用完可按「清除已儲存的 Token」。
- `admin.html` 是公開網址，但沒有 Token 就無法儲存。已加 `noindex`，避免被搜尋引擎收錄。
- 若 repo 是公開的，`data.json` 內容任何人都看得到。電話預設留空，需要時再於後台「基本資料」填入。
- 本機預覽：在此資料夾執行 `python3 -m http.server`，開啟 `http://localhost:8000`。直接雙擊 `index.html` 因瀏覽器限制讀不到 `data.json`。
- 作品類別目前有「管理成果」「工具與系統」「其他」；要新增類別，需修改 `index.html` 與 `admin.html` 內的 `cats`／`CATS`。
