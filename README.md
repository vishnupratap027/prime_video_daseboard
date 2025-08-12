# prime_video_daseboard
INTERNSHIP WORK

## 1. Prime Video Dashboard Overview
An interactive, dynamic analytics tool designed to explore content trends, release patterns, and ratings distribution on Amazon Prime Video. This Power BI dashboard provides clear insights into the platform’s content library, including KPIs for movies and TV shows, trends over time, and the most common ratings—helping users, analysts, and media strategists understand the platform’s catalogue composition and release behavior.

---

## 2. Short Description / Purpose
The Prime Video Dashboard is a visually engaging Power BI report that allows users to analyze Prime Video’s content library by type, release year, ratings, and content addition trends. It is built to assist content analysts, streaming enthusiasts, and business stakeholders in identifying viewing trends, popular ratings, and release year distributions. By combining interactive filters with detailed KPIs, this dashboard delivers quick, data-driven insights into Prime Video’s offerings.

---

## 3. Tech Stack
The dashboard was built using the following tools and technologies:  
- 📊 **Power BI Desktop** – For building interactive visuals and designing the layout.  
- 📂 **Power Query** – For cleaning, transforming, and shaping the raw Prime Video dataset into analysis-ready format.  
- 🧠 **DAX (Data Analysis Expressions)** – For creating measures and calculated columns like *Total Movies*, *Total TV Shows*, and *Most Common Rating*.  
- 📝 **Data Modeling** – Relationships between tables were established for dynamic filtering and accurate aggregation.  
- 🌐 **GitHub** – For hosting and sharing the project files and dashboard screenshots.  
- 📁 **File Format** – Developed in `.pbix` for Power BI and `.png` for visual previews.

---

## 4. Features / Highlights

### Business Problem
Streaming platforms like Prime Video offer vast libraries, but understanding the composition of this content—by type, release year, and ratings—is often challenging without proper visualization. Key questions such as:
- How many movies vs. TV shows are available?
- What’s the most common content rating?
- In which years has Prime Video added the most content?
- Which release years dominate the library?

are difficult to answer quickly without a centralized, interactive dashboard.

### Goal of the Dashboard
To provide a centralized, interactive analytics tool that:
- Monitors the distribution of movies and TV shows.
- Identifies the most common ratings and release year patterns.
- Visualizes content addition trends over time.
- Allows filtering by type, rating, or other attributes for focused analysis.

### Walkthrough of Key Visuals

**KPI Cards (Top Section)**
- **Total Movies** – Count of all movies in the dataset.  
- **Total TV Shows** – Count of all TV shows.  
- **Average Release Year** – Average release year across all titles.  
- **Most Common Rating** – The rating category that appears most frequently.

**Content Type Donut Chart**
- Percentage split between Movies and TV Shows.

**Content Added Over Time (Line Chart)**
- Visualizes how much content was added each year (if `date_added` exists) or via `release_year` as a proxy.
- Built with DAX measures to support dynamic filtering.

**Titles by Release Year (Bar Chart)**
- Shows how many titles were released each year.

**Genre Treemap**
- Distribution of genres (requires splitting `listed_in` into separate rows in the cleaned data).

**Left-Side Filter Panel**
- Slicers for Type, Release Year, Rating, and Genre for interactive exploration.

### Business Impact & Insights
- Content strategy alignment (what types and ratings dominate).  
- Trend analysis to identify periods of higher content release.  
- Data-driven recommendations for acquisition and production.  
- Support for sharing quick insights with stakeholders.

---

## 5. How to Use
1. Download the cleaned dataset (`prime_video_cleaned.csv`) from the `data/` folder in this repository.  
2. Open `Prime_Video_Dashboard.pbix` in **Power BI Desktop** (if provided). Or import the CSV and recreate visuals following the visual mapping below.  
3. Use the **left-side slicers** to filter the whole report by Type, Rating, Release Year, or Genre.  
4. Click any KPI or chart item to cross-filter other visuals for drill-down exploration.  
5. To export the cleaned table: open **Data View** → select the table → right-click → **Copy Table** → paste into Excel and save as CSV. For large datasets use **DAX Studio** to export.

---

## 6. Visual Mapping (Fields → Visuals)
- **KPI Cards**
  - Total Movies → measure `Total Movies`
  - Total TV Shows → measure `Total TV Shows`
  - Average Release Year → `AVERAGE(release_year)`
  - Most Common Rating → measure `Most Common Rating`

- **Donut Chart**
  - Legend → `type`
  - Values → Count of `show_id`

- **Line Chart (Content Added Over Time)**
  - Axis → `release_year` (or `Calendar[Year]` if you created a calendar table)
  - Values → Count of `show_id`
  - Legend (optional) → `type`

- **Bar Chart (Titles by Release Year)**
  - Axis → `release_year`
  - Values → Count of `show_id`
  - Split by `type` for stacked/clustered view if desired

- **Treemap**
  - Group → `listed_in` (genre)
  - Values → Count of `show_id`

---

![Prime Video Dashboard]([https://github.com/YOUR_USERNAME/YOUR_REPO_NAME/blob/main/prime_video_dashboard.png](https://github.com/vishnupratap027/prime_video_daseboard/blob/main/prime_video_daseboard.ss.png))

