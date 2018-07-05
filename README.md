# Programa 13

Linguagem Utilizada: C++.

Programa com menu que faz leitura do sexo, idade e salário de pessoas e retorna a quantidade de mulheres registradas, média dos salários das mulheres e a soma dos salários dos homens.

Programa Desenvolvido no DEV C++ IDE.

Código:

#include "iostream"
#include "cstdlib"
#include "iomanip"
using namespace std;

struct vet{
       string sexo;
       float salar;
       int idade;
       
};
struct vet cadastro[10];

int qtdmulheres = 0;
float mediamulheres = 0, somahomens = 0;

int menu() 
{
	     int tecla;
         system("cls");
	     cout << "\n**Tela Inicial**\n";
         cout << "\n1 - Entrar com valores";
         cout << "\n2 - Exibir dados";
         cout << "\n3 - Sair \n" << endl;
         cin >> tecla;
return tecla;}

int main() {
	setlocale(LC_ALL,"Portuguese");
	int linha = -1, tecla = 0, sex, cont;
	while(tecla != 3)
	{
		tecla = menu();
		
		switch(tecla)
		{
			case 1:
				{
					linha ++;
					cont = 0;
					sex = 0;                                                                                     
					while (cont == 0)
					{
						system("cls");
						cout << "Digite seu sexo: [1] Para Masculino / [2] Para Feminino" << endl;
						cin >> sex;
						
						if (sex == 1)
						{
						  cont = 1;	
						  cadastro[linha].sexo = "Masculino";
						}
						
						if (sex == 2)
						{
						   cadastro[linha].sexo = "Feminino";
						   cont = 1;
						   qtdmulheres = qtdmulheres + 1;	
						}
					}
					
					system("cls");
					
					cout << "Digite sua idade: " << endl;
					cin >> cadastro[linha].idade;
					
					system("cls");
					
					cout << "Digite seu salário: " << endl;
					cin >> cadastro[linha].salar;
					
					if (sex == 1) {
					   somahomens = somahomens + cadastro[linha].salar;	
					}
					
					else {
						mediamulheres = mediamulheres + cadastro[linha].salar;
					}
					
										
					break;
				}
			
			case 2:
				{
					if (linha >= 0)
					{
						system("cls");
						cout << "Quantidade de mulheres na lista = " << qtdmulheres << endl;
						cout << fixed << setprecision(2);
						cout << "Média dos salários das mulheres = " << (mediamulheres/qtdmulheres) << endl;
						cout << fixed << setprecision(2);
						cout << "Soma dos salários dos homens = " << somahomens << endl;
						system("pause");
						
					}
					break;
				}
		}
	}
return 0;}
