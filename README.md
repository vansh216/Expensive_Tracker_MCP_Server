# Expense Tracker MCP Server

An MCP (Model Context Protocol) server built with FastMCP for managing and analyzing expenses through AI assistants such as Claude, ChatGPT, Gemini, Cursor, and other MCP-compatible clients.

## Features

### Tools

#### 1. Add Expense

Add a new expense record.

Parameters:

* date
* amount
* category
* subcategory (optional)
* note (optional)

#### 2. List Expenses

Retrieve all stored expenses.

#### 3. Get Expenses by Category

Filter expenses by category.

#### 4. Calculate Total Expenses

Calculate the total amount spent.

#### 5. Summarize Expenses

Generate a spending summary including:

* Total expenses
* Number of transactions
* Category-wise spending
* Highest expense
* Lowest expense
* Average expense

Example Response:

```json
{
  "total_expenses": 12500,
  "transaction_count": 45,
  "average_expense": 277.78,
  "highest_expense": 1500,
  "lowest_expense": 50,
  "category_breakdown": {
    "Food": 3500,
    "Transport": 2200,
    "Shopping": 4800,
    "Bills": 2000
  }
}
```

---

## MCP Resources

### expense://categories

Returns available expense categories.

MIME Type:

```text
application/json
```

Example:

```json
{
  "categories": [
    "Food",
    "Transport",
    "Shopping",
    "Bills",
    "Healthcare",
    "Entertainment",
    "Education",
    "Other"
  ]
}
```

---

## Project Structure

```text
expense-tracker/
│
├── main.py
├── expenses.db
├── categories.json
├── pyproject.toml
├── README.md
└── .venv/
```

---

## Installation

```bash
git clone <repository-url>
cd expense-tracker
uv sync
```

---

## Running the MCP Server

```bash
uv run fastmcp run main.py
```

Development mode:

```bash
uv run fastmcp run main.py --reload
```

---

## Example Expense Record

```json
{
  "date": "2026-06-20",
  "amount": 250,
  "category": "Food",
  "subcategory": "Restaurant",
  "note": "Lunch"
}
```

---

## Database

SQLite is used for storing expenses.

Fields:

* id
* date
* amount
* category
* subcategory
* note

---

## Supported MCP Clients

* Claude Desktop
* ChatGPT MCP Clients
* Gemini MCP Clients
* Cursor
* VS Code MCP Extensions
* Any MCP-compatible MCP client

---

## License

No license specified.
All rights reserved by the project owner unless otherwise stated.
