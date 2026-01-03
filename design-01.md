# 联合丽格（西南）网站设计规范

> 基于 docs.bccsw.cn 网站提取的设计风格指南

---

## 1. 品牌标识

### 1.1 Logo
- **主 Logo**: `https://docs.bccsw.cn/logo.png`
- **用途**: 导航栏、页脚、宣传物料
- **尺寸规范**:
  - 导航栏: `h-10` (约40px)
  - 页脚: `h-12` (约48px)
  - Hero Section: 根据容器自适应

### 1.2 Favicon
- **路径**: `https://docs.bccsw.cn/favicon.png`
- **格式**: PNG
- **用途**: 浏览器标签页图标

### 1.3 品牌名称
- **主品牌**: 联合丽格
- **区域标识**: 联合丽格（西南）
- **站点名称**: 联合丽格（西南）行业资讯分享

---

## 2. 公司信息

### 2.1 公司全称
```
重庆联合丽格科技有限公司
```

### 2.2 联系信息

| 项目 | 内容 |
|------|------|
| **地址** | 重庆市渝中区临江支路28号 |
| **主热线** | 023-68726872 |
| **加盟热线** | 135-0116-6830 |
| **企业邮箱** | bccsw@cqlhlg.work |
| **负责人邮箱** | yuxiaodong@beaucare.org |
| **负责人** | 于晓冬 先生 |
| **微信号** | @sooogooo |

### 2.3 备案信息
- **ICP备案**: 渝ICP备2024023473号
- **链接**: https://beian.miit.gov.cn/
- **显示位置**: 页脚版权区域

---

## 3. 色彩规范

### 3.1 品牌主色

| 名称 | 色值 | 用途 |
|------|------|------|
| `bcc-blue` | `#0d2c54` | 主导航、重要标题、主要按钮背景 |
| `bcc-navy` | `#0a2240` | 页脚背景、深色强调区域 |
| `bcc-gold` | `#f5a623` | 强调色、重要数据高亮、行动按钮 |

### 3.2 背景色系

| 名称 | 色值 | 用途 |
|------|------|------|
| `warm-white` | `#faf9f7` | 页面主背景 |
| `beige` | `#e8e4df` | 边框、分隔线、卡片边框 |
| `mint-green` | `#c1e3d3` | 受益/增长类标签背景 |
| `pale-purple` | `#d8ccf0` | 装饰背景 |
| `powder-blue` | `#c5d8f0` | 装饰背景 |
| `soft-rose` | `#f5e6e0` | 负面/下降类标签背景 |
| `rose-gold` | `#e8b4a8` | 项目符号、强调小元素 |

