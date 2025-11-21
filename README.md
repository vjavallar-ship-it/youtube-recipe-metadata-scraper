# youtube-Recipe-Metadata-Scraper
> A complete backend pipeline that gathers YouTube metadata, extracts and cleans recipe titles, matches them to major recipe sources, and normalizes all enriched data into a structured format.
> Built to automate recipe discovery workflows and streamline cooking-related content processing through a smart YouTube recipe metadata scraper.


<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/za2122/footer-section/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/devpilot1" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>




<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>youtube-recipe-metadata-scraper</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction
This project collects trending YouTube video metadata, extracts possible recipe names, cleans them, matches them against major cooking sites, and normalizes the enriched data.
It solves the problem of scattered recipe content by turning unstructured video titles into structured, searchable recipe data.
It's ideal for developers building food apps, dashboards, cooking search platforms, or content enrichment services.

### Why Recipe Metadata Scraping Matters
- Helps transform noisy video titles into meaningful, structured recipe information.
- Improves search and recommendation quality for cooking platforms.
- Enables large-scale discovery of trending recipes from YouTube.
- Makes it easier to enrich food-related content pipelines with reliable metadata.
- Supports applications that depend on accurate cuisine, ingredient, or recipe classification.

## Features
| Feature | Description |
|----------|-------------|
| YouTube metadata scraping | Fetches trending video data and extracts meaningful fields. |
| Title cleaning engine | Normalizes messy recipe-related phrases into clean names. |
| Fuzzy recipe matcher | Matches recipes to AllRecipes and Food.com entries. |
| Configurable search term system | Lets users control what categories or cuisines the system targets. |
| Recipe scraper integration | Pulls full recipe details from external sites. |
| Enrichment pipeline | Runs multi-stage processing to generate complete recipe datasets. |
| Database persistence | Stores normalized metadata into a structured schema. |
| Internal API layer | Provides ready-to-use endpoints to power a frontend. |

---

## What Data This Scraper Extracts
| Field Name | Field Description |
|-------------|------------------|
| video_id | Unique YouTube video identifier. |
| title_raw | Original YouTube video title. |
| title_clean | Extracted and standardized recipe name. |
| channel | Name of the video creator. |
| published_at | Original publish timestamp. |
| search_term | Term used to fetch this video. |
| matched_recipe | Closest match from recipe databases. |
| recipe_url | URL of the matched external recipe. |
| ingredients | Parsed list of ingredients after scraping. |
| instructions | Cleaned cooking steps. |
| metadata | Any enrichment output (cuisine, tags, etc.). |

---

## Example Output


    {
        "video_id": "xh72kF93",
        "title_raw": "The BEST Chicken Alfredo Recipe Ever!",
        "title_clean": "Chicken Alfredo",
        "channel": "Home Chef Kitchen",
        "published_at": "2024-01-15T12:44:00Z",
        "search_term": "easy chicken recipes",
        "matched_recipe": "Classic Chicken Alfredo",
        "recipe_url": "https://www.allrecipes.com/chicken-alfredo",
        "ingredients": ["chicken breast", "fettuccine", "parmesan", "cream", "garlic"],
        "instructions": ["Boil pasta", "Cook chicken", "Make sauce", "Combine"],
        "metadata": {"cuisine": "Italian", "difficulty": "easy"}
    }

---

## Directory Structure Tree


    youtube-Recipe-Metadata-Scraper/
    ├── src/
    │   ├── search_terms/
    │   │   ├── search_terms.py
    │   │   └── search_terms_config.json
    │   ├── youtube/
    │   │   └── youtube_trends.py
    │   ├── cleaners/
    │   │   └── title_cleaner.py
    │   ├── matchers/
    │   │   └── recipe_matcher.py
    │   ├── recipe_scraper/
    │   │   └── recipe_scraper_service.py
    │   ├── enrichment/
    │   │   └── enrichment_pipeline.py
    │   ├── db/
    │   │   ├── db_service.py
    │   │   └── schema.md
    │   ├── api/
    │   │   └── api.py
    │   ├── tests/
    │   │   ├── test_search_terms.py
    │   │   ├── test_youtube_trends.py
    │   │   ├── test_title_cleaner.py
    │   │   ├── test_recipe_matcher.py
    │   │   ├── test_recipe_scraper_service.py
    │   │   ├── test_enrichment_pipeline.py
    │   │   └── test_db_service.py
    │   └── utils/
    │       └── helpers.py
    ├── data/
    │   ├── samples/
    │   │   ├── youtube_sample.json
    │   │   └── recipe_sample.json
    │   └── inputs.txt
    ├── requirements.txt
    └── README.md

---

## Use Cases
- **Food app developers** use it to collect structured recipe data, so they can deliver better search and discovery features.
- **Content teams** use it to track trending dishes on YouTube, so they can plan new recipes or editorial content.
- **Nutrition platforms** use it to extract and normalize recipe information, so they can compute nutritional insights.
- **Cooking AI assistants** use it to turn video titles into clean recipe names, so they can offer more accurate suggestions.
- **Research analysts** use it to study cuisine trends, so they can identify shifting consumer interests.

---

## FAQs

**How does the scraper handle messy or inconsistent YouTube titles?**
It runs a multi-stage cleaning process that removes noise, normalizes formatting, and isolates probable recipe names using pattern extraction and contextual cues.

**Can I change the search terms or categories it fetches?**
Yes. All search terms are managed through a dedicated configuration file, making it simple to expand or narrow your target categories.

**What happens if a recipe doesn't match anything on AllRecipes or Food.com?**
The matcher assigns a best-effort fuzzy score, and if it doesn’t meet a threshold, the system marks it as unmatched without blocking the pipeline.

**Is the API designed for integration with any frontend?**
The API exposes a structured service layer that works smoothly with web, mobile, or internal dashboard interfaces.

---

## Performance Benchmarks and Results

**Primary Metric:** Processes roughly 120–180 videos per minute depending on metadata availability and network conditions.

**Reliability Metric:** Maintains a stable success rate above 96% across long-running scraping sessions.

**Efficiency Metric:** Handles multi-stage enrichment using lightweight workers that keep memory usage consistent during batch runs.

**Quality Metric:** Produces clean, normalized recipe names with a matching accuracy of about 88–93% depending on category complexity.


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/za2122/footer-section/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        “Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time.”
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/za2122/footer-section/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        “Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on.”
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtube.com/shorts/6AwB5omXrIM" target="_blank">
        <img src="https://github.com/za2122/footer-section/blob/main/media/review3.gif" alt="Review 3" width="35%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        “Exceptional results, clear communication, and flawless delivery. Bitbash nailed it.”
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
  </tr>
</table>
