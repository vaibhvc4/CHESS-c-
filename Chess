#include <stdio.h>
#include<stdlib.h>
#include<time.h>
#include<conio.h>
void black();
void wcheck();
int bcheck();
void white();
void wcall();
int pieces[8][8] = {{0,0,0,0,0,0,0,0},
                    {0,0,0,0,0,0,0,0},
                    {0,0,0,0,0,0,0,0},
                    {0,0,0,0,0,0,0,0},
                    {0,0,0,0,0,0,0,0},
                    {0,0,0,0,0,0,0,0},
                    {0,0,0,0,0,0,0,0},
                    {0,0,0,0,0,0,0,0}
                };
int board[8][8] =  {{22,42,32,62,52,32,42,22},
                    {12,12,12,12,12,12,12,12},
                    {0,0,0,0,0,0,0,0},
                    {0,0,0,0,0,0,0,0},
                    {0,0,0,0,0,0,0,0},
                    {0,0,0,0,0,0,0,0},
                    {11,11,11,11,11,11,11,11},
                    {21,41,31,61,51,31,41,21}
};
int fake_pieces[8][8] ={{0,0,0,0,0,0,0,0},
                        {0,0,0,0,0,0,0,0},
                        {0,0,0,0,0,0,0,0},
                        {0,0,0,0,0,0,0,0},
                        {0,0,0,0,0,0,0,0},
                        {0,0,0,0,0,0,0,0},
                        {0,0,0,0,0,0,0,0},
                        {0,0,0,0,0,0,0,0}
                    };
                    
int fake_board[8][8] ={ {22,42,32,62,52,32,42,22},
                        {11,12,12,12,12,12,12,12},
                        {0,0,0,0,0,0,0,0},
                        {0,0,0,0,0,0,0,0},
                        {0,0,0,0,0,0,0,0},
                        {0,0,0,0,0,0,0,0},
                        {12,11,11,11,11,11,11,11},
                        {22,41,31,51,61,31,41,21}
};
void initializep();
 void displayp()
{
    int i,j;
    printf("\n     1   2   3   4   5   6   7   8\n");
    printf("\n");
    for(i=0;i<8;i++)
    {
        printf("%d  ",i+1);
        for(j=0;j<8;j++)
        {
            if(pieces[i][j]==0)
                printf("  --");
           
            else if(pieces[i][j]==99)
            {
                printf("  K ");
            }
           
            else
                printf("  %d",pieces[i][j]);
           
        }
        printf("\n");
    }
};

int no_pos()
{
    int temp=0, i,j;
    for(i=0;i<8&& temp==0;i++)
    {
        for(j=0;j<8&& temp==0;j++)
        {
            if(pieces[i][j]!=0)
            {
                temp=1;
           
            }
        }
    }
    return(temp);
}
void wrevive(int x, int y)             //white's revive function
{
    int ch;
    come_here:
    printf("\n White can revive it's piece");
    printf("\n1. Queen \n2. Bishop \n3. Rook \n4. Knight");
    scanf("%d", &ch);
    switch(ch)
    {
        case 1:
            board[x][y] = 61;
            break;
        case 2:
            board[x][y] = 31;
            break;
        case 3:
            board[x][y] = 21;
            break;
        case 4:
            board[x][y] = 41;
            break;
        default:
            goto come_here;
            
    }
    
};
void brevive(int x, int y)
{
    int ch;
    cum_here:
    printf("\n Black can revive it's piece");
    printf("\n1. Queen \n2. Bishop \n3. Rook \n4. Knight");
    scanf("%d", &ch);
    switch(ch)
    {
        case 1:
            board[x][y] = 62;
            break;
        case 2:
            board[x][y] = 32;
            break;
        case 3:
            board[x][y] = 22;
            break;
        case 4:
            board[x][y] = 42;
            break;
        default:
            goto cum_here;
            
    }

};
void initializefake(){
      int i,j;
      for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
            fake_pieces[i][j]=0;
          }
      }

    };







