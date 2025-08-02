# rock-paper-scissors
"A simple Rock-Paper-Scissors game written in python"

import random
print("ROCK-PAPER-SCISSORS: BEST OF 5 🎮")

player_name = input("Enter your name: ")
print(f"\n Welcome❤, {player_name}! Let's begin....")


item_list = ["Rock", "Paper", "Scissors"]
emoji = {
    "Rock": "✊",
    "Paper": "🖐",
    "Scissors": "✌"
}

user_score = 0
comp_score = 0
rounds = 0


while rounds < 5:
    print(f"\nRound {rounds + 1}")
    user_choice = input("Enter your move (Rock, Paper, Scissors): ").capitalize()

    if user_choice.lower() == "exit":
        print("Thanks for playing!👋")
    
    if user_choice not in item_list:
        print("❌ Invalid input! Please choose Rock, Paper, or Scissors.")
        continue  

    comp_choice = random.choice(item_list)

    print(f"👤 {player_name} chooses: {user_choice} {emoji[user_choice]}")
    print(f"💻 Computer chooses: {comp_choice} {emoji[comp_choice]}")

    if user_choice == comp_choice:
        print("⚖️ It's a TIE!")
    elif (user_choice == "Rock" and comp_choice == "Scissors") or \
         (user_choice == "Paper" and comp_choice == "Rock") or \
         (user_choice == "Scissors" and comp_choice == "Paper"):
        print(f"✅ {player_name} WIN this round!")
        user_score += 1
    else:
        print("💻 Computer WINS this round!")
        comp_score += 1

    rounds += 1  

# Final result
print("\n FINAL SCORE 🏁")
print(f"👤 {player_name}: {user_score} | 💻 Computer: {comp_score}")

if user_score > comp_score:
    print(f"🎉 {player_name} WON THE GAME!🏆")
elif comp_score > user_score:
    print("💻 COMPUTER WON THE GAME!🏆")
else:
    print("⚖️ IT'S A DRAW!")




