# 台灣釣點地圖 官方網站

這個 repo 就是網站本身（GitHub Pages 直接發布根目錄）。

網址：<https://timsucompany-gif.github.io/taiwan-fishing-map/>

| 路徑 | 內容 |
|---|---|
| `/` | 下載頁 |
| `/privacy/` | 隱私權政策（上架表單填這個網址） |
| `/upload-terms/` | 投稿須知 |
| `/at/` | App 分享出去的地點頁 |
| `404.html` | 找不到頁面 |
| `.nojekyll` | 告訴 GitHub Pages 不要用 Jekyll 處理 |

## 怎麼更新

網頁不是手寫的，是 `釣魚觀測資料/build_site.py` 產生的（設定在 `site_config.json`）：

```
python build_site.py
```

產生的 `site/` 資料夾內容，就是這個 repo 的根目錄；把內容複製過來 commit 就好。

## 之後才會出現的東西

- `data/`：給已經安裝的 App 自動更新釣點資料用。目前 `site_config.json` 的 `publish_data` 是
  `false`，所以不放（1.0 的資料本來就在 App 裡，不需要再下載一次）。
  之後要發新資料時改成 `true`，並用 `python build_site.py --data-on` 打開開關。
- `app-ads.txt`、`.well-known/`（iOS、Android 的深連結驗證檔）：這些必須放在**網域根目錄**，
  也就是 `timsucompany-gif.github.io` 那個 repo，不是這裡。build_site.py 會把它們放在 `site_root/`。
