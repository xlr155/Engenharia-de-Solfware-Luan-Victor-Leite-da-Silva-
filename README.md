# Engenharia-de-Solfware-Luan-Victor-Leite-da-Silva-
Código em C++
Luan Vitor Leite da Silva
5 Ferramentas CASE Fundamenteal para o Desenvolvimento de Solfware

1)Postgres: é um sistema gerenciador de banco de dados objeto relacional, desenvolvido como projeto de código aberto.
2)Microsoft Word:pode ser usado para produzir trabalhos escolares e textos acadêmicos. Com recursos comparáveis a outros editores de texto modernos, suporta também a adição e edição básica de imagens e formatação de texto.
3)Microsoft Visual Studio é um ambiente de desenvolvimento integrado da Microsoft para desenvolvimento de software especialmente dedicado ao .NET Framework e às linguagens Visual Basic, C, C++, C# e F#.
4)NetBeans:é um ambiente de desenvolvimento integrado gratuito e de código aberto para desenvolvedores de software nas linguagens Java, JavaScript, HTML5, PHP, C/C++, Groovy, Ruby, entre outras.
5)Java Development Kit significa Kit de Desenvolvimento Java, e é um conjunto de utilitários que permitem criar sistemas de software para a plataforma Java. É composto por compilador e bibliotecas

#include <iostream>
using namespace std;

int main(){
    setlocale(LC_ALL, "portuguese");
	string nome;
	int idade = 0; 
	float nota_1,nota_2,nota_3,nota_4, media, nota_maior = -1, soma;
	char digite;
	bool sair = false;
	
	
	cout << "\t---<Controle Acadêmico>---\n\n"; //Distanciamento para Centralizar
	cout << "Escolha as Seguntes Opções:\n\n";

	cout << "(1) <Incluir os dados pessoais do Aluno>\n" << endl;
	cout << "(2) <Incluir as Notas do Aluno>\n" << endl;
	cout << "(3) <Exibir a Média Global do Aluno>\n" << endl;
    cout << "(4) <Exibir a Maior Nota do Aluno>\n" << endl;
    cout << "(5) <Sair>\n" << endl;
    
    while(!sair){
    	cout << "\nNúmero Escolhido: ";
    	cin >> digite;
    	
    	switch(digite){
    		case '1': 
    			 cout << "\n\t--|Dados Pessoais|--\n";
    			 cin.ignore();
    			 cout <<"\n-> Nome Completo do Aluno:\n";
    			 getline (cin, nome);
    			 cout << "\n-> Idade: ";
    			 cin >> idade;
    			 break;
    	    case '2':
    	    	 cout << "\n\t--|Nota do Aluno|--\n";
    	         cout << "{Aluno:" << nome << "  }"<< endl;
    	         cout << "\n1°Nota: ";
    	         cin >> nota_1;
    	         cout << "\n2°Nota: ";
    	         cin >> nota_2;
    	         cout << "\n3°Nota: ";
    	         cin >> nota_3;
    	    	 cout << "\n4°Nota: ";
    	     	 cin >> nota_4;
    	         
    	        if(nota_1 >= nota_2 && nota_1 >= nota_3 && nota_1 >= nota_4){
   	             nota_maior = nota_1;
                }else{
   	                if(nota_2 >= nota_1 && nota_2 >= nota_3 && nota_2 >= nota_4){
   	                nota_maior = nota_2;
                }else{            
   	                if(nota_3 >= nota_1 && nota_3 >= nota_2 && nota_3 >= nota_4){
   	                nota_maior = nota_3;
                }else{
   	                nota_maior = nota_4;
                    }	    
                  }
                }
    	    	break;
    	    case '3'://Média global com controle de acesso
    	    	 cout << "\n\t--|Média Global|--\n\n";// Só será acessado com os dados e com as notas do aluno
    	    	if(idade <= 0){                                              
    	    	     cout << "\n|Por Favor, Preencha o Nome do Aluno!|\n\n";
				}else{
				    if(nota_maior <= -1){	
    			     cout << "\n|Preencha as Notas de (" << nome << ")!|\n\n";
			     }else{
    	    	     cout << "Aluno -> " << nome;
    	    	     soma = (nota_1  + nota_2 + nota_3 + nota_4);
    	    	     media = soma/4;
    	    	     cout << "\nMédia: "<< nota_1 << "+" << nota_2 << "+" << nota_3 << "+" << nota_4 << " = " << soma  << "|4___ = " << media << endl; 
					 
			       }
		       }
    	    	break;
    	    case '4': //Maior nota com controle de acesso
    	    	if(idade <= 0 ){
    	    	 	cout << "\n|Por Favor, Preencha o Nome do Aluno!|\n\n";   	    	 	
				}else{
				    if(nota_maior <= -1){  
				     cout << "\n|Preencha as Notas de (" << nome << ") !|\n\n";
			    }else{
    	    	     cout << "\n\t--|Maior Nota|--\n\n";
    	    	     cout << "Aluno -> " << nome;
    	    	     cout << "\nMaior Nota: " << nota_maior << endl;
			       }
			    }
    	    	break;
    	    case '5'://Controle para Finalizar
			    if(idade <= 0 && nota_maior != -1 ){
				    cout << "\n\n| Para finalizar, Conclua os Dados do Aluno |\n\n";
				}else{
					if(nota_maior <= -1 && idade != 0){
				     cout << "\n\n| Para finalizar, Conclua as Notas do Aluno |\n\n";
					}else{
				     cout << "\n\t--|Controle Acadêmico Finalizado|--\n ";
					 sair = true;
				   }
				}
    	    	break;
    		default:
    			cout << "\n\t--| Tecla Inválida |--\n\n";
    			break;	
	  	}	    	  
	}
	return 0;
}
