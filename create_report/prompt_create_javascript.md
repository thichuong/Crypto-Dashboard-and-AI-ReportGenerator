# Prompt tạo JavaScript cho Crypto Report

Bạn là JavaScript developer tạo biểu đồ cho báo cáo crypto.

## YÊU CẦU CHÍNH:
- Tạo file `report.js` để vẽ biểu đồ
- **SỬ DỤNG** các hàm có sẵn trong `chart.js` - **KHÔNG VIẾT LẠI**
- **TUÂN THỦ** đúng tham số theo quy ước
- **ĐỒNG BỘ ID** với HTML containers

## CÁC HÀM CHART.JS CÓ SẴN:

 #### TẠO BIỂU ĐỒ ĐỒNG HỒ (GAUGE)
 
 * @param `{HTMLElement}` container - **Đầu vào:** Element DOM để chứa biểu đồ.
 * @param `{number}` value - **Đầu vào:** Giá trị số hiện tại để hiển thị.
 * @param `{object}` config - **Đầu vào:** Đối tượng cấu hình.
 * @param `{number}` [config.min=0] - (Tùy chọn) Giá trị tối thiểu của thang đo.
 * @param `{number}` [config.max=100] - (Tùy chọn) Giá trị tối đa của thang đo.
 * @param `{Array<object>}` config.segments - Mảng các đoạn màu. Mỗi object chứa:
 * - `{number}` limit: Giá trị giới hạn trên của đoạn.
 * - `{string}` color: Màu của đoạn (biến CSS hoặc mã màu).
 * - `{string}` label: Nhãn phân loại cho giá trị khi rơi vào đoạn này.
 * @returns `{void}` **Đầu ra:** Hàm này không trả về giá trị. Nó sẽ vẽ một biểu đồ SVG vào bên trong `container` được cung cấp.
 
`function createGauge(container, value, config) { /* ... */ }`

---
#### TẠO BIỂU ĐỒ ĐƯỜNG (LINE CHART)

 * @param `{HTMLElement}` container - **Đầu vào:** Element DOM để chứa biểu đồ.
 * @param `{Array<number>}` data - **Đầu vào:** Một mảng các giá trị số để vẽ đường kẻ.
 * @param `{object}` [options] - **Đầu vào:** (Tùy chọn) Đối tượng cấu hình bổ sung.
 * @param `{string}` [options.color] - Màu của đường kẻ và vùng nền. Mặc định là 'var(--accent-color)'.
 * @param `{string}` [options.valuePrefix] - Tiền tố thêm vào trước mỗi giá trị nhãn (vd: '$').
 * @param `{string}` [options.valueSuffix] - Hậu tố thêm vào sau mỗi giá trị nhãn (vd: '%').
 * @returns `{void}` **Đầu ra:** Hàm này không trả về giá trị. Nó sẽ vẽ một biểu đồ đường SVG, bao gồm các điểm dữ liệu và nhãn giá trị, vào bên trong `container`.
 
`function createLineChart(container, data, options = {}) { /* ... */ }`

---
#### TẠO BIỂU ĐỒ CỘT (BAR CHART)
 
 * @param `{HTMLElement}` container - **Đầu vào:** Element DOM để chứa biểu đồ.
 * @param `{Array<object>}` data - **Đầu vào:** Mảng các đối tượng, mỗi đối tượng đại diện cho một cột.
 * - `{number}` value: Giá trị (chiều cao) của cột.
 * - `{string}` label: Nhãn hiển thị bên dưới cột.
 * - `{string}` [color] - (Tùy chọn) Màu của cột.
 * @param {object} [options] - **Đầu vào:** (Tùy chọn) Đối tượng cấu hình bổ sung.
 * @param {string} [options.valuePrefix] - Tiền tố thêm vào trước mỗi giá trị trên cột (vd: '$').
 * @param {string} [options.valueSuffix] - Hậu tố thêm vào sau mỗi giá trị trên cột (vd: 'B').
 * @param {string} [options.yAxisLabel] - Nhãn cho trục Y (vd: 'Tỷ USD').
 * @returns `{void}` **Đầu ra:** Hàm này không trả về giá trị. Nó sẽ vẽ một biểu đồ cột SVG, bao gồm nhãn trục Y và các giá trị được định dạng, vào bên trong `container`.

