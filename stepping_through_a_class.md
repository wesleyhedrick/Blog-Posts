# Stepping Through a Class

### Below is a python class, a couple instances of the class, and a method called on one of the instances.

    class Pet:
        def __init__(self, type, color):
            self.type = type
            self.color = color
            self.fullness = 100
            self.restedness = 100

        def feed(self):
            self.fullness += 50
        
        def rest(self):
            self.restedness += 50


dog = Pet(dog, brown)
cat = Pet(cat, calico)

dog.feed()

## Steps Python Takes When it Runs this Code
1. It notes that there is a class called pet. It stores it (somewhere?), so that it can be used later.
2. It finds on line 21 that a new instance has been created.
    - It finds the Pet class in memory and steps down through it.
    - When it gets to the __init__ function, it runs it because the formulat 'dog = Pet(dog, brown) tells python that this is an instantiation.
    - When it instantiates, it uses the first parameter, self, that could theoretically be anything but is conventionally self, and it stores all the memory info in that variable.
    - Then it proceeds to assign values to the other parameters.
        - self.type = type if translated into English would be something like "I [Python] will assign to this.type the value that you the user put in the type slot of the parameter list.
        - Again the formula self.type = type could be self.yogibear = type. It could be anything and python would keep track of it. But this would mean that when you wanted to know the type of the pet, you would have to use dog.yogibear, which makes for unreadable code. 
        - to abstract further, you could create a class like this (though it could cause other developers to murder you):
    class Pet:
        def __init__(a,b,c,d):
            a.b = b
            a.c = c
            a.d = d
        - The point is that the first parameter in the __init__ function is reserved for all that sets that particular instance apart and it is conventionally called 'self.'
3. When if finds line 22, it performs all the same steps as above. 
4. When it gets to line 24, it goes back to the Pet class and when it gets to the __init__function, it skips right over it because it know that this is not an instantiation of a class but a request to use a method on an actual instance of the pet class. 
5. When it finds the function feed, it runs that function. 
    - But how does it know what to run the function *on*? 
    - It knows because the function is written with the *self* parameter. 
    - Python finds that specific instance and performs the function 'feed' on it. 
    - It searches through all the attributes of that particular instance and when it finds the 'fullness' attribute, it increments it by      50. 





    