void bcall(){
    int i,x,y,j,z,m;
    for(x=0;x<8;x++)
    {
        for(y=0;y<8;y++)
        {
            if(board[x][y]%10==2)
            {
                if(board[x][y]/10==1) //bpawn
                {
       
        if(y>0){
        if ((board[x+1][y-1]%10!=2)&&(board[x+1][y-1]==0))
        {
          pieces[x+1][y-1] = 66;
           }
           else if(board[x+1][y-1]==51)
           pieces[x+1][y-1]=77;
        }
       
        if(y<7){
        if((board[x+1][y+1]%10!=2)&&(board[x+1][y+1]==0))
        {
           
            pieces[x+1][y+1]=66;
            }
               else if(board[x+1][y+1]==51)
           pieces[x][y]=77;
        }
        }
       
       
   
       
        if(board[x][y]/10==2)//brook
        {
            for(i=x,j=y-1;j>-1;j--)//left
            {       if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
                if(board[i][j]==0)
                { 
                    pieces[i][j]=66;
                }
                else if(board[i][j]%10==1||board[i][j]%10==2)
                {
                    break;
                }
            }
                     
     
                   for(i=x-1,j=y;i>-1;i--)//backward
       {   if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
           
          if(board[i][j]==0)
                {
                    pieces[i][j]=66;
                }
                else if(board[i][j]%10==1||board[i][j]%10==2)
                {
                    break;
                }
         
               
           
        }
        for(i=x+1,j=y;i<8 ;i++)//forward
        {  if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
           
          if(board[i][j]==0)
                {
                    pieces[i][j]=66;
                }
                else if(board[i][j]%10==1||board[i][j]%10==2)
                {
                    break;
                }
               
        }
         for(i=x,j=y+1;j<8;j++)//right
        {  
           if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
          if(board[i][j]==0)
                {
                    pieces[i][j]=66;
                }
                else if(board[i][j]%10==1||board[i][j]%10==2)
                {
                    break;
                }
               
           
        }
       
       
        }
        if(board[x][y]/10==3)                   // bbishop
        {
               for(i=x+1,j=y+1;i<=7&&j<=7;i++,j++) // right down
    { if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
           
            break;
        }
       
     
    }
   
    for(i=x+1,j=y-1;i<=7&&j>=0;i++,j--)// left down
    {   if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
     
            break;
        }
       
    }
   
    for(i=x-1,j=y-1;i>=0&&j>=0;i--,j--) //  left up
    {    if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
       
            break;
        }
       
    }
    for(i=x-1,j=y+1;i>-1&&j<=7;i--,j++) // right up
    {   if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
   
            break;
        }

     
    }
        }
        
        if (board[x][y]/10==6)          // bqueen
        {
             for(i=x+1,j=y;i<8;i++) //downward
    {  if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
     
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
         
            break;
        }
     
    }
    for(i=x-1,j=y;i>=0;i--) //upward
    { if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
     
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
           
            break;
        }
         
    }
    for(i=x, j=y-1;j>=0;j--) //left
    {   if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
       
            break;
        }
   
   
    }
    for(i=x, j=y+1;j<8;j++) //right
    {   if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
       
            break;
        }
   
    }
    for(i=x+1,j=y+1;i<8 && j<8;i++,j++) //down right
    {    if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
       
            break;
        }
   
   
    }
    for(i=x+1,j=y-1; i<8 && j>=0;i++,j--)//down left
    {    if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
         
            break;
        }
     
     
    }
    for(i=x-1, j=y+1; i>=0 && j<8;i--,j++)// up right
    {    if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
           
            break;
        }
       

    }
    for(i=x-1, j=y-1; i>=0 && j>=0;i--,j--) // up left
    {   if(board[i][j]==51)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==1||board[i][j]%10==2)
        {
       
            break;
        }
     
   
    }
        }
        if(board[x][y]/10==4)       //bknight
        { if(y>0) // down left
    {
        if(board[x+2][y-1]==0)
        {
            pieces[x+2][y-1]=66;
        }
       
          if(board[x+2][y-1]==51)
                        pieces[x+2][y-1]=77;
    }
    if(y<7)// down right
    {
        if(board[x+2][y+1]==0)
        {
            pieces[x+2][y+1]=66;
        }
       
          if(board[x+2][y+1]==51)
                        pieces[x+2][y+1]=77;
    }
    if(y>0) //up left
    {
        if(board[x-2][y-1]==0)
        {
            pieces[x-2][y-1]=66;
        }
       
          if(board[x-2][y-1]==51)
                        pieces[x-2][y-1]=77;
    }
    if(y<7) //up right
    {
        if(board[x-2][y+1]==0)
        {
            pieces[x-2][y+1]=66;
        }
       
          if(board[x-2][y+1]==51)
                        pieces[x-2][y+1]=77;
    }
    if(y>1)
    {
        if(board[x-1][y-2]==0) //left up
        {
            pieces[x-1][y-2]=66;
        }
      
          if(board[x-1][y-2]==51)
                        pieces[x-1][y-2]=77;
    }
    if(y>1) //left down
    {
        if(board[x+1][y-2]==0)
        {
            pieces[x+1][y-2]=66;
        }
      
          if(board[x+1][y-2]==51)
                        pieces[x+1][y-2]=77;
    }
    if(y<6)
    {
        if(board[x-1][y+2]==0) //right up
        {
            pieces[x-1][y+2]=66;
        }
      
          if(board[x-1][y+2]==51)
                        pieces[x-1][y+2]=77;
    }
    if(y<6) //right down
    {
        if(board[x+1][y+2]==0)
        {
            pieces[x+1][y+2]=66;
        }
          
          if(board[x+1][y+2]==51)
                        pieces[x+1][y+2]=77;
       
    }
    }
    if (board[x][y]/10==5)            //bking
            {        if(board[x-1][y] ==0)
        {
            pieces[x-1][y] = 66;
        }
          if(board[x-1][y]%10==1)
        {
            pieces[x-1][y] = 66;
        }
         
       
        if(y>0){
        if (board[x-1][y-1]==0)
        {
          pieces[x-1][y-1] = 66;
           }
          else if(board[x-1][y-1]%10==1)
        {
            pieces[x-1][y-1] = 66;
        }
           
        }
        if(y<7){
        if((board[x-1][y+1]==0))
        {
           
            pieces[x-1][y+1]=66;
        }
        else if(board[x-1][y+1]%10==1)
        {
            pieces[x-1][y+1] = 66;
        }
        }
        //black way
          if(board[x+1][y] ==0)
        {
            pieces[x+1][y] = 66;
        }
        else   if(board[x+1][y]%10==1)
        {
            pieces[x+1][y] = 66;
        }
        if(y>0){
        if (board[x+1][y-1]==0)
        {
          pieces[x+1][y-1] = 66;
           }
           else   if(board[x+1][y-1]%10==1)
        {
            pieces[x+1][y-1] = 66;
        }
        }
        if(y<7){
        if((board[x+1][y+1]==0))
        {
           
            pieces[x+1][y+1]=66;
        }
        else  if(board[x+1][y+1]%10==1)
        {
            pieces[x+1][y+1] = 66;
        }
        }
        if(y>0){
          if(board[x][y-1] ==0)
        {
         pieces[x][y-1] = 66;
        }
        else if(board[x][y-1]%10==1)
        {
            pieces[x][y-1] = 66;
        }
        }
        if(y<7){
          if(board[x][y+1] ==0)
        {
            pieces[x][y+1] = 66;
        }
          if(board[x][y+1]%10==1)
        {
            pieces[x][y+1] = 66;
        }
        }
            }
            }
    }
    }
   
displayp();
for(z=0;z<8;z++)
{
    for(m=0;m<8;m++)
    {
        fake_pieces[z][m]=pieces[z][m];
    }
}
initializep();
};


