import re


class UserSession:
    def __init__(self, username, password):  
        self.username = username
        self.password = password
        self.is_signed_in = False

    def sign_in(self, input_username, input_password):
        if self.username == input_username and self.password == input_password:
            self.is_signed_in = True
            print("Sign in successful!")
        else:
            print("Invalid username or password!")

    def sign_out(self):
        if self.is_signed_in:
            self.is_signed_in = False
            print("Signed out successfully!")
        else:
            print("You are not signed in.")

def is_gmail_format(email):
    gmail_regex = r'^[a-zA-Z0-9_.+-]+@gmail\.com$'
    return re.match(gmail_regex, email) is not None 


if __name__ == "__main__":
    user = UserSession("selva@gmail.com", "password123")

  
    username = input("Enter username: ")
    password = input("Enter password: ")
    user.sign_in(username, password)

    
    email = input("Enter your email: ")
    if is_gmail_format(email):
        print("This is a valid Gmail address.")
    else:
        print("Invalid Gmail address.")

   
    user.sign_out()
