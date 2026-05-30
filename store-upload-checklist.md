# Google Play Console アップロード手順 (v1.8)

> ⚠️ Google Play Consoleの操作は手動で行ってください。下記の素材とテキストをそのままコピペで使えます。

---

## 📦 アップロード対象ファイル

| 種別 | パス | サイズ | 用途 |
|---|---|---|---|
| **AAB** | `android/app/build/outputs/bundle/release/app-release.aab` | 8.5 MB | 製品版リリース |
| **APK** | `android/app/build/outputs/apk/release/app-release.apk` | 8.9 MB | 内部テスト (任意) |
| **スクショ 1** | `docs/store-screenshots/output/01-fire-countdown.png` | 1080×1920 | Heroカウントダウン |
| **スクショ 2** | `docs/store-screenshots/output/02-projection.png` | 1080×1920 | 資産推移グラフ |
| **スクショ 3** | `docs/store-screenshots/output/03-indices.png` | 1080×1920 | 4指数 |
| **スクショ 4** | `docs/store-screenshots/output/04-types.png` | 1080×1920 | 5タイプ |
| **スクショ 5** | `docs/store-screenshots/output/05-import.png` | 1080×1920 | ライフプラン取り込み |
| アイコン | `docs/icon-512.png` | 512×512 | 既存 (変更不要) |
| フィーチャー | `docs/feature-graphic.png` | 1024×500 | 既存 (変更不要) |
| プライバシー | `docs/privacy-policy.html` | - | 既存URLにホストされている前提 |

---

## 🚀 Play Consoleでの操作手順

### 1. リリース作成
1. https://play.google.com/console にアクセス
2. **ミライノート** を選択
3. 左メニュー → **製品版**（または内部テストで動作確認後に製品版）
4. **新しいリリースを作成** をクリック

### 2. AAB アップロード
5. **App Bundle** セクションで `app-release.aab` をアップロード
6. アップロード後、versionCode 9 / versionName 1.8 が認識されることを確認

### 3. リリースノート (What's New)
7. **リリースノート** 欄に下記を貼り付け（500文字以内）:

```
🔥 大型アップデート：FIREカウントダウン機能を追加！

■ FIREまでの日数カウントダウン
4指数連動で、あなたのFIRE達成日を毎日表示

■ 資産推移グラフ
複利成長と月積立の合算をマイルストーン付きでグラフ化

■ 5つのFIREタイプ
リーン/ファット/サイド/バリスタ/コースト から選択可能

■ ライフプラン連携
既存プランから年齢・月支出・貯蓄をワンタップ取り込み

■ 新オンボーディング
「FIRE / 老後計画」の目的別に最適な画面へ案内

■ 商用品質の堅牢性
アクセシビリティ・オフライン・エラー耐性を強化
```

### 4. ストア掲載情報を更新（左メニュー → ストアの掲載情報）

8. **アプリ名** （変更）:
```
ミライノート - ライフプラン × FIREシミュレーター
```

9. **短い説明** (80文字):
```
あなたのFIREまで、あと何日？ 4指数連動で目標達成日を毎日カウントダウン。
```

10. **詳細な説明** （`docs/store-listing.md` の「【ミライノートとは？】」以降をコピペ）

11. **スクリーンショット**:
   - 既存のスクショは保持しつつ、`docs/store-screenshots/output/` の5枚を **先頭に追加**
   - 並び順: 01 → 02 → 03 → 04 → 05

### 5. 保存 → 製品版に送信
12. **変更を保存**
13. **製品版へのリリースを開始** → 審査待ち（通常2〜24時間）

---

## ✅ 提出前チェックリスト

- [ ] AAB の versionCode = 9 / versionName = 1.8 を Console 側で確認
- [ ] リリースノートを貼り付け済み
- [ ] スクリーンショット 5枚を追加済み（並び順 1→5）
- [ ] アプリ名と短い説明を更新済み
- [ ] 詳細な説明を更新済み
- [ ] プライバシーポリシーURL が有効（変更なし）
- [ ] コンテンツレーティング（既存のまま）
- [ ] データセーフティ宣言：「指数価格データ取得のため Cloudflare Workers と通信」を追記推奨

---

## 🌐 関連リンク

- Google Play Console: https://play.google.com/console
- Cloudflare Workers ダッシュボード: https://dash.cloudflare.com（API動作確認用）
- アプリ詳細ページ（公開後）: https://play.google.com/store/apps/details?id=com.mirainote.app