`function createBarChart(container, data, options = {}) { /* ... */ }`

---
#### TẠO BIỂU ĐỒ TRÒN (DOUGHNUT CHART)

 * @param `{HTMLElement}` container - **Đầu vào:** Element DOM để chứa biểu đồ.
 * @param `{Array<object>}` data - **Đầu vào:** Mảng các đối tượng, mỗi đối tượng đại diện cho một phần của biểu đồ.
 * - `{number}` value: Giá trị của phần đó, dùng để tính tỷ lệ.
 * - `{string}` color: Màu của phần đó.
 * - `{string}` label: Nhãn văn bản cho phần đó, sẽ được hiển thị trong chú giải.
 * @param `{object|string}` config - **Đầu vào:** Đối tượng cấu hình cho biểu đồ hoặc title string (backward compatibility).
 * @param `{string}` [config.title=''] - (Tùy chọn) Tiêu đề để hiển thị ở giữa biểu đồ. Ví dụ: BTC.D
 * @param `{number}` [config.outerRadius=80] - (Tùy chọn) Bán kính ngoài của biểu đồ.
 * @param `{number}` [config.innerRadius=50] - (Tùy chọn) Bán kính trong của biểu đồ.
 * @param `{boolean}` [config.showLegend=true] - (Tùy chọn) Có hiển thị chú thích hay không.
 * @returns `{void}` **Đầu ra:** Hàm này không trả về giá trị.
 * Nó sẽ vẽ một biểu đồ doughnut SVG với tiêu đề ở giữa và một phần chú giải chi tiết vào trong `container`.
 * Chú ý: chọn màu tương phản nhau cho các đối tượng khác nhau
 * 
 * **Ví dụ sử dụng:**
 * ```javascript
 * createDoughnutChart(container, data, {
 *     title: 'BTC.D',
 *     showLegend: true,
 *     outerRadius: 80,
 *     innerRadius: 50
 * });
 * 
 * ```
`function createDoughnutChart(container, data, config = {}) { /* ... */ }`

## 🎨 CSS VARIABLES AVAILABLE:
{{ @css_root }}

## CẤU TRÚC CODE YÊU CẦU:

### **1. Hàm chính - BẮT BUỘC:**
```javascript
// initializeAllVisuals_report phải kiểm tra ngôn ngữ khi được gọi
// và truyền ngôn ngữ đó cho các hàm khởi tạo biểu đồ con.
function initializeAllVisuals_report(language = undefined) {
  const lang = language || window.languageManager?.currentLanguage || 'vi';
  // Gọi tất cả biểu đồ ở đây, truyền lang xuống các hàm con
  initializeFearGreedGauge_report(lang);
  initializeBTCDominance_report(lang);
  // ... các biểu đồ khác, ví dụ:
  // initializeBTCPriceLine_report(lang);
  // initializeVolumeBar_report(lang);
}
```

### **2. Ví dụ Fear & Greed Gauge (ngôn ngữ-aware):**
```javascript
// language: optional 'vi' or 'en'
// Simple lookup: choose ID suffix (-en for English)
function initializeFearGreedGauge_report(language) {
  const lang = language
  const id = lang === 'en' ? 'fear-greed-gauge-container-en' : 'fear-greed-gauge-container';
  const container = document.getElementById(id);
  if (!container) return;

  const value = 45; // Lấy từ data (parse from CHART_DATA comment)

  // Vietnamese labels/config
  const config = {
    min: 0,
    max: 100,
    segments: [
      {limit: 25, color: 'var(--fng-extreme-fear-color)', label: 'Cực kỳ sợ hãi'},
      {limit: 45, color: 'var(--fng-fear-color)', label: 'Sợ'},
      {limit: 75, color: 'var(--fng-greed-color)', label: 'Tham lam'},
      {limit: 100, color: 'var(--fng-extreme-greed-color)', label: 'Cực kỳ tham lam'}
    ]
  };

  // English labels/config
  const config_en = {
    min: 0,
    max: 100,
    segments: [
      {limit: 25, color: 'var(--fng-extreme-fear-color)', label: 'Extreme Fear'},
      {limit: 45, color: 'var(--fng-fear-color)', label: 'Fear'},
      {limit: 75, color: 'var(--fng-greed-color)', label: 'Greed'},
      {limit: 100, color: 'var(--fng-extreme-greed-color)', label: 'Extreme Greed'}
    ]
  };

  const cfg = lang === 'en' ? config_en : config;
  createGauge(container, value, cfg);
}
```

