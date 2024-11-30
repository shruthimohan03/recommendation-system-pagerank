# TV Series Recommendation System using PageRank Algorithm

## Project Overview
The goal of this project is to develop a recommendation system for TV series by leveraging the **PageRank algorithm**. The system identifies the most influential genres in a dataset of TV series and uses these insights to recommend series based on genre relevance.

---

## Steps Involved

### 1. **Loading the Dataset**
We used a dataset containing the following fields:
- **Series Title**
- **Release Year**
- **Runtime**
- **Genre**
- **Rating**
- **Cast**
- **Synopsis**

Example row:

| Title     | Release Year | Runtime  | Genre                | Rating | Cast                         | Synopsis                             |
|-----------|--------------|----------|----------------------|--------|------------------------------|--------------------------------------|
| Wednesday | 2022–        | 45 min   | Comedy, Crime, Fantasy | 8.2    | Jenna Ortega, Hunter Doohan  | Follows Wednesday Addams' years as a student... |

---

### 2. **Creating the Graph Structure**
- **Nodes:** Represent genres.
- **Edges:** Represent co-occurrences of genres in the same series.
- **Construction:**
  - Split the `Genre` field into a list of genres for each series.
  - Connect each genre to every other genre in the list, forming a graph of genre co-occurrences.

---

### 3. **Implementing the PageRank Algorithm**
- **Initialization:** Assign an equal initial PageRank score to each genre.
- **Iterations:** 
  - Update each genre's score based on contributions from connected genres.
  - Use a damping factor `d = 0.85` to account for random jumps between nodes.
- **Convergence:** Continue iterating until the score changes between iterations are below a threshold (e.g., `1e−6`).

---

### 4. **Integrating PageRank Scores into Recommendations**
- **Genre Importance:** Use the PageRank scores to evaluate the importance of each genre.
- **Recommendation Score:**
  - For a given series, sum the PageRank scores of its genres.
  - Rank series based on their recommendation scores.
- **Output:** Return the top-ranked series as recommendations.

---

### 5. **Interpreting the Recommendations**
- The system identifies series with genres that have high PageRank scores, reflecting influential and well-connected genres.
- The recommendations aim to highlight series with prominent genres.

---

## Benefits and Limitations

### Benefits
- **Genre-Based Insights:** Highlights series with influential and commonly occurring genres.
- **Simplicity:** Focuses solely on genre co-occurrence, making it computationally lightweight.

### Limitations
- **Lack of Personalization:** Does not consider user preferences or past interactions.
- **Limited Metadata Usage:** Only uses genre information; additional factors like ratings or detailed metadata are not included.

---

## Usage
To use the recommendation system:
1. Load a dataset with TV series information (including genres).
2. Run the script to construct the graph and compute PageRank scores.
3. Input a series or genre to receive top recommendations.

---
