![Static Badge](https://img.shields.io/badge/Python-8A2BE2)
![Static Badge](https://img.shields.io/badge/SQL-8A2BE2)

# Database Manager for SQLite

This Python project provides a simple `DatabaseManager` class to interact with an SQLite database. The class includes methods for creating tables, adding, deleting, updating, and checking the existence of items in the database. As an example, I have developed a login page with GUI employing these SQL functions.

## Features

- **Create Table:** Initializes the `users` table with `id`, `name`, `family_name`, and `age` columns.
- **Add Item:** Inserts a new record into the `users` table.
- **Delete Item:** Removes a specific record from the `users` table.
- **Check Item Existence:** Checks if a specific user record exists in the database.
- **Update Item:** Updates a user record based on `user_id`.
- **Close Connection:** Closes the database connection after operations are complete.

## Requirements

- Python 3.x
- SQLite (comes pre-installed with Python)

## Installation

Clone this repository:

   ```bash
   git clone https://github.com/taha-parsayan/Database-Manager-for-SQLite.git
   cd database-manager
   ```

## Usage

To use the `DatabaseManager`, follow these steps:

### 1. Initialize the DatabaseManager

```python
from database_manager import DatabaseManager

db = DatabaseManager("your_db_name.db")  # Optional: Provide your custom DB name
```

### 2. Create the `users` Table

```python
db.create_table()
```

### 3. Add an Item to the Database

```python
db.add_item("John", "Doe", 28)
db.add_item("Jane", "Smith", 32)
```

### 4. Check if an Item Exists

```python
exists = db.item_exists("John", "Doe", 28)
print("John Doe exists:", exists)
```

### 5. Update an Item

```python
db.update_item(user_id=1, age=29)  # Update age for user with id 1
```

### 6. Delete an Item from the Database

```python
db.delete_item("John", "Doe", 28)
```

### 7. Close the Connection

```python
db.close_connection()
```

## Example Usage

Here's an example script to demonstrate how the class works:

```python
if __name__ == "__main__":
    db = DatabaseManager()
    db.create_table()

    # Adding items
    db.add_item("John", "Doe", 28)
    db.add_item("Jane", "Smith", 32)

    # Check if an item exists
    exists = db.item_exists("John", "Doe", 28)
    print("John Doe exists:", exists)

    # Update an item
    db.update_item(1, age=29)

    # Delete an item
    db.delete_item("John", "Doe", 28)

    # Close the connection when done
    db.close_connection()
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
