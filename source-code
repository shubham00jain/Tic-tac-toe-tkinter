from tkinter import *
from tkinter.messagebox import *
win=[{0,1,2},{3,4,5},{6,7,8},{0,3,6},{1,4,7},{2,5,8},{0,4,8},{2,4,6}]
root=Tk()
root.config(bg='powder blue')
root.title("My Game")
def Player(t):
    global pl,buttonlist,ps1,ps2,count
    if pl:
        buttonlist[3*t[0]+t[1]]['bg']='red'
        ps1.add(3*t[0]+t[1])
        pl=False
    else:
        buttonlist[3*t[0]+t[1]]['bg']='green'
        ps2.add(3*t[0]+t[1])
        pl=True
    buttonlist[3*t[0]+t[1]]['state']='disable'
    count+=1
    if count>=5:
        if pl==False:
            for s in win:
                if s.issubset(ps1):
                    showinfo("Result","Player 1 won")
                    Initial()
                    return
        else:
            for s in win:
                if s.issubset(ps2):
                    showinfo("Result","Player 2 won")
                    Initial()
                    return
            
    if count==9:
        showinfo("Result","Game Draw")
        Initial()
def Start():
    global buttonlist,count,pl,ps1,ps2
    for b in buttonlist:
        b['state']='active'
    count=0        
    pl=True
    ps1=set()
    ps2=set()
def Initial():
    global buttonlist
    buttonlist=[]
    for i in range(3):
        for j in range(3):
            buttonlist.append(Button(root,state='disable',command=lambda t=(i,j):Player(t)))
            buttonlist[-1].grid(row=i,column=j,padx=5,pady=5,sticky='nswe')
Initial()
start=Button(root,text="Start",command=Start)
start.grid(row=3,column=1,padx=5,pady=5,sticky='nswe')
for i in range(4):
    root.grid_rowconfigure(i,weight=1)
for i in range(3):
    root.grid_columnconfigure(i,weight=1)
root.mainloop()
