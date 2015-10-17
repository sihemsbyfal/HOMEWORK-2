# HOMEWORK-2
/**
* Created by sihem on 02/10/2015.
*/
public class personne {

private String nom;

private String prenom;

private String nationalite;

private int nbAmis;

private personne[]Amis;

private int age;

public personne(String nom,String prenom,String nationalite,int age){

this.nom=nom;

this.prenom=prenom;

this.nationalite=nationalite;

this.age=age;
}
public personne(){

}

public personne(personne autre){

nom=autre.nom;

prenom=autre.prenom;

nationalite=autre.nationalite;

age=autre.age;

}

public String toString(){

return "nom"+this.getnom()+"\n prenom"+this.getprenom()+"\n nationalite"+this.getnationalite()+"\n age"+this.getage();
}

public void CreelisteAmis(){

Amis=new personne[4];
}

public void AjouterAmis(personne p){

Amis[nbAmis]=new personne(p);

nbAmis=nbAmis+1;
}

public void MalisteAmis(){

for( personne i:Amis)

System.out.println(i);
}
public void AmisAlgeriens(){
for(int i=0;i<Amis.length;i++){
if(nationalite.equals (Amis[i].nationalite)) /* j'ai utilisé (==) mais elle n'a pas marchée psq c une égalité entre des chaines de carctères */
System.out.println(Amis[i]);
}
}
public void AmisEtrangers(){
for(int i=0;i<Amis.length;i++){
if(! nationalite.equals (Amis[i].nationalite))
System.out.println(Amis[i]);
}
}
//setters and getters //
public String getnom(){
return nom;
}
public String getprenom(){
return prenom;
}
public String getnationalite(){
return nationalite;
}
public int getage(){
return age;
}
public void setnom (String nom){

this.nom=nom;
}
public void setprenom (String prenom){

this.prenom=prenom;
}
public void setnationalite (String nationalite){

this.nationalite=nationalite;

}
public void setage (int age){

this.age=age;

}

}


Test.java
/**
* Created by sihem on 02/10/2015.
*/
public class Test {

public static void main(String[]args){

personne p1=new personne("\n Boukhari","\n Faiza","\n Algerian",20);

personne p2=new personne("\n Besbaci","\n Sarah","\n Algerian",20);

personne p3=new personne("\n Jonis","\n Pierre","\n Frensh",41);

personne p4=new personne("\n Alies","\n Sofia","\n British",16);

personne p=new personne();

p.setnom ("\n Boussetta");

p.setprenom("\n Sihem");

p.setnationalite("\n Algerian");

p.setage(20);


System.out.print("\n je suis \n ");

System.out.println(p);
System.out.println("\n Creation of my list freind's");

p.CreelisteAmis();
System.out.println(" \n Add my freind's List");

p.AjouterAmis(p1);
p.AjouterAmis(p2);
p.AjouterAmis(p3);
p.AjouterAmis(p4);

/* les affichages */

System.out.println("\n\n\n My freinds are :) : ");

p.MalisteAmis();

System.out.println("\n\n\n My Stranger freinds are : ");

p.AmisEtrangers();

System.out.println("\n\n\n My Algerian freinds are :) : ");

p.AmisAlgeriens();

}
