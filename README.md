from tkinter import*
from tkinter import massagebox
import random

trenutni_igrac=random.choice(["x","o"])
igra_aktivna=True
pobjednik=none

def zamrzni_gumbe():
  b1,config(state=DISABLED)
  b2,config(state=DISABLED)
  b3,config(state=DISABLED)
  b4,config(state=DISABLED)
  b5,config(state=DISABLED)
  b6,config(state=DISABLED)
  b7,config(state=DISABLED)
  b8,config(state=DISABLED)
  b9,config(state=DISABLED)
  
def deaktiviraj_igru():
  global igra_aktivna
  igra_aktivna=False
  pobjednik=trenutni_igrac
  massagebox.showinfo("Križić kružić igra",f"pobijedio je{pobjednik}")
zamrzni_gumbe()
def igraj_krizic_kruzic(gumb):
    global igra_aktivna,trenutni_igrac
    if igra_aktivna:
        igra_igrac(gumb,trenutni_igrac)

def igra_igrac(gumb,igrac):
    if gumb["text"]==" ":
        gumb.config(text=igrac)
        provjeri_kraj_igre()
        promjeni_igraca()
    else:
        messagebox.showerror("krizic kruzic","to nije dozvoljeno polje. Pokusaj ponovo.")


def provjeri_kraj_igre():
    provjeri_pobjedu()
    provijeri_nerijeseno()

def provijeri_pobjedu():
  global b1,b2,b3,b4,b5,b6,b7,b8,b9
  if b1["text"]==b2["text"]==b3["text"]!= " ":
    deaktiviraj_igru()
elif b4["text"]==b5["text"]==b6["text"]!= " ":
    deaktiviraj_igru()
elif b7["text"]==b8["text"]==b9["text"]!= " ":
    deaktiviraj_igru()
elif b1["text"]==b4["text"]==b7["text"]!= " ":
    deaktiviraj_igru()
elif b2["text"]==b5["text"]==b8["text"]!= " ":
    deaktiviraj_igru()
b2["text"]==b5["text"]==b8["text"]!= " ":
    deaktiviraj_igru()
b3["text"]==b6["text"]==b9["text"]!= " ":
    deaktiviraj_igru()
b1["text"]==b5["text"]==b9["text"]!= " ":
    deaktiviraj_igru()
b3["text"]==b5["text"]==b7["text"]!= " ":
    deaktiviraj_igru()

def provijeri_nerijeseno():
    global igra_aktivna
    kliknuti_svi_gumbi=b1["text"]!=" " and b2["text"]!=" " and b3["text"]!=" " and b4["text"]!=" " and b5["text"]!=" " and b6["text"]!=" " and b7["text"]!=" " and b8["text"]!=" " and b9["text"]!=" "
    if pobjednik==None and kliknuti_svi_gumbi:
    igra_aktivna=False
    zamrzni_gumbe()
    messagebox.showinfo("Križić kružić igra","Neriješeno je!")
    
daf promijeni_igraca():
    global trenutni_igrac
    if tranutni_igrac=="x":
      trenutni_igrac="o"
    elif trenutni_igrac=="o":
        trenutni_igrac="o"

root=tk()
root.title("krizic kruzic igra")
b1=button(root,text=" ",font=("helvetica,20"),height=3,widgh=6,bg="white",
command=lambda:igraj_krizic_kruzic(b1))
b2=button(root,text=" ",font=("helvetica,20"),height=3,widgh=6,bg="white",
command=lambda:igraj_krizic_kruzic(b2))
b3=button(root,text=" ",font=("helvetica,20"),height=3,widgh=6,bg="white",
command=lambda:igraj_krizic_kruzic(b3))

b4=button(root,text=" ",font=("helvetica,20"),height=3,widgh=6,bg="white",
command=lambda:igraj_krizic_kruzic(b4))
b5=button(root,text=" ",font=("helvetica,20"),height=3,widgh=6,bg="white",
command=lambda:igraj_krizic_kruzic(b5))
b6=button(root,text=" ",font=("helvetica,20"),height=3,widgh=6,bg="white",
command=lambda:igraj_krizic_kruzic(b6))

b7=button(root,text=" ",font=("helvetica,20"),height=3,widgh=6,bg="white",
command=lambda:igraj_krizic_kruzic(b7))
b8=button(root,text=" ",font=("helvetica,20"),height=3,widgh=6,bg="white",
command=lambda:igraj_krizic_kruzic(b8))
b9=button(root,text=" ",font=("helvetica,20"),height=3,widgh=6,bg="white",
command=lambda:igraj_krizic_kruzic(b9))

b1.grid(row=0,column=0)
b2.grid(row=0,column=1)
b3.grid(row=0,column=2)

b1.grid(row=1,column=0)
b2.grid(row=1,column=1)
b3.grid(row=1,column=2)

b1.grid(row=2,column=0)
b2.grid(row=2,column=1)
b3.grid(row=2,column=2)

root.mainloop()


