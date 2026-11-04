# 尘封卡带 · Sealed Cassette

竖屏趋势小 demo（TEMP playtest HTML）：每天来一个尘封包裹 → 开箱 → 用手指擦掉污垢，露出程序绘制的假卡带封面 → 入架收入货架图鉴。

全部卡带名为虚构戏仿（《林间闪光》《空轨站》《深井回声》《纸舟》《夜市骰子》《云端洗衣》《石阶猫》《锈港电台》等），像素封面由 Canvas 绘制，无外链图、无真作版权素材。

## 怎么打开

- **手机直开（GitHub Pages）**：https://zhanghaofan1986-dot.github.io/sealed-cassette/
- **源码仓**：https://github.com/zhanghaofan1986-dot/sealed-cassette-demo （PAT 无法直接开 Pages，故托管于用户 github.io 子目录）
- **本地**：双击 `index.html`，或用浏览器打开 `file:///…/sealed-cassette/index.html`。
- **本地小服务**：在本目录执行  
  `python3 -m http.server 8765`  
  然后打开 http://127.0.0.1:8765/

纯前端单页，无 npm 构建；`file://` 与 `http` 均可玩。

## 怎么玩（三步）

1. **开箱**：点「开箱」，纸箱裂开 / 胶带撕开短动画后露出脏卡带。
2. **擦拭**：用手指 / 鼠标拖着擦掉锈斑污垢（碎屑飞溅 + 沙沙音 + 轻微震动）；进度到 25/50/75% 有顿挫；≥ 95% 闪光通关并弹出「修好了！」。
3. **入架**：点「入架」卡带飞入货架；再点「拆下一个包裹」模拟次日，收集 8 种不同假卡带（稀有金边脉冲）。

「货架」可随时查看已收集缩略格（已收集格 pop-in，稀有格微光）。

## 技术要点

- 竖屏手机框 UI + `viewport` 禁缩放；Pointer Events 兼容触控与鼠标。
- 双 Canvas：底层程序绘像素卡带，上层污垢蒙版；擦除用 `destination-out`，进度按 alpha 抽样估算。
- 通关 / 开箱 / 擦拭 / 入架音：Web Audio API 短合成音（含噪声沙沙），无音频文件；可选 `navigator.vibrate`。
- 暖旧物配色（米黄 / 纸板 / 铁锈），无赛博霓虹主调；开箱 / 通关 / 入架均有 CSS 仪式反馈。

## 说明

TEMP playtest HTML demo，仅供玩法试玩，可随时删除。