### 3.3 文字颜色
- **主文字**: `gray-800` (#1f2937)
- **次要文字**: `gray-500` (#6b7280)
- **浅色文字**: `gray-300` (#d1d5db) - 深色背景上使用
- **白色文字**: 在深色背景上使用

---

## 4. 字体规范

### 4.1 字体族
```css
font-family: 'Noto Sans SC', 'Inter', system-ui, sans-serif;
```

| 字体 | 用途 |
|------|------|
| Noto Sans SC | 中文内容（粗细: 300/400/500/600/700） |
| Inter | 英文内容、数字 |
| system-ui | 系统默认无衬线字体 |

### 4.2 字号规范

| 用途 | 字号 class | 近似px值 |
|------|-----------|----------|
| Hero 大标题 | `text-4xl ~ text-6xl` | 36px ~ 60px |
| 章节标题 | `text-3xl ~ text-4xl` | 30px ~ 36px |
| 卡片标题 | `text-xl` | 20px |
| 正文内容 | `text-base ~ text-lg` | 16px ~ 18px |
| 辅助说明 | `text-sm` | 14px |
| 标签/小字 | `text-xs` | 12px |

### 4.3 字重与间距
- **默认字重**: 300 (light)
- **强调字重**: 500 ~ 600
- **行高**: `1.9`
- **字间距**: `0.03em`

---

## 5. 组件设计

### 5.1 导航栏
- **固定定位**: `fixed w-full z-40`
- **背景**: 白色半透明 (`bg-white/95 backdrop-blur-md`)
- **底部边框**: `border-b border-gray-100`
- **Logo位置**: 左侧
- **桌面菜单**: 居中，间距 `space-x-8`
- **按钮**: CTA按钮使用 `bg-bcc-gold text-white rounded-full`

### 5.2 Hero Section
```css
.hero-section {
    background: linear-gradient(135deg, rgba(13, 44, 84, 0.85), rgba(13, 44, 84, 0.75)),
                url('背景图片URL');
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
}
```
- **视差效果**: PC端使用 `fixed`，移动端回退到 `scroll`
- **装饰元素**: 浮动圆形模糊背景 (`blur-3xl`)

### 5.3 毛玻璃卡片
```css
.glass-card {
    background: rgba(255, 255, 255, 0.08);
    backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.15);
}

.glass-card-light {
    background: rgba(255, 255, 255, 0.7);
    backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.5);
}
```

### 5.4 数据卡片
- **形状**: 圆角 `rounded-3xl`
- **背景**: `bg-warm-white border border-beige`
- **悬停效果**: `hover:shadow-xl hover:-translate-y-2`

### 5.5 标签样式
```html
<!-- 受益/增长标签 -->
<span class="px-3 py-1.5 rounded-full bg-mint-green/40 text-green-700 text-xs font-medium">
    <i class="ri-arrow-up-line"></i> 受益
</span>

<!-- 受冲击标签 -->
<span class="px-3 py-1.5 rounded-full bg-soft-rose/60 text-red-700 text-xs font-medium">
    <i class="ri-arrow-down-line"></i> 受冲击
</span>

<!-- 调整中标签 -->
<span class="px-3 py-1.5 rounded-full bg-beige/70 text-gray-600 text-xs font-medium">
    <i class="ri-refresh-line"></i> 调整
</span>
```

### 5.6 步骤卡片
- **序号圈**: `w-20 h-20 rounded-full border-4 border-bcc-blue`
- **当前步骤**: 数字样式
- **最后步骤**: 金色背景 `bg-bcc-gold text-white`

---

## 6. 动画效果

### 6.1 浮动动画
```css
@keyframes float {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33% { transform: translate(30px, -30px) scale(1.05); }
    66% { transform: translate(-20px, 20px) scale(0.95); }
}

.float-animation { animation: float 20s ease-in-out infinite; }
.float-animation-delay { animation: float 25s ease-in-out infinite reverse; }
```

### 6.2 渐入动画
```css
.fade-in {
    opacity: 0;
    transform: translateY(40px);
    transition: opacity 0.8s ease, transform 0.8s ease;
}

.fade-in.visible {
    opacity: 1;
    transform: translateY(0);
}

.fade-in-delay-1 { transition-delay: 0.1s; }
.fade-in-delay-2 { transition-delay: 0.2s; }
.fade-in-delay-3 { transition-delay: 0.3s; }
```

### 6.3 点击缩放
```css
.active-scale:active { transform: scale(0.97); }
```

---

## 7. 响应式设计

### 7.1 断点
| 断点 | 前缀 | 屏幕宽度 |
|------|------|----------|
| Mobile | 默认 | < 768px |
| Tablet | `md:` | ≥ 768px |
| Desktop | `lg:` | ≥ 1024px |

### 7.2 移动端底部常驻栏
```html
<div class="md:hidden fixed bottom-0 left-0 w-full bg-white border-t border-gray-200 flex z-50">
    <button class="flex-1 py-3 ...">智能咨询</button>
    <button class="flex-1 py-3 ...">转发</button>
    <a href="tel:xxx" class="flex-[2] bg-bcc-blue ...">加盟热线</a>
</div>
```

### 7.3 移动端菜单
- **触发**: 汉堡菜单图标
- **动画**: `transform: translateY(-100%)` ↔ `translateY(0)`
- **z-index**: 1000 (遮罩层), 1100 (菜单)

---

## 8. 图标规范

### 8.1 图标库
- **Remix Icon**: `https://cdn.jsdelivr.net/npm/remixicon@4.2.0/fonts/remixicon.css`
- **使用方式**: `<i class="ri-图标名"></i>`

### 8.2 常用图标速查

| 用途 | 图标名 |
|------|--------|
| 分享 | `ri-share-line` |
| 菜单 | `ri-menu-line` / `ri-close-line` |
| 电话 | `ri-phone-line` |
| 邮件 | `ri-mail-line` |
| 箭头向下 | `ri-arrow-down-line` |
| 箭头向右 | `ri-arrow-right-s-line` |
| 图表 | `ri-file-chart-line` |
| 灯泡 | `ri-lightbulb-line` |
| 机器人 | `ri-robot-line` |

---

## 9. 第三方集成

### 9.1 Tailwind CSS
```html
<script src="https://cdn.tailwindcss.com"></script>
```

### 9.2 Google Fonts
```html
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
```

### 9.3 微信分享二维码 API
```
https://api.qrserver.com/v1/create-qr-code/?size=300x300&data={URL编码后的链接}
```

### 9.4 AI助手 (MaxKB)
- **移动端**: 内嵌 iframe
- **PC端**: 嵌入式脚本
- **Token**: d380a7be78eb61ff

---

## 10. SEO 与社交媒体

### 10.1 Open Graph 标签
```html
<meta property="og:type" content="article">
<meta property="og:title" content="页面标题">
<meta property="og:description" content="页面描述">
<meta property="og:image" content="https://docs.bccsw.cn/logo.png">
<meta property="og:url" content="当前页面URL">
<meta property="og:site_name" content="联合丽格（西南）行业资讯分享">
```

### 10.2 Twitter Card
```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="页面标题">
<meta name="twitter:description" content="页面描述">
<meta name="twitter:image" content="https://docs.bccsw.cn/logo.png">
```

### 10.3 微信分享
```html
<meta itemprop="name" content="页面标题">
<meta itemprop="description" content="页面描述">
<meta itemprop="image" content="https://docs.bccsw.cn/logo.png">
```

### 10.4 其他 SEO
```html
<meta name="description" content="页面描述">
<meta name="keywords" content="关键词1,关键词2,...">
<meta name="author" content="重庆联合丽格科技有限公司">
<link rel="canonical" href="标准URL">
```

---

## 11. 页面结构模板

### 11.1 标准页面区块顺序
1. **导航栏** (Nav)
2. **Hero Section** (首屏大图/标题)
3. **数据统计** (Stats Section)
4. **核心洞察** (Key Points)
5. **详细内容** (Content Sections)
6. **行动号召** (CTA Section)
7. **加盟/联系** (Join Section)
8. **页脚** (Footer)

### 11.2 移动端适配
- 底部常驻导航栏
- 汉堡菜单
- 触控友好的按钮尺寸 (最小 44px)
- 横向滚动避免

---

## 12. 设计资源汇总

### 12.1 在线资源
| 资源 | URL |
|------|-----|
| Tailwind CSS | https://tailwindcss.com |
| Remix Icon | https://remixicon.com |
| Google Fonts | https://fonts.google.com |
| QR Code API | https://api.qrserver.com |

### 12.2 静态资源路径
| 资源 | 路径 |
|------|------|
| Logo | https://docs.bccsw.cn/logo.png |
| Favicon | https://docs.bccsw.cn/favicon.png |
| 微信二维码 | https://docs.bccsw.cn/sooogooo.png |
| 背景图 | https://www.chain.bccsw.cn/wp-content/uploads/2025/12/bcc-001.jpg |

---

## 13. 使用建议

### 13.1 新页面创建检查清单
- [ ] 引用 Tailwind CSS 和 Remix Icon
- [ ] 配置品牌色彩 (`bcc-blue`, `bcc-gold`)
- [ ] 设置正确的字体族
- [ ] 添加 SEO meta 标签
- [ ] 配置 Open Graph 标签
- [ ] 设置正确的 title
- [ ] 添加页脚（包含备案信息）
- [ ] 测试移动端响应式
- [ ] 验证分享功能

### 13.2 设计原则
1. **层次分明**: 标题 > 正文 > 辅助说明
2. **留白充足**: 使用 `py-20`, `gap-8` 等间距类
3. **色彩克制**: 主色不超过3种
4. **动画适度**: 避免过度动画影响性能
5. **移动优先**: 先确保移动端体验

---

> 本规范由网站设计提取生成，适用于联合丽格（西南）相关项目的设计与开发。
