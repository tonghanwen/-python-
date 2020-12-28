import tkinter as tk
import time
root = tk.Tk()
root.geometry('500x500')
def uptime():
    s = []
    w = time.localtime()
    for e in w:
        s.append(e)
    a = s[0],'年',s[1],'月',s[2],"日"
    text1 = tk.Label(root,text = a,width = 40,bg = 'red')
    text1.place(x = 0,y = 20)
    b = f'周{s[6]+1}'
    text2 = tk.Label(root,text = b,width = 40,bg = 'yellow')
    text2.place(x = 0,y = 40)
    c = s[3],":",s[4],":",s[5]
    text3 = tk.Label(root,text = c,width = 40,bg = 'green')
    text3.place(x = 0,y = 60)
    root.after(1000,uptime)
uptime()
e = tk.Label(root,text = '秒数',width = 40)
e.place(x = 0, y = 80)
entry = tk.Entry(root,width = 40)
entry.place(x = 0, y = 100)
def get_into():
    def finish():

        t = tk.Label(root,text = '完成',width = 40)
        t.place(x = 0, y = 140)
        def fresh():
            fresh1 = tk.Label(root,text = '',width = 40)
            fresh1.place(x = 0, y = 140)
        root.after(3000,fresh)
    r = entry.get()
    root.after(int(r)*1000,finish)
button = tk.Button(root,text = '计时',command = get_into)
button.place(x = 0, y = 120)
root.mainloop()
