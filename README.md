print("===================================")
print("   FRAUD TRANSACTION DETECTOR")
print("===================================")

amount = float(input("Enter transaction amount: ₹"))
transaction_type = input("Enter transaction type (Online/ATM/UPI): ")
hour = int(input("Enter transaction hour (0-23): "))

risk = 0

# Check transaction amount
if amount > 50000:
    risk += 40

# Check transaction time
if hour < 6 or hour > 23:
    risk += 30

# Check transaction type
if transaction_type.lower() == "online":
    risk += 10

print("\n-----------------------------------")
print("Transaction Analysis")
print("-----------------------------------")

print("Amount: ₹", amount)
print("Type:", transaction_type)
print("Time:", hour, ":00")
print("Risk Score:", risk, "%")

if risk >= 50:
    print("⚠️ RESULT: POTENTIAL FRAUD")
else:
    print("✅ RESULT: LEGITIMATE TRANSACTION")

print("-----------------------------------") 