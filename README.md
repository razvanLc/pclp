# pclp
asd

#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
#include <ctype.h>
#define LMAX 5
#define CMAX 5

int citireM(int v[LMAX][CMAX], int a, int b)
{
    int i, j, l, c;


    for(i = 0; i < a; i++)
    {
        for(j = 0; j < b; j++)
        {
            printf("elementul[%d][%d]: ", i, j);
            scanf("%d", &v[i][j]);
        }
    }
}

int afisareM(int v[CMAX][LMAX], int a, int b)
{
    printf("\n");
    int i, j;
    for(i = 0; i < a; i++)
    {
        for(j = 0; j < b; j++)
        {
            printf("%d\t", v[i][j]);
        }
        printf("\n");
    }
}

int verificareSimet(int v[CMAX][LMAX], int a, int b)
{
    printf("\n");
    int tester = 0, i, j;

    while(a != b)
        return printf("Matricea nu poate fi testata pentru simetrie(Numar linii =/= Numar coloane).\n");

    for(i = 0; i < a; i++)
    {
        for(j = 0; j < b; j++)
        {
            if(v[i][j] != v[j][i])
                tester++;
        }

    }

    if(tester == 0)
        printf("Matricea este simetrica!");
    else
        printf("Matricea nu este simetrica!");


}

void verificarePoz(int v[][CMAX], int a, int b)
{
    int d, i, j, m = 0;
    scanf("%d", &d);
    for(i = 0; i < a; i++)
    {
        for(j = 0; j < b; j++)
        {
            if(d == v[i][j])
                printf("Elementul a fost gasit [%d][%d]\n", i,j);
            m++;

        }
    }
    if(m == 0)
        printf("Elementul cautat nu se afla in matrice!");

}

void spirala(int v[][CMAX], int a)
{
    int j, k;

}






int main()
{
    int v[LMAX][CMAX], l, c, verificare[LMAX][CMAX];
    char menu;

    do
    {
        system("cls");
        printf("Alegeti din urmatoarele variante:");
        printf("\n1 - Citirea matricei:");
        printf("\n2 - Afisarea matricei:");
        printf("\n3 - Simetria matricei.");
        printf("\n4 - Cautare element in matrice.");
        printf("\n5 - Iesire.");
        printf("\n\nOptiunea dvs: ");
        menu = getch();

        switch(menu)

        {

        case '1':
            do
            {
                printf("\nIntroduceti numarul de linii(<=5): ");
                scanf("%d", &l);

            }
            while(l < 0 || l > LMAX);

            do
            {
                printf("Introduceti numarul de coloane(<=5): ");
                scanf("%d", &c);

            }
            while(c < 0 || c > CMAX);
            citireM(v, l, c);
            break;

        case '2':
            afisareM(v, l, c);
            getch();
            break;

        case '3':
            verificareSimet(v, l, c);
            getch();
            break;
        case '4':
            verificarePoz(v, l, c);
            getch();
            break;
        case '5':
            spirala(v, l);
            getch();
            break;

        default:
            printf("\nOptiune inexistenta.");
            getch();
            break;

        }
    }
    while(1);



    return 0;
}


