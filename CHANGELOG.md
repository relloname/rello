# Changelog - Marketing Report v7

## Version 7.0 (2024)

### New Features

#### 🛍️ 상품 분석 탭 (Product Analysis Tab)
- Complete product performance analysis with image display
- Filter by campaign, ad group, and device
- ROAS highlighting and sorting
- Change rate indicators matching existing design
- Left-aligned product names for better readability

#### 📤 개선된 데이터 업로드 (Improved Data Upload)
- Drag & drop file upload zones (4 separate zones)
- Visual feedback with checkmarks on successful upload
- Support for CSV, XLSX, and TSV formats
- Removed cluttered statistics section

#### 🔝 TOP10 검색어 테이블 (TOP10 Keywords Tables)
- 5 tables showing top 10 keywords by different metrics
- Fixed positioning at top of ranking analysis page
- Metrics: 광고비, 노출수, 클릭수, 전환수, 매출액

### Enhanced Features

#### TOTAL 행 순서 변경 (Reordered TOTAL Rows)
- New order: 4-week average → Previous week → Current week
- Dynamic week labels from data
- Change rates only on current week vs previous week
- Applied to: Campaign, Ad Group, Keyword, and Product analysis

#### 💲 CPC 분석 필터 개선 (Enhanced CPC Analysis Filters)
- Complete filter set matching efficiency analysis
- 최대 전환당비용 (Maximum CPA) instead of minimum
- All standard filters: keyword exclusion, campaign type, campaign, ad group
- Performance thresholds: min cost, min conversions, min ROAS, max CPA

#### 🔍 키워드 분석 개선 (Enhanced Keyword Analysis)
- ROAS now shows change rate indicator
- Already using RAW2.csv for detailed keyword data
- Accurate TOTAL calculations

### Technical Improvements

#### New Functions
- `parseProductCSV(buf)` - Parse product performance CSV
- `parseTSV(buf)` - Parse product mapping TSV
- `updateProductTable()` - Update product analysis table
- `updateTop10Tables()` - Generate TOP10 tables
- `resetProduct()` - Reset product filters

#### New Global Variables
- `productRows` - Product performance data array
- `productMap` - Product ID to info mapping

#### CSS Additions
- Upload dropzone styles with hover effects
- TOP10 table sticky positioning
- Product table alignment styles

### Maintained Features
- All existing tabs and their functionality
- Chart.js visualizations
- Filter and sort capabilities
- ROAS highlighting
- Change rate indicators
- Responsive design
- Collapsible detail rows

---

## Migration Guide

### From v6 to v7

1. **File Upload Changes**
   - Old: 2 file inputs (RAW, RAW2)
   - New: 4 drag & drop zones (RAW, RAW2, Product CSV, Product TSV)

2. **New Tab Available**
   - 🛍️ 상품 분석 tab between 키워드 분석 and 매체별 분석

3. **TOTAL Row Changes**
   - Check your reports - TOTAL rows now appear in different order
   - Current week TOTAL shows change vs previous week only

4. **CPC Analysis**
   - New filter options available
   - Maximum CPA instead of minimum

### Data Files Required

1. **RAW.csv** - Daily/weekly campaign data (existing)
2. **RAW2.csv** - Keyword search data (existing)
3. **Product CSV** - Product performance data (NEW)
4. **Product TSV** - Product information mapping (NEW)

Product CSV format:
```
캠페인유형,캠페인,광고그룹,상품ID,일별,주별,날짜,광고비,노출수,클릭수,전환수,매출액
```

Product TSV format:
```
[Various fields]  productId  [fields]  productName  productImageURL
```

---

## Browser Compatibility

Tested and working on:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

Required:
- JavaScript enabled
- Modern browser with ES6 support
- Chart.js 4.4.0 (loaded from CDN)
- XLSX library 0.18.5 (loaded from CDN)

---

## File Size

- marketing_report_v7.html: ~120KB
- No external dependencies (all libraries from CDN)
- All functionality in single file

---

## Known Limitations

1. Product analysis requires both CSV and TSV files
2. File uploads are client-side only (data not persisted)
3. Large datasets (>10,000 rows) may slow performance
4. Excel files must be .xlsx or .xls format (not .csv saved as .xls)

---

## Future Enhancements (Not in this version)

- [ ] Data persistence (save to browser storage)
- [ ] Export functionality for filtered data
- [ ] Custom date range selection
- [ ] Multi-file batch upload
- [ ] Dark mode theme

---

## Credits

Based on marketing_report_v6_Version2_Version2 (1).html
Product analysis features inspired by 소재.html
