from tkinter import*
import random
root = Tk()
root.title("CoinSnatcher alpha") 
w=640
h=320
main = Canvas(width=w,height=h,bg='lightblue')
main.pack()
menu = Canvas(width = w, height = 50, bg= "lightgreen" )
menu.pack()
class Player:
    x1=0
    y1=h-20
    x2=20
    y2=w/2
    score=0
    scorevar = IntVar()
    scorevar.set(0)
    player = main.create_rectangle([x1,y1],[x2,y2], fill="black")
       
    def move_up(self, event):
         if self.y1!=0:
             main.move(self.player,0,-20)
             self.y1-=20
             self.y2-=20
             self.check(coin1)
          
    def move_down(self, event):
         if self.y2!=320:
             main.move(self.player,0,20)
             self.y1+=20
             self.y2+=20
            ## print("y1=",y1)
            ## print("y2=",y2)
             self.check(coin1)
         
    def move_left(self, event):
         if self.x1!=0:
              main.move(self.player,-20,0)
              self.x1-=20
              self.x2-=20
              ##print("x1=",x1)
              ##print("x2=",x2)
              self.check(coin1)
              
    def move_right(self, event):
         if self.x2!=640:
              main.move(self.player,20,0)
              self.x1+=20
              self.x2+=20
              ##print("x1=",x1)
              ##print("x2=",x2)
              self.check(coin1)
    def check(self, coin1):
        if self.x1==coin1.a and self.y1==coin1.b and self.x2==coin1.a+20 and self.y2==coin1.b+20:
            main.delete(coin1.coins)
            ##print('IT WORKS')
            self.score+=1
            self.scorevar.set(self.score)
            ##print("SCORE111 = ",self.scorevar.get())
            ##print("SCORE = ",self.score)
            
            coin1.new_coin()
        
class Coin:
    a=random.randrange(0,640,20)
    b=random.randrange(0,320,20)
    coins = main.create_rectangle([a+20,b],[a,b+20], fill="yellow")
    ##print("Coordinates of coin is a1=",a,"b1=",b,"a2=",a+20,"b2=",b+20)
    def new_coin(self):
            self.a=random.randrange(0,640,20)
            self.b=random.randrange(0,320,20)
            self.coins = main.create_rectangle([self.a+20,self.b],[self.a,self.b+20], fill="yellow")
            ##print("Coordinates of coin is a1=",self.a,"b1=",self.b,"a2=",self.a+20,"b2=",self.b+20)
        
    
######PLAYER AND CONTROLS##############
Player1=Player()        
main.bind('<w>',Player1.move_up)
main.bind('<s>',Player1.move_down)
main.bind('<a>',Player1.move_left)
main.bind('<d>',Player1.move_right)
    
#######################################
coin1 = Coin()
textv = Label(menu, textvariable = Player1.scorevar, font="Verdana 20", fg = "Black", bg = "Yellow")
##menu.create_text(10,20,text="SCORE:"+str(Player1.scorevar.get()), font="Verdana 12",anchor="w",justify=LEFT,fill="red")
textv.pack()
main.focus_set()     
mainloop()    
