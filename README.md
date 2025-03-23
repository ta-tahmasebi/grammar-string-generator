# Grammar String Generator ![CFG Generator](https://img.shields.io/badge/Grammar-Generator-blueviolet?style=for-the-badge)

## Overview
This project provides a Python-based **Grammar String Generator** that expands grammar rules to generate terminal strings. It uses a **breadth-first search (BFS) approach** to iteratively apply grammar rules and produce valid strings.

## Features
- Supports **custom Grammar rules**
- Ensures **validity of grammar inputs**
- Uses **BFS** to systematically explore string generations
- **Handles infinite loops** with a step limit
- Includes **example grammars** for testing

Note: the current implementation only supports grammar rules where variables and terminals are single characters. However, we have plans to extend this functionality to support multi-character variables and terminals in future updates.



## Installation
Install the required dependency before running the script:
```shell
pip install colorama
```
Then, clone the repository:
```sh
# Clone this repository
git clone https://github.com/ta-tahmasebi/grammar-string-generator.git
cd grammar-string-generator
```

## Usage
Run the script directly to generate example strings:
```sh
python generate_strings.py
```

### Custom Usage
To define a custom grammar, modify or add new examples like this:
```python
from generate_strings import GrammarGenerator

grammar = [
    ('S', ''),      # S -> epsilon
    ('S', 'A'),     # S -> A
    ('A', 'aABC'),  # A -> aABC
    ('A', 'abC'),   # A -> abC
    ('CB', 'BC'),   # CB -> BC
    ('bB', 'bb'),   # bB -> bb
    ('bC', 'bc'),   # bC -> bc
    ('cC', 'cc'),   # cC -> cc
]

try:
    generator = GrammarGenerator.generate_strings(grammar, start='S', max_steps=10000, debug=False)
    for result in generator:
        print(f'"{result}"')
except Exception as e:
    print(f"Fatal error: {e}")

```

## Contributing 🤝
Feel free to submit pull requests or report issues to improve the project.

# Made with ❤️