void wcall(){
    int x,y, i , z,m,j;

    for(x=0; x<8;x++)
    {
        for(y=0;y<8;y++)
        {
            if(board[x][y]%10==1)
            {
                if(board[x][y]/10==1)   // wpawn
                {
                    
            if(y>0){
        if ((board[x-1][y-1]%10==2) || (board[x-1][y-1]==0))
        {
          pieces[x-1][y-1] = 66;
           }
        }else if(board[x-1][y-1]==52)
           pieces[x-1][y-1]=77;
        if(y<7){
        if((board[x-1][y+1]%10==2) || (board[x-1][y+1]==0))
        {
           
            pieces[x-1][y+1]=66;
        }else if(board[x-1][y+1]==52)
           pieces[x-1][y+1]=77;
        }
                }
                

        if(board[x][y]/10==2)             //wrook
        {
           for(i=x+1,j=y;i<8;i++)//backward
       {  if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
           
           if(board[i][j]==0)
           {
                pieces[i][j]=66;
           }
           else if((board[i][j]%10)==2||board[i][j]%10==1)
           {
            
               break;
           }
           
             
       }
       for(i=x-1,j=y;i>=0 ;i--)//forward
       {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
         
           if( board[i][j]==0)
                pieces[i][j]=66;
            else if((board[i][j]%10)==2||board[i][j]%10==1)
           {
             
               break;
           }
          
           
       }
       
       for(i=x,j=y+1;j<8;j++)//right
       {  if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
           if(board[i][j]==0)
                pieces[i][j]=66;
            else if((board[i][j]%10)==2||board[i][j]%10==1)
           {
             
               break;
           }
          
       }
       for(i=x,j=y-1; j>=0;j--)//left
       {  if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
           if(board[i][j]==0)
                pieces[i][j]=66;
            else if((board[i][j]%10)==2||board[i][j]%10==1)
           {
            
               break;
           }
           
           
           
       } 
        }
        if(board[x][y]/10==4)                  //wknight
        {
            if(y>0) // down left
    {
        if(board[x+2][y-1]==0)
        {
            pieces[x+2][y-1]=66;
        }
        
         if(board[x+2][y-1]==52)
                        pieces[x+2][y-1]=77;
    }
    if(y<7)// down right
    {
        if(board[x+2][y+1]==0)
        {
            pieces[x+2][y+1]=66;
        }
          if(board[x+2][y+1]==52)
                        pieces[x+2][y+1]=77;
    }
    if(y>0) //up left
    {
        if(board[x-2][y-1]==0)
        {
            pieces[x-2][y-1]=66;
        }
         if(board[x-2][y-1]==52)
                        pieces[x-2][y-1]=77;
    }
    if(y<7) //up right
    {
        if(board[x-2][y+1]==0)
        {
            pieces[x-2][y+1]=66;
        }
      if(board[x-2][y+1]==52)
                        pieces[x-2][y+1]=77;
    }
    if(y>1)
    {
        if(board[x-1][y-2]==0) //left up
        {
            pieces[x-1][y-2]=66;
        }
         if(board[x-1][y-2]==52)
                        pieces[x-1][y-2]=77;
    }
    if(y>1) //left down
    {
        if(board[x+1][y-2]==0)
        {
            pieces[x+1][y-2]=66;
        }
          if(board[x+1][y-2]==52)
                        pieces[x+1][y-2]=77;
    }
    if(y<6)
    {
        if(board[x-1][y+2]==0) //right up
        {
            pieces[x-1][y+2]=66;
        }
         if(board[x-1][y+2]==52)
                        pieces[x-1][y+2]=77;
    }
    if(y<6) //right down
    {
        if(board[x+1][y+2]==0)
        {
            pieces[x+1][y+2]=66;
        }
          if(board[x+1][y+2]==52)
                        pieces[x+1][y+2]=77;
       
    }
        }
        
        if(board[x][y]/10==5)            //wking
        {
       
       
         if(board[x-1][y] ==0)
        {
            pieces[x-1][y] = 66;
        }
       
        
        
           
        if(y>0){
        if (board[x-1][y-1]==0)
        {
          pieces[x-1][y-1] = 66;
           }
       
           
        }
        
        

        if(y<7){
        if((board[x-1][y+1]==0))
        {
           
            pieces[x-1][y+1]=66;
        }
       
        }
        
        
        //back way
          if(board[x+1][y] ==0)
        {
            pieces[x+1][y] = 66;
        }
       
        
       
        if(y>0){
        if (board[x+1][y-1]==0)
        {
          pieces[x+1][y-1] = 66;
           }
      
        }
        
       
        if(y<7){
        if((board[x+1][y+1]==0))
        {
           
            pieces[x+1][y+1]=66;
        }
      
        }
        
       
        if(y>0){
          if(board[x][y-1] ==0)
        {
            pieces[x][y-1] = 66;
        }
       
        }
        
        
        if(y<7){
          if(board[x][y+1] ==0)
        {
            pieces[x][y+1] = 66;
        }
       
        }
            
        }
        
        
        if(board[x][y]/10==3)     //wbishop
        {
            for(i=x+1,j=y+1;i<=7&&j<=7;i++,j++) // right down
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
            
            break;
        }
       
    }
   
    for(i=x+1,j=y-1;i<=7&&j>=0;i++,j--)// left down
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
           
            break;
        }
      
    }
   
    for(i=x-1,j=y-1;i>=0&&j>=0;i--,j--) //  left up
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
     
            break;
        }
      
    }
    for(i=x-1,j=y+1;i>=0&&j<=7;i--,j++) // right up
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
      
            break;
        }
       
    }
        }
        
        if(board[x][y]/10==6)                       //wqueen
        {
            
            for(i=x+1,j=y;i<8;i++) //downward
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
          
            break;
        }
       
    }
    for(i=x-1,j=y;i>=0;i--) //upward
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
            
            break;
        }
        
    }
    for(i=x, j=y-1;j>=0;j--) //left
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
       
            break;
        }
        
    }
    for(i=x, j=y+1;j<8;j++) //right
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
            
            break;
        }
       
    }
    for(i=x+1,j=y+1;i<8 && j<8;i++,j++) //down right
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
         
            break;
        }
       
    }
    for(i=x+1,j=y-1; i<8 && j>=0;i++,j--)//down left
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
         
            break;
        }
       
    }
    for(i=x-1, j=y+1; i>=0 && j<8;i--,j++)// up right
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
         
            break;
        }
       
    }
    for(i=x-1, j=y-1; i>=0 && j>=0;i--,j--) // up left
    {if(board[i][j]==52)
            {
                        pieces[i][j]=77;
                        continue;
            }
        if(board[i][j]==0)
        {
            pieces[i][j]=66;
        }
        else if(board[i][j]%10==2||board[i][j]%10==1)
        {
           
            break;
        }
        
    }
            
            
        }
        
                
                
                
                }
            }
        }

//displayp();

for(z=0;z<8;z++)
{
    for(m=0;m<8;m++)
    {
        fake_pieces[z][m]=pieces[z][m];
    }
}

initializep();


 }
    
    
    