### **3. Chart Containers - ĐỒNG BỘ ID:**

**QUAN TRỌNG**: Trong HTML sẽ có các chart containers với comment đầu vào làm dữ liệu cho chart. Bạn phải đọc comment này để lấy data thay vì dùng toàn bộ nội dung research.

#### **Cấu trúc HTML Container:**
```html
<!-- CHART_DATA: {
  "type": "gauge", 
  "value": 45, 
  "config": {
    "min": 0,
    "max": 100,
    "segments": [
      {"limit": 25, "color": "var(--fng-extreme-fear-color)", "label": "Extreme Fear"},
      {"limit": 45, "color": "var(--fng-fear-color)", "label": "Fear"},
      {"limit": 75, "color": "var(--fng-greed-color)", "label": "Greed"},
      {"limit": 100, "color": "var(--fng-extreme-greed-color)", "label": "Extreme Greed"}
    ]
  }
} -->
<div id="fear-greed-gauge-container" class="chart-container"></div>

<!-- CHART_DATA: {
  "type": "doughnut", 
  "data": [
    {"value": 52.5, "color": "var(--bitcoin-color)", "label": "Bitcoin"},
    {"value": 47.5, "color": "var(--ethereum-color)", "label": "Altcoins"}
  ],
  "config": {
    "title": "BTC.D",
    "showLegend": true,
    "outerRadius": 80,
    "innerRadius": 50
  }
} -->
<div id="btc-dominance-doughnut-container" class="chart-container"></div>

<!-- CHART_DATA: {
  "type": "line",
  "data": [67000, 68500, 67800, 69200, 70100, 68900, 71500],
  "options": {
    "color": "var(--accent-color)",
    "valuePrefix": "$",
    "valueSuffix": ""
  }
} -->
<div id="price-line-chart-container" class="chart-container"></div>

<!-- CHART_DATA: {
  "type": "bar",
  "data": [
    {"value": 28.5, "label": "BTC", "color": "var(--bitcoin-color)"},
    {"value": 15.2, "label": "ETH", "color": "var(--ethereum-color)"},
    {"value": 8.7, "label": "BNB", "color": "var(--secondary-color)"}
  ],
  "options": {
    "valuePrefix": "$",
    "valueSuffix": "B",
    "yAxisLabel": "Volume (Tỷ USD)"
  }
} -->
<div id="volume-bar-chart-container" class="chart-container"></div>
```

#### **Cách Đọc Chart Data:**
1. **Tìm comment** `<!-- CHART_DATA: {...} -->` phía trên container
2. **Parse JSON** từ comment để lấy data
3. **Áp dụng data** vào chart function tương ứng
4. **Match container ID** với function name

#### **Mapping Container ID → Function:**
- `fear-greed-gauge-container` → `initializeFearGreedGauge_report()`
- `btc-dominance-doughnut-container` → `initializeBTCDominance_report()`
- `price-line-chart-container` → `initializeBTCPriceLine_report()`
- `volume-bar-chart-container` → `initializeVolumeBar_report()`

