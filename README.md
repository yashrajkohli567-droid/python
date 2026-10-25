correct_pin = "1234"
balance = 10000
att = 0
transaction = []
while att<3:
    pin = (input("Enter PIN:- "))
    if pin == correct_pin:
        break
    else:
        att +=1
        if att<3:
            print("Wrong PIN. Attempts left", 3-att)
        else:
            print("Card Blocked")
if pin == correct_pin:
    while True:
        print("\n1. Balance")
        print("2. Deposit")
        print("3. Withdraw")
        print("4. Exit")

        choice = input("Enter choice: ")

        if choice =="1":
            print("Balance: ", balance)
        elif choice == "2":
            amount = int(input("Enter amount to deposit:- "))
            if amount > 0:
                balance += amount
                transaction.append("Deposit: " + str(amount))
                print("New balance:", balance)
            else:
                print("Amount must be above Zero")
        elif choice =="3":
            amount = int(input("Enter the amount to withdraw: "))
            if amount>balance:
                print("Insufficient balance")
            elif amount>0:
                balance = balance - amount
                transaction.append("Withdraw: " + str(amount))
                print("New balance:", balance)
            else:
                print("Amount must be above Zero")
        elif choice=="4":
            print("Thank you!")
            print("\nTransaction History:")
            for item in transaction:
                print(item)

            break
        else:
            print("Invalid Choice")

students = {
    "Aman": [85, 90, 78],
    "Riya": [92, 88, 95],
    "Zoya": [70, 65, 80]
}

for name in students:
    marks = students[name]

    avg = sum(marks) / len(marks)

    if avg >= 85:
        grade = "A"
    elif avg >= 70:
        grade = "B"
    elif avg >= 50:
        grade = "C"
    else:
        grade = "F"

    print(name, round(avg, 2), grade)

highest_avg = 0
topper = ""

for name in students:
    avg = sum(students[name]) / len(students[name])

    if avg > highest_avg:
        highest_avg = avg
        topper = name

print("Topper:", topper)

while True:
    print("\n1. Add student")
    print("2. View all")
    print("3. Show topper")
    print("4. Exit")

    choice = input("Enter choice: ")

    if choice == "1":

        name = input("Enter student name: ")

        if name in students:
            print("Student already exists.")
            continue

        marks = []

        while len(marks) < 3:
            mark = int(input("Enter mark: "))

            if mark >= 0 and mark <= 100:
                marks.append(mark)
            else:
                print("Invalid mark, try again.")

        students[name] = marks

    elif choice == "2":

        for name in students:
            avg = sum(students[name]) / len(students[name])

            if avg >= 85:
                grade = "A"
            elif avg >= 70:
                grade = "B"
            elif avg >= 50:
                grade = "C"
            else:
                grade = "F"

            print(name, round(avg, 2), grade)

    elif choice == "3":

        highest_avg = 0
        topper = ""

        for name in students:
            avg = sum(students[name]) / len(students[name])

            if avg > highest_avg:
                highest_avg = avg
                topper = name

        print("Topper:", topper)

    elif choice == "4":
        print("Goodbye!")
        break

    else:
        print("Invalid choice")