void wcheckmate()
{  
   
    int x,y, i , j, check=1;
    wcall();
         wcheck();
   for(i=0;i<8;i++)
   {
       for(j=0;j<8;j++)
       {
           if(board[i][j]%10==2&&board[i][j]/10==5)
           {
              x=i;
              y=j;
              break;
           }
       }
   }

if(fake_pieces[x-1][y]!=66)
 {        if(board[x-1][y] ==0)
        {
            pieces[x-1][y] = 44;
        }
          if(board[x-1][y]%10==1)
        {
            pieces[x-1][y] = 99;
        }
 }     
 
  if(fake_pieces[x-1][y-1]!=66)
  {
        if(y>0){
        if (board[x-1][y-1]==0)
        {
          pieces[x-1][y-1] = 44;
           }
          else if(board[x-1][y-1]%10==1)
        {
            pieces[x-1][y-1] = 99;
        }
           
        }
  }
  
     if(fake_pieces[x-1][y+1]!=66)
     {
  
        if(y<7){
        if((board[x-1][y+1]==0))
        {
           
            pieces[x-1][y+1]=44;
        }
        else if(board[x-1][y+1]%10==1)
        {
            pieces[x-1][y+1] = 99;
        }
        }
     }
        //back way
         if(fake_pieces[x+1][y]!=66)
         {
          if(board[x+1][y] ==0)
        {       
   
            pieces[x+1][y] = 44;
        }
        else   if(board[x+1][y]%10==1)
        {
            pieces[x+1][y] = 99;      
        }
   }
        
         
          if(fake_pieces[x+1][y-1]!=66)
          {
        if(y>0){
        if (board[x+1][y-1]==0)
        {
          pieces[x+1][y-1] = 44;
           }
           else   if(board[x+1][y-1]%10==1)
        {
            pieces[x+1][y-1] = 99;
        }
        }
          }
           if(fake_pieces[x+1][y+1]!=66)
           {
        if(y<7){
        if((board[x+1][y+1]==0))
        {
           
            pieces[x+1][y+1]=44;
        }
        else  if(board[x+1][y+1]%10==1)
        {
            pieces[x+1][y+1] = 99;
        }
        }
           }
            if(fake_pieces[x][y-1]!=66)
            {
        if(y>0){
          if(board[x][y-1] ==0)
        {
         pieces[x][y-1] = 44;
        }
        else if(board[x][y-1]%10==1)
        {
            pieces[x][y-1] = 99;
        }
        }
            }
             if(fake_pieces[x][y+1]!=66)
             {
        if(y<7){
          if(board[x][y+1] ==0)
        {
            pieces[x][y+1] = 44;
        }
          if(board[x][y+1]%10==1)
        {
            pieces[x][y+1] = 99;
        }
        }
             }
             
     
             
        for(i=0;i<8;i++)
        {
            for(j=0;j<8;j++)
            {
                if(pieces[i][j]==44 || pieces[i][j]==99 )
                {
                    check=0;
                    break;
                }
            }
        }
        
        if(check==1 && fake_pieces[x][y]==77)
        {
            printf("\nCHECK FROM WHITE ");
            printf("\n White Wins");
            exit(0);
        }
initializep();
initializefake();
}




void bcheckmate()
{
    
    int x,y, i , j, check=1;
    bcall();
    bcheck();
    for(i=0;i<8;i++)
   {
       for(j=0;j<8;j++)
       {
           if(board[i][j]%10==1&&board[i][j]/10==5)
           {
              x=i;
              y=j;
              break;
           }
       }
   }
   
   if(fake_pieces[x-1][y]!=66)
 {        if(board[x-1][y] ==0)
        {
            pieces[x-1][y] = 44;
        }
          if(board[x-1][y]%10==2)
        {
            pieces[x-1][y] = 99;
        }
 }     
 
  if(fake_pieces[x-1][y-1]!=66)
  {
        if(y>0){
        if (board[x-1][y-1]==0)
        {
          pieces[x-1][y-1] = 44;
           }
          else if(board[x-1][y-1]%10==2)
        {
            pieces[x-1][y-1] = 99;
        }
           
        }
  }
  
     if(fake_pieces[x-1][y+1]!=66)
     {
  
        if(y<7){
        if((board[x-1][y+1]==0))
        {
           
            pieces[x-1][y+1]=44;
        }
        else if(board[x-1][y+1]%10==2)
        {
            pieces[x-1][y+1] = 99;
        }
        }
     }
        //back way
         if(fake_pieces[x+1][y]!=66)
         {
          if(board[x+1][y] ==0)
        {       
   
            pieces[x+1][y] = 44;
        }
        else   if(board[x+1][y]%10==2)
        {
            pieces[x+1][y] = 99;      
        }
   }
        
         
          if(fake_pieces[x+1][y-1]!=66)
          {
        if(y>0){
        if (board[x+1][y-1]==0)
        {
          pieces[x+1][y-1] = 44;
           }
           else   if(board[x+1][y-1]%10==2)
        {
            pieces[x+1][y-1] = 99;
        }
        }
          }
           if(fake_pieces[x+1][y+1]!=66)
           {
        if(y<7){
        if((board[x+1][y+1]==0))
        {
           
            pieces[x+1][y+1]=44;
        }
        else  if(board[x+1][y+1]%10==2)
        {
            pieces[x+1][y+1] = 99;
        }
        }
           }
            if(fake_pieces[x][y-1]!=66)
            {
        if(y>0){
          if(board[x][y-1] ==0)
        {
         pieces[x][y-1] = 44;
        }
        else if(board[x][y-1]%10==2)
        {
            pieces[x][y-1] = 99;
        }
        }
            }
             if(fake_pieces[x][y+1]!=66)
             {
        if(y<7){
          if(board[x][y+1] ==0)
        {
            pieces[x][y+1] = 44;
        }
          if(board[x][y+1]%10==2)
        {
            pieces[x][y+1] = 99;
        }
        }
    }
        for(i=0;i<8;i++)
        {
            for(j=0;j<8;j++)
            {
                if(pieces[i][j]==44 || pieces[i][j]==99 )
                {
                    check=0;
                    break;
                }
            }
        }
        
        if(check==1 && fake_pieces[x][y]==77)
        {
            printf("\nCHECK FROM BLACK ");
            printf("\n BLACK Wins");
            exit(0);
        }
initializep();
initializefake();
   
   
};







void wcheck()
{
     int i,j, temp;
  
   
    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77)
               printf("CHECK FROM WHITE");
           
              } 
               
          }
          
}


















int bcheck(){
    
    int i,j, temp;
  
   
    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
               printf("CHECK FROM BLACK");
               return 1;
            
            }else{
                return 0;
                
             
                
              } 
               
          }
          
      }
};


void black();
void white();  

void wqueen(int x , int y);
void wbishop(int x, int y);
void wknight(int x, int y);
void wpawn(int x,int y);
void wrook(int x,int y);
void wking(int x , int y);


void bpawn(int x, int y);
void brook(int x, int y);
void bqueen(int x, int y);
void bbishop( int x, int y);
void bknight(int x, int y);
void bking(int x, int y);
int bcheck();


void displayb()
    {
    int i,j;
    printf("\n     1   2   3   4   5   6   7   8\n");
    printf("\n");
    for(i=0;i<8;i++)
    {  
        printf("%d  ",i+1);
        for(j=0;j<8;j++)
        {
            if(board[i][j]==0)
                printf("  --");
           
            else if(board[i][j]==99)
            {
                printf("  K");
            }
           
            else
                printf("  %d",board[i][j]);
           
        }
        printf("\n");
       
    }
       
    };                  

void loop()
{   
    
    
    //wcheckmate();
    white(); 
    
    
   
};