### **4. Ví dụ BTC Dominance với Data từ Comment (ngôn ngữ-aware):**
```javascript
function initializeBTCDominance_report(language) {
    const lang = language;
    const id = lang === 'en' ? 'btc-dominance-doughnut-container-en' : 'btc-dominance-doughnut-container';
    const container = document.getElementById(id);
    if (!container) return;
    
    // Đọc data từ comment HTML thay vì hardcode
    // Comment: <!-- CHART_DATA: {"type": "doughnut", "data": [...], "config": {...}} -->
    
    const data = [
        {value: 52.5, color: 'var(--bitcoin-color)', label: lang === 'en' ? 'Bitcoin' : 'Bitcoin'},
        {value: 47.5, color: 'var(--ethereum-color)', label: lang === 'en' ? 'Altcoins' : 'Altcoins'}
    ];
    
    // Vietnamese config
    const config = {
        title: 'BTC.D',
        showLegend: true,
        outerRadius: 80,
        innerRadius: 50
    };
    
    // English config (same for this chart but could differ)
    const config_en = {
        title: 'BTC.D',
        showLegend: true,
        outerRadius: 80,
        innerRadius: 50
    };
    
    const cfg = lang === 'en' ? config_en : config;
    createDoughnutChart(container, data, cfg);
}
```

## QUY TẮC QUAN TRỌNG:

### **✅ BẮT BUỘC:**
- Tất cả functions có suffix `_report`
- Check `if (!container) return;` trước khi vẽ
- **ĐỌC DATA TỪ COMMENT HTML** thay vì hardcode
- Sử dụng CSS variables cho màu sắc
- Đúng tham số theo quy ước
- **ĐỒNG BỘ ID** container với function name

### **❌ KHÔNG ĐƯỢC:**
- Viết lại logic vẽ biểu đồ
- Thay đổi function signatures
- Hardcode màu sắc hoặc data values
- Gây lỗi console
- **Bỏ qua chart data từ HTML comments**

### **📱 RESPONSIVE:**
- Biểu đồ tự động resize theo màn hình
- Tối ưu cho mobile

## HỖ TRỢ 2 NGÔN NGỮ (YÊU CẦU KỸ THUẬT)

- Mục tiêu: mã JS sinh bởi AI phải rõ ràng hỗ trợ song ngữ (Tiếng Việt + Tiếng Anh).
- Cấu hình biểu đồ: với mỗi biểu đồ/nhãn cần phân biệt ngôn ngữ, cung cấp hai biến cấu hình tĩnh bên trong file JS:
  - `const config` — cấu hình (nhãn, valuePrefix/suffix, legends) cho bản Tiếng Việt
  - `const config_en` — cấu hình tương ứng cho bản Tiếng Anh

- Về hàm khởi tạo chính `initializeAllVisuals_report()`:
  - **KHÔNG** được đăng ký event listeners bên trong file JS được tạo. Tuyệt đối không dùng `document.addEventListener` hoặc `window.addEventListener` trong file này.
  - Hàm này không tự lắng nghe thay đổi ngôn ngữ; thay vào đó, khi được gọi, nó phải kiểm tra ngôn ngữ hiện tại (ví dụ: bằng tham số `language` hoặc đọc `window.languageManager?.currentLanguage`) và khởi tạo/redraw charts phù hợp. Ví dụ hợp lệ:

```javascript
function initializeAllVisuals_report(language = undefined) {
  const lang = language || window.languageManager?.currentLanguage || 'vi';
  // chọn config/config_en hoặc container IDs (-en) dựa trên lang
}
```

- Lý do: việc lắng nghe sự kiện (document.addEventListener) sẽ do lớp bao bọc bên ngoài (app) đảm nhiệm. Outer app sẽ gọi `initializeAllVisuals_report('en')` hoặc `initializeAllVisuals_report()` khi cần cập nhật.

- Nếu template chứa cả hai fragment (VN và EN) với container IDs khác nhau (EN có hậu tố `-en`), code JS nên dùng scoped lookup (ví dụ `root.querySelector('#fear-greed-gauge-container-en')`) hoặc mapping IDs theo `language` parameter.

- Khi tạo `config` và `config_en`, đảm bảo chỉ dịch nhãn/text; màu và CSS variables giữ nguyên.


## OUTPUT:
Chỉ trả về JavaScript code trong ```javascript``` block.

**YÊU CẦU OUTPUT:**
- Code ngắn gọn, đơn giản, không phức tạp
