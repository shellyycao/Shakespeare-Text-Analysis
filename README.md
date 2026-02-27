# Shakespeare Genre Analysis

Computational analysis of genre signatures in Shakespeare's plays using TF-IDF, Pearson correlation, and syntactic complexity measures.

## Project Overview

This project explores whether Shakespeare's genre categories (tragedy, comedy, history) are reflected in measurable linguistic patterns. Using a corpus of 21 plays, we analyze:

- **Lexical distinctiveness** (TF-IDF)
- **Text similarity** (Pearson correlation)
- **Syntactic complexity** (sentence structure analysis)

## Research Question

What are the computational signatures of tragedy, comedy, and history in Shakespeare's plays? Do genre categories reflect measurable linguistic differences, or are they primarily thematic distinctions?

## Corpus

**21 Shakespeare plays:**
- 8 Tragedies: *Hamlet*, *Macbeth*, *Othello*, *King Lear*, *Romeo and Juliet*, *Julius Caesar*, *Antony and Cleopatra*, *Coriolanus*
- 8 Comedies: *A Midsummer Night's Dream*, *Much Ado About Nothing*, *Twelfth Night*, *As You Like It*, *The Merchant of Venice*, *The Taming of the Shrew*, *The Comedy of Errors*, *The Tempest*
- 5 Histories: *Henry V*, *Richard III*, *Henry IV Part 1*, *Henry IV Part 2*, *Richard II*

**Source:** Folger Digital Texts

## Repository Structure
```
Shakespeare-Text-Analysis/
├── Data/
│   └── 00_raw/              # Raw text files from Folger Shakespeare
├── Script/
│   └── shakespeare_eda.ipynb  # Main analysis notebook
├── Output/
│   ├── tfidf_*.png          # TF-IDF visualizations
│   ├── pearson_heatmap.png  # Correlation heatmap
│   └── syntactic_*.png      # Syntactic complexity charts
└── README.md
```

## Methods

### 1. Text Normalization
- Removed metadata and stage directions
- Normalized spelling variants (long s: ſ → s)
- Converted to lowercase
- Preserved complete dialogue for analysis

### 2. TF-IDF Analysis
- Identified distinctive vocabulary for each play
- Compared lexical patterns across genres
- Used scikit-learn's TfidfVectorizer with English stopwords

### 3. Pearson Correlation
- Computed pairwise correlations between all plays
- Identified most/least similar play pairs
- Visualized genre clustering patterns

### 4. Syntactic Complexity
- Analyzed *Julius Caesar* vs. *Antony and Cleopatra*
- Measured: sentence length, clausal density, subordination, coordination, phrasal complexity
- Used spaCy for dependency parsing

## Key Findings

1. **Vocabulary is content-driven**: Character names and setting-specific terms dominate distinctive vocabulary more than genre-based terms

2. **Sub-genre clustering**: Roman plays, Italian comedies, and other thematic groups cluster more tightly than broad genre categories

3. **Syntax operates independently**: Plays with high lexical similarity (r = 0.558) can differ significantly in syntactic complexity, reflecting different dramatic modes (public oratory vs. private conversation)

4. **Genre is real but moderate**: Maximum correlation in corpus is r = 0.558, indicating substantial lexical diversity even between closely related plays

## Technologies Used

- **Python 3.9**
- **Libraries:**
  - pandas, numpy (data manipulation)
  - scikit-learn (TF-IDF, vectorization)
  - spaCy (syntactic parsing)
  - matplotlib, seaborn (visualization)
  - pathlib (file management)

## Installation
```bash
# Clone repository
git clone https://github.com/yourusername/Shakespeare-Text-Analysis.git
cd Shakespeare-Text-Analysis

# Create virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install pandas numpy scikit-learn spacy matplotlib seaborn jupyter

# Download spaCy model
python -m spacy download en_core_web_sm
```

## Usage
```bash
# Navigate to Script directory
cd Script

# Open Jupyter notebook
jupyter notebook shakespeare_eda.ipynb
```

Or run all cells:
```bash
jupyter nbconvert --execute shakespeare_eda.ipynb
```

## Outputs

All visualizations and results are saved to `Output/`:
- TF-IDF bar charts for all plays
- Pearson correlation heatmap
- Syntactic complexity comparisons
- CSV files with detailed results


## Author

Shelly Cao

## Acknowledgments

- [Folger Shakespeare Library](https://www.folger.edu/explore/shakespeares-works/all-works/)  for digitized texts
- IDS 570 course materials and tutorials (Weeks 3-5)
