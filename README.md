import java .io .BufferedReader ;	
import java .io .InputStreamReader;	
import java .io .IOException ;
	
class Main {	

public static BufferedReader input = new BufferedReader (new InputStreamReader(System.in));	
private static void doEncryption ()throws IOException{
String id = ""; String name = "" ; String message = "" ;  String encrypt_message = "" ;
 int vuid = 0 ; int name_length = 0 ;
 System .out .println ("Please enter your Student ID");
 id = input .readLine(); 
 if( id.length () < 11 || id.length() > 11){	
 System.out.println ("Please enter correct Student ID");
  id = input.readLine();

}else{

id = id.replace("[^\\d]",""); 
 id = id .trim();
 vuid = Integer.parseInt(id);
 System.out.println ("Please enter your full name");
  name = input .readLine ();
 if ( name.length () < 6 ){
 System.out.println ("Please enter full name having aleast 6 characters");

 }else {

 name_length = name.replace (" " , "") . length ();

 }

  System.out.println ("Please enter the message you want to encrypt");
   message = input.readLine ();
  name = input.readLine ();
 if ( message.length () < 10 ){
      System.out.println ("Please enter the  having atleast 10 character");
      message = input.readLine ();
}
 int key = vuid % name length;

 for (int i = 0 ; i < message.length (); i++){
   encrypt_message += Character.toString ((char) (message .charAt (i) ^ key));

 }

 System.out.println ("Encrypted message : "+ encrypt_message);
 System.out.println("Key : "+key);

 } 

 private static void doDecryption()throws IOException {
     String message = "";  String encrypt_message = "";
     System.out.println ("Please enter the message you want to decrypt");
     message = input.readLine ();
 if (message.length () < 10){
      System.out.println ("Please enter the  having atleast 10 character");
      message = input.readLine ();
 }
     System.out.println ("please enter the key")
     int key = Integer.parseInt(input.readline());
  for (int i = 0 ; i < message.length (); i++){
   encrypt_message += Character.toString ((char) (message .charAt (i) ^ key));

 }

 System.out.println ("Encrypted message : " + encrypt_message);

}
	
private void developedBy (){
System .out .println ("Developed By :Tehreem Ehsan (BC170403166);	
      	
}
	
public static void main (String [] args)throws IOException{ 
boolean  check = true ; int choice = 0;
	
do {	
System.out.println ("Press 1   for encryption or 2 for descryption or 3 for exit");	
choice = Integer .parseInt (input .readLine ());

switch (choice){
case 1:
        doEncryption ();
         break ;
case 2:
       doDecryption (); 
          break ;
case 3:
        developedBy (); 
         check = false;
           break ;
default :
         System.out.println (" Please enter correct choice");
   }
}whi1e (check);

}
	
