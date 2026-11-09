# Bank-Account-Management-System
[Bank Account Management System.py](https://github.com/user-attachments/files/34601129/Bank.Account.Management.System.py)
class BankAccount:
    def __init__(self, acc_number, acc_holder, initial_balance):
        self.acc_number = acc_number
        self.acc_holder = acc_holder
        self.balance = initial_balance
        self.transactions = []

    def deposit(self, amount):
        self.balance += amount
        self.transactions.append(f"Deposited {amount}")

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
            self.transactions.append(f"Withdrew {amount}")
        else:
            print("Insufficient funds!")

    def get_balance(self):
        return self.balance

    def get_transaction_history(self):
        for transaction in self.transactions:
            print(transaction)


def main():
    account_number = input("Enter account number: ")
    account_holder = input("Enter account holder name: ")
    initial_balance = float(input("Enter initial balance: "))

    account = BankAccount(account_number, account_holder, initial_balance)

    while True:
      print("\nMenu:")
      print("1. Deposit")
      print("2. Withdraw")
      print("3. Check Balance")
      print("4. Transaction History")
      print("5. Exit")

      choice = input("Enter your choice (1-5): ")

      if choice == '1':
        amount = float(input("Enter deposit amount: "))
        account.deposit(amount)
        print("Deposit successful.")

      elif choice == '2':
        amount = float(input("Enter withdrawal amount: "))
        account.withdraw(amount)

      elif choice == '3':
        print(f"Current Balance: {account.get_balance()}")

      elif choice == '4':
        print("Transaction History:")
        account.get_transaction_history()

      elif choice == '5':
        print("Exiting program. Goodbye!")
        break

      else:
        print("Invalid choice. Please enter a number between 1 and 5.")
      
      print("--------------------------------------")
    


if __name__ == "__main__":
    main()
