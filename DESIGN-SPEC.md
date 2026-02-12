# 16 EASTERN PARK — 设计规范 (Design Spec)

## 1. 品牌定位

- **品牌名称：** 16 EASTERN PARK / 东韵16号
- **Slogan：** 生长在艺术中心的街区商业
- **品牌关键词：** 艺术 · 生长 · 共生 · 社群
- **调性：** 高端、克制、艺术感、有质感

---

## 2. 色彩系统 (Color System)

### 主色 (Primary)
| 名称 | 色值 | 用途 |
|------|------|------|
| Primary | `#0D6B5E` | 主要按钮、选中态、强调色 |
| Primary Light | `#14B8A6` | 图标、标签、辅助强调 |
| Primary Dark | `#0A4F46` | 深色按钮、hover 状态 |
| Primary Glow | `rgba(13,107,94,0.3)` | 光晕效果、卡片边框 |

### 背景色 (Background)
| 名称 | 色值 | 用途 |
|------|------|------|
| BG Primary | `#0A1A18` | 页面主背景 |
| BG Card | `rgba(13,107,94,0.08)` | 卡片背景 |
| BG Elevated | `rgba(13,107,94,0.15)` | 浮层、弹窗背景 |
| BG Input | `rgba(13,107,94,0.12)` | 输入框背景 |

### 文字色 (Text)
| 名称 | 色值 | 用途 |
|------|------|------|
| Text Primary | `#FFFFFF` | 标题、主要文字 |
| Text Secondary | `rgba(255,255,255,0.7)` | 副标题、说明文字 |
| Text Tertiary | `rgba(255,255,255,0.45)` | 提示文字、禁用态 |
| Text Brand | `#14B8A6` | 品牌色文字、链接 |

### 语义色 (Semantic)
| 名称 | 色值 | 用途 |
|------|------|------|
| Success | `#10B981` | 成功状态 |
| Warning | `#F59E0B` | 警告状态 |
| Error | `#EF4444` | 错误状态 |
| Info | `#14B8A6` | 信息提示 |

---

## 3. 字体系统 (Typography)

### 字体族
```
font-family: -apple-system, BlinkMacSystemFont, "PingFang SC", "Helvetica Neue", "Microsoft YaHei", sans-serif;
```

### 字号规范
| 层级 | 字号 | 字重 | 行高 | 用途 |
|------|------|------|------|------|
| H1 | 24px | 700 | 1.3 | 页面标题 |
| H2 | 20px | 600 | 1.4 | 区块标题 |
| H3 | 17px | 600 | 1.4 | 卡片标题 |
| H4 | 15px | 500 | 1.4 | 列表标题 |
| Body | 14px | 400 | 1.5 | 正文 |
| Caption | 12px | 400 | 1.4 | 辅助说明 |
| Mini | 10px | 400 | 1.3 | 标签、角标 |

### 品牌字体
- 英文标题（如 "16 EASTERN PARK"）：使用 letter-spacing: 2px，字重 700
- 中文标题：PingFang SC Medium/Semibold

---

## 4. 间距系统 (Spacing)

基础单位：4px

| Token | 值 | 用途 |
|-------|------|------|
| spacing-xs | 4px | 图标与文字间距 |
| spacing-sm | 8px | 紧凑元素间距 |
| spacing-md | 12px | 常规元素间距 |
| spacing-lg | 16px | 卡片内边距 |
| spacing-xl | 20px | 区块间距 |
| spacing-2xl | 24px | 页面边距 |
| spacing-3xl | 32px | 区块之间大间距 |

---

## 5. 圆角系统 (Border Radius)

| Token | 值 | 用途 |
|-------|------|------|
| radius-sm | 6px | 小标签、按钮 |
| radius-md | 12px | 卡片、输入框 |
| radius-lg | 16px | 大卡片、弹窗 |
| radius-xl | 24px | 胶囊按钮 |
| radius-full | 50% | 头像、圆形图标 |

---

## 6. 阴影与光效 (Shadow & Glow)

### 阴影
```css
/* 卡片阴影 */
box-shadow: 0 2px 12px rgba(0, 0, 0, 0.3);

/* 浮层阴影 */
box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
```

### 光晕效果
```css
/* 卡片边框光晕 */
border: 1px solid rgba(13, 107, 94, 0.2);

/* 选中态光晕 */
box-shadow: 0 0 12px rgba(13, 107, 94, 0.4);

/* Banner 顶部光效 */
background: radial-gradient(ellipse at top, rgba(13,107,94,0.3), transparent 70%);
```

---

## 7. 图标系统 (Icons)

### 图标库
- **主要：** Lucide Icons（CDN: unpkg.com/lucide@latest）
- **备选：** Semi Design Icons（如后续迁移至 React）

