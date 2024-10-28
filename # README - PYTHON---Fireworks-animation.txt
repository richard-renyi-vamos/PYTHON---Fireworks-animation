CHATGPT CONVERSATION

********

You said:
create a PYTHON code that displays fireworks animation
ChatGPT said:
ChatGPT
Here's a Python code snippet that uses turtle to display a simple fireworks animation! The turtle module is a great choice for animations because it’s simple to set up and works well for creating visuals like fireworks. 🎇🎆✨

You can run this code in any Python environment that supports the turtle module (usually works well with IDLE or standalone Python installations).

python
Copy code
import turtle as t
import random
import time

# Set up the screen
screen = t.Screen()
screen.bgcolor("black")
screen.setup(width=800, height=600)
screen.title("Fireworks Display")

# Firework class
class Firework:
    def __init__(self):
        self.explosion = t.Turtle()
        self.explosion.shape("circle")
        self.explosion.color(random.choice(["red", "yellow", "blue", "green", "purple", "orange"]))
        self.explosion.penup()
        self.explosion.speed(0)
        self.explosion.goto(random.randint(-350, 350), random.randint(-100, 300))
        self.size = random.randint(10, 20)
        self.explosion.hideturtle()
    
    def explode(self):
        self.explosion.showturtle()
        for _ in range(self.size):
            self.explosion.shapesize(stretch_wid=_ / 5, stretch_len=_ / 5)
            self.explosion.stamp()
            time.sleep(0.05)
        self.explosion.hideturtle()

# Function to launch multiple fireworks
def launch_fireworks():
    fireworks = [Firework() for _ in range(10)]
    for firework in fireworks:
        firework.explode()

# Main animation loop
while True:
    launch_fireworks()

# Close the screen when clicked
screen.exitonclick()
Explanation 🧨:
Firework Class: Each Firework object represents one firework burst, choosing a random color, size, and position.
Explode Method: The firework appears at its random position and "grows" in size as it "explodes," creating a stamp effect.
Launch Fireworks: This function launches multiple fireworks by creating multiple Firework objects in random places.
Run this code, and you’ll see colorful fireworks lighting up the screen!
