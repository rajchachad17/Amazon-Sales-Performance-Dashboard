# 📦 Amazon Sales Performance Dashboard

An end-to-end data analytics project analyzing Amazon product sales data — covering data collection, cleaning, preprocessing, SQL querying, Excel analysis, and interactive Power BI visualization.

---

## 📁 Project Structure

```
amazon-sales-dashboard/
│
├── amazon (raw_data).csv                  # Raw dataset (Phase 1)
├── amazon_df (clean_data).xlsx            # Cleaned data output (Phase 2)
├── amazon_df_excel_engineered.xlsx        # Excel-engineered data with pivot tables (Phase 4)
├── Sales_Performance_Dashboard.ipynb      # Main Python notebook (Phase 2 & 3)
├── Sales_Performance_Visualisation.pbix   # Power BI dashboard (Phase 5)
└── README.md
```

---

## 🔄 Project Phases

### Phase 1 — Data Collection
- Source: Amazon product dataset (16 columns, 1000+ rows)
- Key fields: `product_id`, `product_name`, `category`, `discounted_price`, `actual_price`, `discount_percentage`, `rating`, `rating_count`, `user_id`, `review_id`

---

### Phase 2 — Data Cleaning (Python)
- Dropped unnecessary columns (e.g. `about_product`, `img_link`, `product_link`, etc.)
- Removed duplicate records
- Identified primary attributes for analysis
- Detected and handled missing values
- Filled missing values using context-aware strategies:
  - `category` → filled with `'UNKNOWN_CATEGORY'`
  - `discount_percentage` → recalculated from price columns
  - `rating` → filled with **group mean by category**
  - `rating_count`, `review_id` → filled with `0`
  - `user_id` → filled with `'UNKNOWN_USER'`

---

### Phase 3 — Data Preprocessing (Python + SQL)
- Cleaned and converted currency columns (`₹` symbol removed, cast to `float`)
- Stripped `%` from discount column and converted to numeric
- Loaded cleaned DataFrame into **SQLite** using `sqlite3`
- Performed analytical SQL queries:
  - Products per category
  - Average rating by category
  - Top 10 highest-rated products
  - Products with high discount (>40%)
  - Price segmentation (Low / Medium / High) with avg ratings
  - Categories with avg rating ≥ 4.2

---

### Phase 4 — Data Engineering (Excel)
- Added derived columns based on category groupings
- Built **Pivot Tables** for category-level summaries
- Created **Pivot Charts** for quick visual reference

---

### Phase 5 — Data Visualization (Power BI)
- Built an interactive **Sales Performance Dashboard** in Power BI
- Visuals include category-wise breakdowns, rating distributions, discount analysis, and price segment performance

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Python (pandas, numpy) | Data cleaning & preprocessing |
| SQLite3 | SQL-based data querying |
| Microsoft Excel | Feature engineering & pivot analysis |
| Power BI | Interactive dashboard & visualization |
| Jupyter Notebook | Development environment |

---

## 📊 Key Insights

- Identified categories with the highest average ratings and product volumes
- Revealed a pattern where heavily discounted products don't always correlate with high ratings
- Medium-priced products (₹500–₹2000) showed the best balance of rating and volume
- Categories with consistent avg rating ≥ 4.2 surfaced as top-performing segments

---

## 👤 Author

**Rajvardhan Chachad**
GitHub: [@rajchachad17](https://github.com/rajchachad17)