### 图标尺寸
| 场景 | 尺寸 | stroke-width |
|------|------|-------------|
| Tab 导航 | 24px | 1.5 |
| 快捷入口 | 24px | 1.5 |
| 列表前缀 | 20px | 1.5 |
| 行内图标 | 16px | 2 |

### 图标颜色
- 默认：`rgba(255,255,255,0.7)`
- 选中/激活：`#14B8A6`
- 禁用：`rgba(255,255,255,0.3)`

---

## 8. 组件规范 (Components)

### 8.1 底部导航栏 (Tab Bar)
- 高度：60px + safe-area-inset-bottom
- 背景：`#0A1A18` + 顶部 1px 边框 `rgba(13,107,94,0.2)`
- 选中态：图标 + 文字变为 `#14B8A6`，顶部 2px 指示条
- 未选中：`rgba(255,255,255,0.45)`

### 8.2 卡片 (Card)
- 背景：`rgba(13,107,94,0.08)`
- 边框：`1px solid rgba(13,107,94,0.15)`
- 圆角：12px
- 内边距：16px
- 点击态：border-color 变为 `rgba(13,107,94,0.4)`，200ms transition

### 8.3 按钮 (Button)
**主要按钮：**
- 背景：`#0D6B5E`
- 文字：`#FFFFFF`
- 圆角：24px（胶囊形）
- 高度：40px
- hover：背景变亮至 `#0E7D6D`
- active：缩放 scale(0.97)，200ms

**幽灵按钮：**
- 背景：transparent
- 边框：`1px solid rgba(13,107,94,0.4)`
- 文字：`#14B8A6`

### 8.4 优惠券卡片 (Coupon Card)
- 左侧金额区：teal 渐变背景
- 右侧信息区：标题 + 说明
- 领取按钮：幽灵按钮样式
- 已领取态：按钮变灰，文字"已领取"

### 8.5 商户卡片 (Merchant Card)
- 左侧：圆形图标容器（48px）
- 中间：商户名 + 描述 + 分类标签
- 右侧：评分（星标 + 分数）
- 分类标签：小圆角背景色块

### 8.6 Toast 提示
- 居中浮现
- 背景：`rgba(13,107,94,0.9)`
- 圆角：12px
- 动画：fadeIn 0.3s + fadeOut 0.3s
- 持续时间：2秒

### 8.7 搜索栏 (Search Bar)
- 背景：`rgba(13,107,94,0.12)`
- 边框：`1px solid rgba(13,107,94,0.2)`
- focus 态：border-color `#0D6B5E`
- 前缀：search 图标
- 圆角：12px
- 高度：44px

---

## 9. 动效规范 (Animation)

### 过渡
```css
/* 默认过渡 */
transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);

/* 快速反馈 */
transition: all 0.15s ease;

/* 页面切换 */
transition: opacity 0.25s ease, transform 0.25s ease;
```

### 交互动效
| 场景 | 动效 | 时长 |
|------|------|------|
| Tab 切换 | 淡入淡出 | 250ms |
| 按钮点击 | scale(0.97) | 150ms |
| 卡片点击 | border 高亮 | 200ms |
| Toast 出现 | translateY + fadeIn | 300ms |
| 签到成功 | scale 弹跳 + 粒子 | 500ms |
| 页面滚动 | 顶部渐变出现 | 200ms |
| 下拉刷新 | 旋转 loading | - |

### 手势交互（移动端）
- Banner：左右滑动切换
- 商户列表：上拉加载更多
- 优惠券：长按查看详情
- 签到按钮：按下缩放反馈

---

## 10. 页面布局 (Layout)

### 安全区域
```css
padding-top: env(safe-area-inset-top);
padding-bottom: env(safe-area-inset-bottom);
```

### 页面结构
- 顶部固定区：Header（56px）
- 内容滚动区：flex: 1, overflow-y: auto
- 底部固定区：TabBar（60px + safe-area）

### 页面边距
- 左右边距：20px
- 内容卡片间距：12px

---

## 11. 会员等级视觉 (Membership Tiers)

| 等级 | 颜色 | 标识 |
|------|------|------|
| 普通会员 | `#6B7280`（灰） | 无特殊标识 |
| 银卡 | `#C0C0C0`（银） | 银色渐变卡面 |
| 金卡 | `#D4AF37`（金） | 金色渐变卡面 |
| 黑金卡 | `#1a1a1a` + `#D4AF37` | 黑金渐变卡面 |

---

## 12. 技术实现备注

### 当前（Demo 阶段）
- 单 HTML 文件 + 内联 CSS/JS
- Lucide Icons CDN
- 纯 CSS 动画

### 未来（正式开发）
- 框架：Taro + React（小程序 + H5 双端）
- UI 库：Semi Design（移动端组件）
- 图标：Semi Icons 或 Lucide
- 状态管理：Zustand
- 构建：Vite

---

*版本：v1.0*
*更新日期：2026-02-12*
*维护：Rody*
