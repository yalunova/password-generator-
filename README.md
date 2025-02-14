import random
import string

def generate_password(length=12):
    """Generates a secure password of a given length."""
    if length < 8:
        print("Password must be at least 8 characters long.")
        return None

    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

# User input for password length
try:
    length = int(input("Enter password length (8 to 16): "))
    if 8 <= length <= 16:
        print("Generated password:", generate_password(length))
    else:
        print("Error: Password length must be between 8 and 16 characters.")
except ValueError:
    print("Error: Please enter a number.")
