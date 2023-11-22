## Knuth-Morris-Pratt (KMP) Algorithm

A highly efficient method for string searching. Improves upon the naive approach by minimizing the number of character comparisons.

### Overview

- **Purpose**: To find occurrences of a pattern within a text string.
- **Efficiency**: Reduces the number of comparisons, especially in cases with many repeated patterns.
- **Complexity**: O(n + m), where n is the length of the text and m is the length of the pattern.

### Components

1. **LPS Array**: Longest Prefix Suffix array.
    - Stores lengths of the longest proper prefix that is also a suffix for each substring.
    - Used to determine where to resume scanning after a mismatch.

2. **Pattern Matching**:
    - Involves comparing the pattern with the text.
    - Utilizes the LPS array to skip unnecessary comparisons.

### Algorithm Steps

1. **Preprocessing**:
    - Compute the LPS array for the pattern.
    - This step involves dynamic calculation based on the pattern's own characters.

2. **Searching**:
    - Traverse the text with the pattern.
    - On mismatch, use the LPS array to shift the pattern efficiently.
    - This prevents re-comparing characters that are already known to match.

### Example

- Pattern: "ABCDAB"
- Text: "ABC ABCDAB ABCDABCDABDE"
- LPS Array: [0, 0, 0, 0, 1, 2]

### Key Advantages

- **Avoids Redundant Comparisons**: Skips parts of the text that are known matches.
- **Time-Efficient**: Especially beneficial when the pattern has repetitive elements.
- **Preprocessing Benefit**: LPS computation is independent of the text, useful for searching a pattern in multiple texts.

### Applications

- Text search in word processors.
- Search engines.
- Data compression algorithms.

In conclusion, the KMP algorithm significantly improves the efficiency of string searching by utilizing the preprocessing of patterns and intelligent skipping during text scanning.