void main(){
    int ch;
    long double i;
    
    printf("\n\t\t\t\t\t\t\t\tChess Game\n\t\t\t\t\t\t\tDeveloped By: Dickson & Vaibhav\n");
    //sleep(2);

    printf("\n1. Start \n2. Rules\n3. Exit\n");
    scanf("%d", &ch);
    switch(ch)
    {
        case 1:
        loop();
        break;
       
        case 2:
        printf("\n * Enter the correct position of the piece, after entering the position a board will appear, \n  44 means that is the possible move for that piece and K means that piece can kill an enemy's piece at that position\n");
        break;
       
        case 3:
           exit(0);
       
        default:
            printf("Invalid Option selected");
            system("clear");
            main();
            break;
           
    }
   
   
}
void white(){
    
    int x, y;
    displayb();
    white_here:
    printf("\n White's Turn");
    printf("\nEnter the row position and column position of the piece:\n");
    scanf("%d:%d",&x,&y);
    x=x-1;
    y=y-1;
    if(board[x][y]%10!=1)
    {
   printf("The entered position is not White's");
   goto white_here;
    }
    if(board[x][y]/10==1)
    {
        wpawn(x,y);
    }
     else if (board[x][y]/10==2)
    {  
     
        wrook(x,y);
       
    }
    else if (board[x][y]/10==4)
    {
      wknight(x,y);
    }
    else if (board[x][y]/10 ==3)
    {
        wbishop(x,y);
    }
   
    else if(board[x][y]/10==5)
    {
        wking(x,y);
    }
    else if (board[x][y]/10==6)
    {
       wqueen(x,y);
    }
    else
    {
        printf("\n Choose a valid coordinate ");
        white();
    }
}
void black(){
    
        displayb();
        int x, y;
    black_here:
    printf("\n Black's Turn");
    printf("\nEnter the row position and column position of the piece:\n");
    scanf("%d:%d",&x,&y);
    x=x-1;
    y=y-1;
    if(board[x][y]%10!=2)
    {
   printf("The entered position is not Black's ");
   goto black_here;
    }
    if(board[x][y]/10==1)
    {
       bpawn(x,y);
    }
     else if (board[x][y]/10==2)
    {  
     
      brook(x,y);
       
    }
    else if (board[x][y]/10==4)
    {
     bknight(x,y);
    }
    else if (board[x][y]/10 ==3)
    {
         bbishop(x,y);
    }
   
    else if(board[x][y]/10==5)
    {
      bking(x,y);
    }
    else if (board[x][y]/10==6)
    {
       bqueen(x,y);
    }
    else
    {
        printf("\n Choose a valid coordinate ");
        black();
    }
}


void wpawn(int x , int y){
      int a ,b,i,j, check;
      
        for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
            fake_board[i][j]=board[i][j];
               
             }
             } 
       
        if(x==6&&board[4][y]==0)
        {
            pieces[4][y]=44;
        }
         if(board[x-1][y] ==0)
        {
            pieces[x-1][y] = 44;
        }
        if(y>0){
        if ((board[x-1][y-1]%10==2)&&(board[x-1][y-1]!=0))
        {
          pieces[x-1][y-1] = 99;
           }
        }
        if(y<7){
        if((board[x-1][y+1]%10==2)&&(board[x-1][y+1]!=0))
        {
           
            pieces[x-1][y+1]=99;
        }
        }
        if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            white();
        }
        displayp();
        here:
        printf("\nEnter the move coordinate");
        scanf("%d:%d", &a, &b);
        a -=1;
        b -=1;
        if(pieces[a][b]==44||pieces[a][b]==99){
        board[a][b]=board[x][y];
        board[x][y]=0;
        }
        else  
        {   printf("INVALID MOVE");
            goto here;
        }
        if(a==0)
        {
            wrevive(a,b);
        }
        initializep();
        bcall();

    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
              
            for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
              board[i][j]=fake_board[i][j];
               
             }
             }
             printf("INVALID MOVE CAUSE OF CHECK FROM BLACK");
             white();

        
        }
          }
      }
        
        wcheckmate();          
        black();
}

void wrook(int x,int y){
   
          int i,j,movea,moveb;
         for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
            fake_board[i][j]=board[i][j];
               
             }
             } 
       for(i=x+1,j=y;i<8;i++)//backward
       {  
           
           if(board[i][j]==0)
           {
                pieces[i][j]=44;
           }
           else if((board[i][j]%10)==2)
           {
               pieces[i][j]=99;
               break;
           }
           else
           {
               break;
           }
           
             
       }
       for(i=x-1,j=y;i>=0 ;i--)//forward
       {
         
           if( board[i][j]==0)
                pieces[i][j]=44;
            else if((board[i][j]%10)==2)
           {
               pieces[i][j]=99;
               break;
           }
           else
           {
               break;
           }
           
       }
       
       for(i=x,j=y+1;j<8;j++)//right
       {  
           if(board[i][j]==0)
                pieces[i][j]=44;
            else if((board[i][j]%10)==2)
           {
               pieces[i][j]=99;
               break;
           }
           else
           {
               break;
           }
           
       }
       for(i=x,j=y-1; j>=0;j--)//left
       {  
           if(board[i][j]==0)
                pieces[i][j]=44;
            else if((board[i][j]%10)==2)
           {
               pieces[i][j]=99;
               break;
           }
           else
           {
               break;
           }
           
           
       }
       if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            white();
        }
       
       displayp();
       here_rook:
       printf("Enter the move coordinate");
       scanf("%d:%d",&movea,&moveb);
       movea -=1;
       moveb-=1;
       if(pieces[movea][moveb]==44 || pieces[movea][moveb]==99)
       {
           board[movea][moveb]=board[x][y];
           board[x][y]=0;
       }
       else
       {
           printf("Invalid Move!");
           goto here_rook;
       }
       initializep();
          bcall();

    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
              
            for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
              board[i][j]=fake_board[i][j];
               
             }
             }
             printf("INVALID MOVE CAUSE OF CHECK FROM BLACK");
             white();

        
        }
          }
      }
        wcheckmate();
        black();
       
       
    }

  void initializep() //to initialize the pieces grid back to zero after displaying possible moves
  {
      int i,j;
      for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
            pieces[i][j]=0;
          }
      }
  }
