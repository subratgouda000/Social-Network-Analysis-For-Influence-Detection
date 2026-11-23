# Social Network Analysis For Influence Detection

This repository contains the complete source code, datasets, and documentation for the B.Tech Major Project and published research paper: **"Social Network Analysis For Influence Detection"** (Published in *Tanz Research Journal*, vol. 12, no. 33, pp. 346-363, 2026).

## 📖 Project Overview
Social Network Analysis (SNA) is the study of relationships and interactions between individuals (nodes) in a network using graph theory. This project applies SNA to detect influential users across three major social media platforms: **Facebook**, **Twitter**, and **YouTube**. 

The system combines four centrality measures with content-based analysis to produce a final Influence Score for each user. **TextBlob** is used for sentiment analysis to classify comments, and a **custom rule-based function** filters out fake accounts before final ranking.

## 📂 Platform Datasets Analyzed
- **Facebook:** Community-based interactions (600 users | 2963 edges)
- **Twitter:** Information Bridge Network (600 users | 2974 edges)
- **YouTube:** Broadcast Subscription Model (600 channels | 3500 edges)

*(Note: Synthetic datasets were generated using ChatGPT for consistency across platforms).*

## 🛠️ Tools and Technologies
- **Language:** Python 3
- **Libraries:** `Pandas` (data manipulation), `NetworkX` (graph construction & centrality), `TextBlob` (sentiment analysis), `Matplotlib` (visualization)
- **Environment:** Google Colab / Jupyter Notebook
- **Data Format:** Excel (.xlsx) with two sheets: Nodes (User Profiles) and Edges (Interactions)

## 🔬 Methodology (6 Sequential Phases)
1. **Data Collection:** Synthetic datasets for 3 platforms (600 users each).
2. **Data Preprocessing:** Cleaning and normalization.
3. **Network Construction:** Build Graph G=(V, E) where V = users, E = interactions (follows, mentions, comments, shares).
4. **Centrality Analysis:** Compute Degree, Betweenness, Closeness, and Eigenvector centrality using NetworkX.
5. **Content Analysis:**
   - **Sentiment Analysis:** Uses `TextBlob` to return a polarity score (-1.0 to +1.0). Polarity > 0 is Positive, < 0 is Negative, and empty text is "No Comment".
   - **Bot Detection:** Custom Rule-Based Scoring Function. Each rule adds +1 to the bot score: 
     - Rule 01: Following > 1000
     - Rule 02: Followers < 100
     - Rule 03: Posts > 300
     - Rule 04: Eigenvector < 0.01
     - *Decision Rule:* Bot Score ≥ 2 → Classified as "Bot"; Bot Score < 2 → "Real User".
6. **Influence Score:** Final Score = Degree + Betweenness + Closeness + Eigenvector. Users are ranked from high to low.

## 📊 Key Results & Platform Comparison
- **YouTube (Broadcast Model):** Top channels show high Eigenvector Centrality (avg 0.076) and low bot scores (avg 0.11). Sentiment is mostly positive (avg 0.82).
- **Twitter (Information Bridge):** Highest Betweenness Centrality (avg 0.038) and Closeness (avg 0.499), confirming its role in fast information spread. 
- **Facebook (Community Model):** Lower centrality across the board (avg degree 0.017, avg closeness 0.330). Betweenness is lowest (avg 0.005) indicating fewer bridge users.

### Top 5 Influencers Found (by Influence Score):
**YouTube:**
1. Channel_560 (0.51)
2. Channel_387 (0.51)
3. Channel_528 (0.50)
4. Channel_439 (0.50)
5. Channel_503 (0.49)

**Twitter:**
1. User_387 (0.50)
2. User_528 (0.49)
3. User_237 (0.49)
4. User_73 (0.49)
5. User_439 (0.49)

**Facebook:**
1. User_397 (0.50)
2. User_431 (0.50)
3. User_110 (0.49)
4. User_169 (0.48)
5. User_198 (0.48)

## 📜 Publication & Authors
**Publication:** Ashish Kumar Dass, Subrat Gouda, Aparna Sahu, Akanksha Priyadarshani Muni, Kiran Devi, "Social Network Analysis For Influence Detection," *Tanz Research Journal*, vol.12, no. 33, pp. 346-363, 2026.

**DOI/URL Link:** https://tanzresearch.net/volume-12-issue-3-2026

**Project Team:**
- Subrat Gouda (Roll No: 202220361)
- Aparna Sahu (Roll No: 202221390)
- Akanksha Priyadarshani Muni (Roll No: 202221287)
- Kiran Devi (Roll No: 202245370)

*Under the guidance of Mr. Ashish Kumar Dass, NIST University.*
