

def create_tracker():
    return {
        "expenses": []
    }


def add_expense(tracker, category, amount):
    for expense in tracker["expenses"]:
        if expense["category"] == category:
            expense["amount"] += amount
            return

    tracker["expenses"].append({
        "category": category,
        "amount": amount
    })


def total_expenses(tracker):
    total = 0
    for expense in tracker["expenses"]:
        total += expense["amount"]
    return total


def expenses_by_category(tracker, category):
    return list(filter(lambda expense: expense["category"] == category, tracker["expenses"]))


def get_categories(tracker):
    return list(map(lambda expense: expense["category"], tracker["expenses"]))


def max_expense(tracker):
    if not tracker["expenses"]:
        return 0

    max_value = tracker["expenses"][0]["amount"]

    for expense in tracker["expenses"]:
        if expense["amount"] > max_value:
            max_value = expense["amount"]

    return max_value


def show_all_expenses(tracker):
    if not tracker["expenses"]:
        print("No expenses")
        return

    for expense in tracker["expenses"]:
        print(f"{expense['category']} - {expense['amount']:.2f}")



tracker = create_tracker()

while True:
    print("""
1. Add expense
2. Show all expenses
3. Total expenses
4. Filter by category
5. Show categories
6. Highest expense
0. Exit
""")

    command = input("Choose option: ")

    if command == "1":
        category = input("Category: ")
        amount = float(input("Amount: "))
        add_expense(tracker, category, amount)
        print("Expense added!")

    elif command == "2":
        show_all_expenses(tracker)

    elif command == "3":
        print("Total:", total_expenses(tracker))

    elif command == "4":
        category = input("Category: ")
        result = expenses_by_category(tracker, category)

        if result:
            for expense in result:
                print(f"{expense['category']} - {expense['amount']:.2f}")
        else:
            print("No expenses in this category")

    elif command == "5":
        categories = get_categories(tracker)
        if categories:
            print("Categories:", categories)
        else:
            print("No categories")

    elif command == "6":
        print("Highest expense:", max_expense(tracker))

    elif command == "0":
        print("Goodbye!")
        break

    else:
        print("Invalid option")