void wknight(int x , int y)
{
    int movea, i,j,moveb;
    for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
            fake_board[i][j]=board[i][j];
               
             }
             } 
    if(y>0) // down left
    {
        if(board[x+2][y-1]==0)
        {
            pieces[x+2][y-1]=44;
        }
        else if(board[x+2][y-1]%10==2)
        {
            pieces[x+2][y-1]=99;
        }
    }
    if(y<7)// down right
    {
        if(board[x+2][y+1]==0)
        {
            pieces[x+2][y+1]=44;
        }
        else if(board[x+2][y+1]%10==2)
        {
            pieces[x+2][y+1]=99;
        }
    }
    if(y>0) //up left
    {
        if(board[x-2][y-1]==0)
        {
            pieces[x-2][y-1]=44;
        }
        else if(board[x-2][y-1]%10==2)
        {
            pieces[x-2][y-1]=99;
        }
    }
    if(y<7) //up right
    {
        if(board[x-2][y+1]==0)
        {
            pieces[x-2][y+1]=44;
        }
        else if(board[x-2][y+1]%10==2)
        {
            pieces[x-2][y+1]=99;
        }
    }
    if(y>1)
    {
        if(board[x-1][y-2]==0) //left up
        {
            pieces[x-1][y-2]=44;
        }
        else if(board[x-1][y-2]%10==2)
        {
            pieces[x-1][y-2]=99;
        }
    }
    if(y>1) //left down
    {
        if(board[x+1][y-2]==0)
        {
            pieces[x+1][y-2]=44;
        }
        else if(board[x+1][y-2]%10==2)
        {
            pieces[x+1][y-2]=99;
        }
    }
    if(y<6)
    {
        if(board[x-1][y+2]==0) //right up
        {
            pieces[x-1][y+2]=44;
        }
        else if(board[x-1][y+2]%10==2)
        {
            pieces[x-1][y+2]=99;
        }
    }
    if(y<6) //right down
    {
        if(board[x+1][y+2]==0)
        {
            pieces[x+1][y+2]=44;
        }
        else if(board[x+1][y+2]%10==2)
        {
            pieces[x+1][y+2]=99;
        }    
       
    }
    if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            white();
        }
       
    displayp();
    here_knight :
    printf("Enter the move coordinate");
    scanf("%d:%d", &movea, &moveb);
    movea -=1;
    moveb -=1;
    if(pieces[movea][moveb]==44 || pieces[movea][moveb]==99)
       {
           board[movea][moveb]=board[x][y];
           board[x][y]=0;
       }
       else
       {
           printf("Invalid Move!");
           goto here_knight;
       }
    initializep();
        bcall();

    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
              
            for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
              board[i][j]=fake_board[i][j];
               
             }
             }
             printf("INVALID MOVE CAUSE OF CHECK FROM BLACK");
             white();

        
        }
          }
      }
      
    wcheckmate();
   black();
}


void wbishop( int x, int y)
{
    int i,j,movea, moveb;
    for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
            fake_board[i][j]=board[i][j];
               
             }
             } 
    for(i=x+1,j=y+1;i<=7&&j<=7;i++,j++) // right down
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
   
    for(i=x+1,j=y-1;i<=7&&j>=0;i++,j--)// left down
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j] =99;
            break;
        }
        else
        {
            break;
        }
    }
   
    for(i=x-1,j=y-1;i>=0&&j>=0;i--,j--) //  left up
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j] =99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x-1,j=y+1;i>=0&&j<=7;i--,j++) // right up
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j] =99;
            break;
        }
        else
        {
            break;
        }
    }
    if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            white();
        }
   
    displayp();
   
   here_bishop :
    printf("Enter the move coordinate");
    scanf("%d:%d", &movea, &moveb);
    movea -=1;
    moveb -=1;
    if(pieces[movea][moveb]==44 || pieces[movea][moveb]==99)
       {
           board[movea][moveb]=board[x][y];
           board[x][y]=0;
       }
       else
       {
           printf("Invalid Move!");
           goto here_bishop;
       }
    initializep();
        bcall();

    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
              
            for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
              board[i][j]=fake_board[i][j];
               
             }
             }
             printf("INVALID MOVE CAUSE OF CHECK FROM BLACK");
             white();

        
        }
          }
      }
      wcheckmate();
    black();
   
}
void wking(int x , int y){
    int a,b;
                                                    // King valid moves logic starts
        bcall();
        if(fake_pieces[x-1][y]!=66)
        {
       
         if(board[x-1][y] ==0)
        {
            pieces[x-1][y] = 44;
        }
          if(board[x-1][y]%10==2)
        {
            pieces[x-1][y] = 99;
        }
        }
        if(fake_pieces[x-1][y-1]!=66)
        {
           
        if(y>0){
        if (board[x-1][y-1]==0)
        {
          pieces[x-1][y-1] = 44;
           }
          else if(board[x-1][y-1]%10==2)
        {
            pieces[x-1][y-1] = 99;
        }
           
        }
        }
        if(fake_pieces[x-1][y+1]!=66)
        {

        if(y<7){
        if((board[x-1][y+1]==0))
        {
           
            pieces[x-1][y+1]=44;
        }
        else if(board[x-1][y+1]%10==2)
        {
            pieces[x-1][y+1] = 99;
        }
        }
        }
        if(fake_pieces[x+1][y]!=66)
        {
        //back way
          if(board[x+1][y] ==0)
        {
            pieces[x+1][y] = 44;
        }
        else   if(board[x+1][y]%10==2)
        {
            pieces[x+1][y] = 99;
        }
        }
        if(fake_pieces[x+1][y-1]!=66)
        {
        if(y>0){
        if (board[x+1][y-1]==0)
        {
          pieces[x+1][y-1] = 44;
           }
           else   if(board[x+1][y-1]%10==2)
        {
            pieces[x+1][y-1] = 99;
        }
        }
        }
        if(fake_pieces[x+1][y+1]!=66)
        {
        if(y<7){
        if((board[x+1][y+1]==0))
        {
           
            pieces[x+1][y+1]=44;
        }
        else  if(board[x+1][y+1]%10==2)
        {
            pieces[x+1][y+1] = 99;
        }
        }
        }
        if(fake_pieces[x][y-1]!=66)
        {
        if(y>0){
          if(board[x][y-1] ==0)
        {
            pieces[x][y-1] = 44;
        }
        else if(board[x][y-1]%10==2)
        {
            pieces[x][y-1] = 99;
        }
        }
        }
        if(fake_pieces[x][y+1]!=66)
        {
        if(y<7){
          if(board[x][y+1] ==0)
        {
            pieces[x][y+1] = 44;
        }
          if(board[x][y+1]%10==2)
        {
            pieces[x][y+1] = 99;
        }
        }
        }                                                   // king valid moves logic ends
        if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            white();
        }
       
        displayp();
        here:
        printf("\nEnter the move coordinate");
        scanf("%d:%d", &a, &b);
        a -=1;
        b -=1;
        if(pieces[a][b]==44||pieces[a][b]==99){
        board[a][b]=board[x][y];
        board[x][y]=0;
        }
        else
        {   printf("INVALID MOVE");
            goto here;
        }
        initializep();
        
        wcheckmate();
       black();


}
void wqueen(int x, int y)
{
    int i, j, movea, moveb;
    for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
            fake_board[i][j]=board[i][j];
               
             }
             } 
    for(i=x+1,j=y;i<8;i++) //downward
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x-1,j=y;i>=0;i--) //upward
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x, j=y-1;j>=0;j--) //left
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x, j=y+1;j<8;j++) //right
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x+1,j=y+1;i<8 && j<8;i++,j++) //down right
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x+1,j=y-1; i<8 && j>=0;i++,j--)//down left
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x-1, j=y+1; i>=0 && j<8;i--,j++)// up right
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x-1, j=y-1; i>=0 && j>=0;i--,j--) // up left
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==2)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            white();
        }
   
    displayp();
   
    here_queen :
    printf("Enter the move coordinate");
    scanf("%d:%d", &movea, &moveb);
    movea -=1;
    moveb -=1;
    if(pieces[movea][moveb]==44 || pieces[movea][moveb]==99)
       {
           board[movea][moveb]=board[x][y];
           board[x][y]=0;
       }
       else
       {
           printf("Invalid Move!");
           goto here_queen;
       }
    initializep();
         bcall();

    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
              
            for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
              board[i][j]=fake_board[i][j];
               
             }
             }
             printf("INVALID MOVE CAUSE OF CHECK FROM BLACK");
             white();

        
        }
          }
      }
  wcheckmate();  
  black();
  
   
}



