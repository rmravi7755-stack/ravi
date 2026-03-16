class ATM:
  def _init_(self):
    self.pin=''
    self.balance=0
    self.menu()
  def menu(self):
    print('''
    1) press 1 to create pin.
    2) press 2 to cash Withdrwal.
    3) press 3 to cash Deposit.
    4) press 4 to cash Transfar.
    5) press 5 to check Balance.
    6) press 6 to exit.
    ''')
    user_choice = input("Please Enter your choice: ")
    if user_choice == '1':
      self.create_pin()
    elif user_choice == '2':
      self.cash_withdrawl()
    elif user_choice == '3':
      self.cash_deposit()
    elif user_choice == '4':
      self.cash_transfar()
    elif user_choice == '5':
      self.check_balance()
    elif user_choice == '6':
      exit()
    else:
      print("Invalid choice")
  def create_pin(self):
       ask1 = input(" Enter your pin: ")
       self.pin == ask1
       print("Pin set successfully")
       self.menu()
  def cash_withdrawl(self):
    ask2 = input("Enter your pin: ")
    if ask2 == self.pin:
      ask3 = int(input("Enter your amount: "))
      if ask3 <= self.balance:
        self.balance = self.balance - ask3
        print("Please collect your cash")
        print("your remaing Balance is",self.balance)
      else:
        print("Insufficient balance")
    else:
      print("Invalid pin")
      self.menu()
  def cash_deposit(self):
    ask2 = input("Enter your pin: ")
    if ask2 == self.pin:
      ask3 = int(input("Enter amount to deposit: "))
      self.balance = self.balance + ask3
      print("Amount deposited successfully.")
      print("Your current balance is", self.balance)
    else:
      print("Invalid pin")
    self.menu()


  def cash_transfar(self):
    ask2 = input("Enter your pin: ")
    if ask2 == self.pin:

      recipient_account = input("Enter recipient's account number: ")
      transfer_amount = int(input("Enter amount to transfer: "))
      if transfer_amount <= self.balance:
        self.balance -= transfer_amount
        print(f"Successfully transferred {transfer_amount} to {recipient_account}")
        print("Your remaining balance is", self.balance)
      else:
        print("Insufficient balance for transfer.")
    else:
      print("Invalid pin")
    self.menu()


  def check_balance(self):
    ask2 = input("Enter your pin: ")
    if ask2 == self.pin:
      print("Your current balance is", self.balance)
    else:
      print("Invalid pin")
    self.menu()
