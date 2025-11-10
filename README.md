# Database Design and Normalization

A comprehensive database design project demonstrating normalization techniques, ER modeling, and advanced SQL query implementations using MySQL.

## 🎯 Project Overview

This repository contains two major database design assignments:

1. **Normalization Analysis** - Analysis of TechCrunch startup funding data, transforming it from a flat CSV file into a properly normalized 3NF relational database
2. **Recipe Database Implementation** - SQL implementation featuring complex JOIN operations, data insertion, and multi-table queries

## 💻 Technologies Used

- **Database:** MySQL 8.0
- **Tools:** MySQL Workbench
- **Languages:** SQL
- **Data Formats:** CSV, SQL scripts
- **Documentation:** Markdown, PDF

## 📁 Project Structure

```
database-design-normalization/
│
├── Part1-Normalization/
│   ├── techcrunch.csv                    # Original dataset
│   ├── normalization-analysis.pdf        # Detailed analysis document
│   └── README.md                         # Part 1 documentation
│
├── Part2-Recipe-Database/
│   ├── recipes.sql                       # Original database schema
│   ├── complete-assignment.sql           # Complete solution with all 3 parts
│   ├── screenshots/                      # Query result screenshots
│   └── README.md                         # Part 2 documentation
│
└── README.md                             # This file
```

## 📊 Part 1: Data Normalization

### Overview
Analysis of the TechCrunch startup funding dataset to identify normalization violations and design a properly normalized database schema.

### Dataset
- **Source:** TechCrunch funding records
- **Records:** 523 funding events
- **Attributes:** company, funding amount, date, location, category, round type

### Deliverables
1. **Primary Key Analysis** - Identification of valid and invalid primary key candidates
2. **Normal Form Assessment** - Evaluation of 1NF, 2NF, and 3NF compliance
3. **ER Diagram** - Proposed entity-relationship design achieving 3NF
4. **Normalized Schema** - Five-table design eliminating redundancy

### Key Findings
- ✅ Original data satisfies 1NF (atomic values)
- ❌ Violates 2NF (company information redundancy)
- ❌ Violates 3NF (transitive dependencies)

### Proposed Solution
Normalized into 5 tables:
- **COMPANIES** - Unique company information
- **FUNDING_EVENTS** - Individual funding transactions
- **CATEGORIES** - Business category lookup
- **LOCATIONS** - City-state combinations
- **FUNDING_ROUNDS** - Round type definitions

**Relationships:**
- COMPANIES → FUNDING_EVENTS (1:M)
- CATEGORIES → COMPANIES (1:M)
- LOCATIONS → COMPANIES (1:M)
- FUNDING_ROUNDS → FUNDING_EVENTS (1:M)

## 🍳 Part 2: Recipe Database

### Overview
Implementation of a recipe management database with complex multi-table relationships and JOIN operations.

### Database Schema
- **recipe_main** - Recipe details (title, description, times, difficulty)
- **rec_ingredients** - Recipe-ingredient relationships with amounts
- **ingredients** - Ingredient master list
- **categories** - Recipe categories

### Assignment Tasks

#### Task 1: Data Insertion
- Inserted 2 new recipes: **Cinnamon Rolls** and **Banana Shake**
- Added new category: **Beverages**
- Added 10 new ingredients
- Properly linked recipes to ingredients with amounts

#### Task 2: Multi-Table JOIN Query
- Retrieved all information for the two new recipes
- Used INNER JOINs across all 4 tables
- Demonstrated understanding of foreign key relationships

#### Task 3: Filtered SELECT with Sorting
- Selected specific columns: recipe name, category, ingredient name, amount
- Applied complex sorting: category DESC → recipe ASC → ingredient DESC
- Works for all recipes in the database

### SQL Features Demonstrated
- `INSERT INTO` statements with proper foreign key references
- `INNER JOIN` across multiple tables
- `WHERE` clause filtering
- `ORDER BY` with multiple columns
- Aggregate relationships (1:M)
- Primary and foreign key constraints

## 🔑 Key Concepts Covered

### Database Design
- Entity-Relationship (ER) modeling
- Primary and foreign key selection
- Referential integrity
- Table relationships (1:1, 1:M, M:N)

### Normalization
- First Normal Form (1NF) - Atomic values
- Second Normal Form (2NF) - No partial dependencies
- Third Normal Form (3NF) - No transitive dependencies
- Redundancy elimination
- Anomaly prevention (insertion, update, deletion)

### SQL Operations
- Complex JOIN operations
- Multi-table queries
- Data insertion with foreign keys
- Filtering and sorting
- Query optimization

## 🚀 How to Run

### Prerequisites
- MySQL Server 8.0 or higher
- MySQL Workbench (recommended)

### Part 1: Normalization Analysis
1. Open `techcrunch.csv` in Excel or import to MySQL
2. Review the analysis in `normalization-analysis.pdf`
3. (Optional) Implement the proposed normalized schema using provided SQL

### Part 2: Recipe Database
1. Open MySQL Workbench
2. Run `recipes.sql` to create the initial database:
   ```sql
   SOURCE /path/to/recipes.sql;
   ```
3. Run `complete-assignment.sql` to execute all three parts:
   ```sql
   SOURCE /path/to/complete-assignment.sql;
   ```
4. Verify results by checking the screenshots folder

### Expected Results
- Part 1: Properly normalized 5-table schema
- Part 2: 4 recipes total (2 original + 2 new)
- Part 2: All queries execute successfully with no errors

## 📚 Learning Outcomes

Through this project, I demonstrated proficiency in:

✅ **Database Design Principles**
- Identifying entity relationships
- Creating normalized schemas
- Designing efficient table structures

✅ **Normalization Techniques**
- Analyzing datasets for normal form compliance
- Eliminating data redundancy
- Preventing update/insertion/deletion anomalies

✅ **SQL Proficiency**
- Writing complex multi-table JOIN queries
- Implementing proper foreign key relationships
- Data manipulation (INSERT, SELECT)
- Query optimization and sorting

✅ **Problem Solving**
- Analyzing real-world datasets
- Transforming flat data into relational structures
- Documenting technical decisions

## 📝 Notes

- All SQL scripts are thoroughly commented for clarity
- Screenshots demonstrate successful query execution
- ER diagrams follow standard notation (crow's foot)
- Code follows MySQL 8.0 syntax standards



This project is part of academic coursework for Database Management Systems.

---

**Course:** Database Management Systems  
**Institution:** [Your University]  
**Semester:** [Current Semester/Year]