void bpawn(int x,  int y){
          int a ,b, i, j;
       
       for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
            fake_board[i][j]=board[i][j];
               
             }
             } 
        if(x==1&&board[3][y]==0)
        {
            pieces[3][y]=44;
        }
         if(board[x+1][y] ==0)
        {
            pieces[x+1][y] = 44;
        }
        if(y>0){
        if ((board[x+1][y-1]%10!=2)&&(board[x+1][y-1]!=0))
        {
          pieces[x+1][y-1] = 99;
           }
        }
        if(y<7){
        if((board[x+1][y+1]%10!=2)&&(board[x+1][y+1]!=0))
        {
           
            pieces[x+1][y+1]=99;
        }
        }
        if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            black();
        }
       
        displayp();
        here:
        printf("\nEnter the move coordinate");
        scanf("%d:%d", &a, &b);
        a -=1;
        b -=1;
        if(pieces[a][b]==44||pieces[a][b]==99){
        board[a][b]=board[x][y];
        board[x][y]=0;
        }
        else
        {   printf("INVALID MOVE");
            goto here;
        }
        if(a==7)
        {
            brevive(a, b);
        }
        initializep();
            wcall();

    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
              
            for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
              board[i][j]=fake_board[i][j];
               
             }
             }
             printf("INVALID MOVE CAUSE OF CHECK FROM WHITE");
             black();

        
        }
          }
      }
      bcheckmate();
        loop();
}

void brook(int x, int y){
        int i,j,movea,moveb;
        for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
            fake_board[i][j]=board[i][j];
               
             }
             } 
         
       for(i=x-1,j=y;i<8;i--)//backward
       {  
           
           if(board[i][j]==0)
           {
                pieces[i][j]=44;
           }
           else if((board[i][j]%10)==1)
           {
               pieces[i][j]=99;
               break;
           }
           else
           {
               break;
           }
           
             
       }
       for(i=x+1,j=y;i>=0 ;i++)//forward
       {
         
           if( board[i][j]==0)
                pieces[i][j]=44;
            else if((board[i][j]%10)==1)
           {
               pieces[i][j]=99;
               break;
           }
           else
           {
               break;
           }
           
       }
       
       for(i=x,j=y+1;j<8;j++)//right
       {  
           if(board[i][j]==0)
                pieces[i][j]=44;
            else if((board[i][j]%10)==1)
           {
               pieces[i][j]=99;
               break;
           }
           else
           {
               break;
           }
           
       }
       for(i=x,j=y-1; j>=0;j--)//left
       {  
           if(board[i][j]==0)
                pieces[i][j]=44;
            else if((board[i][j]%10)==1)
           {
               pieces[i][j]=99;
               break;
           }
           else
           {
               break;
           }
       }
       if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            black();
        }
       
       
           displayp();
       here_rook:
       printf("Enter the move coordinate");
       scanf("%d:%d",&movea,&moveb);
       movea -=1;
       moveb-=1;
       if(pieces[movea][moveb]==44 || pieces[movea][moveb]==99)
       {
           board[movea][moveb]=board[x][y];
           board[x][y]=0;
       }
       else
       {
           printf("Invalid Move!");
           goto here_rook;
       }
       initializep();
         wcall();
    
    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
              
            for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
              board[i][j]=fake_board[i][j];
               
             }
             }
             printf("INVALID MOVE CAUSE OF CHECK FROM WHITE");
             black();
        
        
        }
          }
      }
      
      bcheckmate();
      loop();
}

void bqueen(int x, int y)
{
int i, j, movea, moveb;
for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
            fake_board[i][j]=board[i][j];
               
             }
             } 
    for(i=x+1,j=y;i<8;i++) //downward
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x-1,j=y;i>=0;i--) //upward
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x, j=y-1;j>=0;j--) //left
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x, j=y+1;j<8;j++) //right
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x+1,j=y+1;i<8 && j<8;i++,j++) //down right
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x+1,j=y-1; i<8 && j>=0;i++,j--)//down left
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x-1, j=y+1; i>=0 && j<8;i--,j++)// up right
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x-1, j=y-1; i>=0 && j>=0;i--,j--) // up left
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
    if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            black();
        }
       
   
    displayp();

    here_queen :
    printf("Enter the move coordinate");
    scanf("%d:%d", &movea, &moveb);
    movea -=1;
    moveb -=1;
    if(pieces[movea][moveb]==44 || pieces[movea][moveb]==99)
       {
           board[movea][moveb]=board[x][y];
           board[x][y]=0;
       }
       else
       {
           printf("Invalid Move!");
           goto here_queen;
       }
    initializep();
      wcall();

    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
              
            for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
              board[i][j]=fake_board[i][j];
               
             }
             }
             printf("INVALID MOVE CAUSE OF CHECK FROM WHITE");
             black();

        
        }
          }
      }
      bcheckmate();
    loop();


}

