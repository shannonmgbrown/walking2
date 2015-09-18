# walking2
walking animation
x = 2
y = 4
round = 1
r = 0
from random import randint
import time, os, sys


def move_up(x, y):
    if y < 10:
        return x , y+1
    else:
        return x, y
        
def move_down(x, y):
    if y > 10:
        return x , y-1
    else:
        return x, y
        
def move_left(x, y):
    if x > 0:
        return x-1 , y
    else:
        return x, y
        
def move_right(x, y):
    if x < 10:
        return x+1 , y
    else:
        return x, y
   
pic = (" " * (x) + "O" + "\n" + " " * (x) + "^" + "\n" + " " * (x) + "|" + "\n" + " " * (x) + "^" + "\n" * y)

def tell_position(x, y_coord):
    print(" " * (x) + "O" + "\n" + " " * (x) + "^" + "\n" + " " * (x) + "|" + "\n" + " " * (x) + "^" + "\n" * y)
    
def clear():
    clear_console = 'clear' if os.name == 'posix' else 'CLS'
    os.system(clear_console)
    sys.stdout.write(pic)
    sys.stdout.flush()
    time.sleep(0.2)
    
def random():
    return randint(1,4)

for i in range(1,10):
    r= random()
    if r == 1:
        x , y = move_up(x, y)
    elif r == 2:
        x , y = move_down(x, y)
    elif r == 3:
        x , y = move_left(x, y)
    elif r == 4:
        x , y = move_right(x, y)
    tell_position(x, y)
    clear()