void bbishop(int x, int y)
{
int i,j,movea, moveb;
for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
            fake_board[i][j]=board[i][j];
               
             }
             } 
    for(i=x+1,j=y+1;i<=7&&j<=7;i++,j++) // right down
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j]=99;
            break;
        }
        else
        {
            break;
        }
    }
   
    for(i=x+1,j=y-1;i<=7&&j>=0;i++,j--)// left down
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j] =99;
            break;
        }
        else
        {
            break;
        }
    }
   
    for(i=x-1,j=y-1;i>=0&&j>=0;i--,j--) //  left up
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j] =99;
            break;
        }
        else
        {
            break;
        }
    }
    for(i=x-1,j=y+1;i>=0&&j<=7;i--,j++) // right up
    {
        if(board[i][j]==0)
        {
            pieces[i][j]=44;
        }
        else if(board[i][j]%10==1)
        {
            pieces[i][j] =99;
            break;
        }
        else
        {
            break;
        }
    }
    if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            black();
        }
       
   
   
    displayp();
   
   here_bbishop :
    printf("Enter the move coordinate");
    scanf("%d:%d", &movea, &moveb);
    movea -=1;
    moveb -=1;
    if(pieces[movea][moveb]==44 || pieces[movea][moveb]==99)
       {
           board[movea][moveb]=board[x][y];
           board[x][y]=0;
       }
       else
       {
           printf("Invalid Move!");
           goto here_bbishop;
       }
    initializep();
      wcall();

    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
              
            for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
              board[i][j]=fake_board[i][j];
               
             }
             }
             printf("INVALID MOVE CAUSE OF CHECK FROM WHITE");
             black();

        
        }
          }
      }
    bcheckmate();
    loop();
}
void bknight(int x, int y){
     int movea, i,j,moveb;
     for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
            fake_board[i][j]=board[i][j];
               
             }
             } 
    if(y>0) // down left
    {
        if(board[x+2][y-1]==0)
        {
            pieces[x+2][y-1]=44;
        }
        else if(board[x+2][y-1]%10==1)
        {
            pieces[x+2][y-1]=99;
        }
    }
    if(y<7)// down right
    {
        if(board[x+2][y+1]==0)
        {
            pieces[x+2][y+1]=44;
        }
        else if(board[x+2][y+1]%10==1)
        {
            pieces[x+2][y+1]=99;
        }
    }
    if(y>0) //up left
    {
        if(board[x-2][y-1]==0)
        {
            pieces[x-2][y-1]=44;
        }
        else if(board[x-2][y-1]%10==1)
        {
            pieces[x-2][y-1]=99;
        }
    }
    if(y<7) //up right
    {
        if(board[x-2][y+1]==0)
        {
            pieces[x-2][y+1]=44;
        }
        else if(board[x-2][y+1]%10==1)
        {
            pieces[x-2][y+1]=99;
        }
    }
    if(y>1)
    {
        if(board[x-1][y-2]==0) //left up
        {
            pieces[x-1][y-2]=44;
        }
        else if(board[x-1][y-2]%10==1)
        {
            pieces[x-1][y-2]=99;
        }
    }
    if(y>1) //left down
    {
        if(board[x+1][y-2]==0)
        {
            pieces[x+1][y-2]=44;
        }
        else if(board[x+1][y-2]%10==1)
        {
            pieces[x+1][y-2]=99;
        }
    }
    if(y<6)
    {
        if(board[x-1][y+2]==0) //right up
        {
            pieces[x-1][y+2]=44;
        }
        else if(board[x-1][y+2]%10==1)
        {
            pieces[x-1][y+2]=99;
        }
    }
    if(y<6) //right down
    {
        if(board[x+1][y+2]==0)
        {
            pieces[x+1][y+2]=44;
        }
        else if(board[x+1][y+2]%10==1)
        {
            pieces[x+1][y+2]=99;
        }    
       
    }
    if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            black();
        }
       
   
   
    displayp();
    here_knight :
    printf("Enter the move coordinate");
    scanf("%d:%d", &movea, &moveb);
    movea -=1;
    moveb -=1;
    if(pieces[movea][moveb]==44 || pieces[movea][moveb]==99)
       {
           board[movea][moveb]=board[x][y];
           board[x][y]=0;
       }
       else
       {
           printf("Invalid Move!");
           goto here_knight;
       }
    initializep();
      wcall();

    for(i=0;i<8;i++)
      {
          for(j=0;j<8;j++)
          {
           if( fake_pieces[i][j]==77){
              
            for(i=0;i<8;i++)
             {
          for(j=0;j<8;j++)
             {
              board[i][j]=fake_board[i][j];
               
             }
             }
             printf("INVALID MOVE CAUSE OF CHECK FROM WHITE");
             black();

        
        }
          }
      }
      bcheckmate();
    loop();
}


void bking(int x, int y)
{
int a,b;
wcall();
if(fake_pieces[x-1][y]!=66)
 {        if(board[x-1][y] ==0)
        {
            pieces[x-1][y] = 44;
        }
          if(board[x-1][y]%10==1)
        {
            pieces[x-1][y] = 99;
        }
 }     
 
  if(fake_pieces[x-1][y-1]!=66)
  {
        if(y>0){
        if (board[x-1][y-1]==0)
        {
          pieces[x-1][y-1] = 44;
           }
          else if(board[x-1][y-1]%10==1)
        {
            pieces[x-1][y-1] = 99;
        }
           
        }
  }
  
     if(fake_pieces[x-1][y+1]!=66)
     {
  
        if(y<7){
        if((board[x-1][y+1]==0))
        {
           
            pieces[x-1][y+1]=44;
        }
        else if(board[x-1][y+1]%10==1)
        {
            pieces[x-1][y+1] = 99;
        }
        }
     }
        //black way
         if(fake_pieces[x+1][y]!=66)
         {
          if(board[x+1][y] ==0)
        {
            pieces[x+1][y] = 44;
        }
        else   if(board[x+1][y]%10==1)
        {
            pieces[x+1][y] = 99;
        }
         }
          if(fake_pieces[x+1][y-1]!=66)
          {
        if(y>0){
        if (board[x+1][y-1]==0)
        {
          pieces[x+1][y-1] = 44;
           }
           else   if(board[x+1][y-1]%10==1)
        {
            pieces[x+1][y-1] = 99;
        }
        }
          }
           if(fake_pieces[x+1][y+1]!=66)
           {
        if(y<7){
        if((board[x+1][y+1]==0))
        {
           
            pieces[x+1][y+1]=44;
        }
        else  if(board[x+1][y+1]%10==1)
        {
            pieces[x+1][y+1] = 99;
        }
        }
           }
            if(fake_pieces[x][y-1]!=66)
            {
        if(y>0){
          if(board[x][y-1] ==0)
        {
         pieces[x][y-1] = 44;
        }
        else if(board[x][y-1]%10==1)
        {
            pieces[x][y-1] = 99;
        }
        }
            }
             if(fake_pieces[x][y+1]!=66)
             {
        if(y<7){
          if(board[x][y+1] ==0)
        {
            pieces[x][y+1] = 44;
        }
          if(board[x][y+1]%10==1)
        {
            pieces[x][y+1] = 99;
        }
        }
             }
        if(no_pos()==0)
        {
            printf("\nNo possible moves for the selected piece");
            printf("\n Select a different piece");
            black();
           
        }
      
       
       
        displayp();
        here:
        printf("\nEnter the move coordinate");
        scanf("%d:%d", &a, &b);
        a -=1;
        b -=1;
        if(pieces[a][b]==44||pieces[a][b]==99){
        board[a][b]=board[x][y];
        board[x][y]=0;
        }
        else
        {   printf("INVALID MOVE");
            goto here;
        }
        initializep();
        bcheckmate();
        loop();
}


