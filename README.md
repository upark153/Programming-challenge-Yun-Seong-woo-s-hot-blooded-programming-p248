# Programming-challenge-Yun-Seong-woo-s-hot-blooded-programming-p248
![image](https://user-images.githubusercontent.com/115389450/233525100-a9800eda-d72d-4635-a21f-ff64934439ba.png)
```
#include <stdio.h>

int main(void)
{
     int a;
     printf("10진수 정수를 입력하세요 : ");
     scanf("%d", &a);
     printf("16진수 : ");
     scanf("%X", &a);  // 16진수 대문자 출력
  
     return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233525184-0e921c7e-c0b5-4fca-a2ab-424ed230ccf0.png)
```
#include <stdio.h>
void mutiple(int n);

int main(void)
{
    int n=0;
    printf("구구단을 하려면 1을 눌러주세요 : ");
    scanf("%d", &n);
    multiple(n);
    return 0;
}

void multiple(int n)
{
    int a,b;
    int i,j=0;
    printf("두 개의 정수 입력 : ");
    scanf("%d %d", &a, &b);
    if(a>b)
    {
        for(j=1;j<=9; j++)
        {
            for(i=b; i<=a; i++)
            {
                printf("%d x %d = %2d |", i, j, i*j);
            }
            printf("\n");
        }
    }
    else if(b>a)
    {
        for(j=1; j<=9; j++)
        {
            for(i=a; i<=b; i++)
            {
                printf("%d x %d = %2d |", i, j, i*j);
            }
            printf("\n");
        }
    }
}
```
![image](https://user-images.githubusercontent.com/115389450/233525289-b4a30865-41f5-4e30-a34e-d8aa31b89a25.png)
```
#include <stdio.h>

int main(void)
{
    int max=0; // 최댓값 구하기
    int min=0; // 최솟값 구하기
    int sum=0; // 총합 구하기
    int arr[5]; // 다섯개의 정수를 입력받을 자리

    printf("정수 5개를 입력하세요 : ");
    for(int i=0; i<5; i++)
    {
        scanf("%d", &arr[i]); // arr[0], arr[1], arr[2], arr[3], arr[4]
    }   
    
    max=arr[0]; // max 값을 arr[0]에 넣어준다.
    for(int i=1; i<5; i++)
    {
        if(max<arr[i]) // max가 arr[i]보다 작은 경우
            max=arr[i]; // max는 arr[i]이다.
    }
    printf("최댓값은 : %d\n", max);

    min=arr[0];
    for(int i=1; i<5; i++)
    {
        if(min>arr[i])
            min=arr[i];
    }
    printf("최솟값은 : %d\n", min);

    sum=arr[0];
    for(int i=1; i<5; i++)
    {
        sum += arr[i];
    }
    printf("총합은 : %d\n", sum);
    return 0;
}
```
- - -
문자형 출력 연습
- - -
```
#include <stdio.h>

int main(void)
{
    char str[]="Good morning!";
    printf("배열 str의 크기 : %d \n", sizeof(str));
    printf("널 문자 문자형 출력: %c \n", str[13]);
    printf("널 문자 정수형 출력: %d \n", str[13]);

    str[12]='?';
    printf("문자열 출력 %s \n", str);
    return 0;
}
```
```
#include <stdio.h>

int main(void)
{
    char str[50];
    int idx=0;

    printf("문자열 입력 : ");
    scanf("%s", str);
    printf("입력 받은 문자열 : %s \n", str);

    printf("문자 단위 출력 : ");
    while(str[idx] != '\0')
    {
        printf("%c", str[idx]);
        idx++;
    }
    printf("\n");
    return 0;
}
```
- - -
문자열의 끝에 '널(null)'문자가 필요한 이유
- - -
```
while(str[idx] != '\0')
{
       printf("%c", str[idx]);
       idx++;
}
```
- - -
﻿
문자열의 출력에 사용되는 서식문자 %s가 존재하지 않는다고 가정해 보자.

그래서 배열요소에 일일이 접근을 해서 문자열 전부를 출력해야 한다고 가정해 보자.

이러한 상황에서 문자열의 끝을 나타내기 위한

어떠한 도구도 마련되어 있지 않다면,

문자열을 출력할 수 있겠는가?

﻿
- - -
```
#include <stdio.h>

int main(void)
{
     char str[50]="I like C programming";
     printf("string: %s \n", str);
     
     str[8]='\0';    // 9번째 요소에 널 문자 저장
     printf("string: %s \n", str);
   
    str[6]='\0';      // 7번째 요소에 널 문자 저장
    printf("string: %s \n", str);

   str[1]='\0';   // 2번째 요소에 널 문자 저장
   printf("string: %s \n", str);
   return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233525467-3fde0afe-15ec-4c7d-b90b-fff4b9c10d18.png)
```
#include <stdio.h>

int main(void)
{
    char word[100];
    int len=0;

    printf("영단어 입력 : ");
    scanf("%s", word);
    
    while(word[len] !=0)  // 문자열의 끝을 나타내기 위한 도구. 이것은 좀 외워야할 것 같다..ㄷㄷ
        len++;
    
    printf("입력한 영단어의 길이는 %d \n", len); 

    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233525514-dce29328-ab57-4f61-b271-5f6fb91b4b4f.png)
```
#include <stdio.h>

int main(void)
{
    char word[100];
    int reverse;
    int len=0;
    int i;
    
    printf("영단어를 입력하세요 : ");
    scanf("%s", word)
    
    while(word[len]!='=0')         // 영단어 길이 세기
         len ++;

   for(i=0; i<len/2; i++) // 영단어 뒤집기
  {
        reverse=word[i]   // 앞의 문자 임시로 저장
        word[i]=word[(len-i)-1]; // 제일 뒤문자를 제일 앞 문자와 교체. len-i는 null문자이고 1을 빼서 실제 제일 뒤에 문자
        word[(len-i)-1]=reverse;  // 앞의 문자를 뒤로
  }
 printf("뒤집힌 영단어 : %s \n", word);
 return 0;
}
```

```
#include <stdio.h>

//프로그램 사용자로부터 영단어를 입력 받는다
// 입력 받은 영단어를 구성하는 문자 중에서
// 아스키 코드의 값이 가장 큰 문자를 찾아서
// 출력하는 프로그램을 작성해보자.
// 예를 들어서 입력된 영단어가 "LOVE"라면
// 이 중에서 아스키 코드 값이
// 가장 큰 문자는 V이므로 V가 출력 되어야 한다.

int main(void)
{
    char word[100];
    int len=0;
    int i;
    char max=0;

    printf("영단어 입력 : ");
    scanf("%s", word);

    while(word[len]!='\0')
        len++;

    for(i=0; i<len; i++)
    {
        if(max<word[i])
        {
            max=word[i];
        }
    }
    printf("가장 큰 아스키 코드 값의 문자 : %c \n", max);
    return 0;
}
```
- - -
﻿
아스키코드 가장 큰 값을 구하는 문제였는데,

최댓값 구하는 방법과 비슷했다.

다만 .. 단어의 길이를 구한 뒤 접근해야 했다.

흠..어렵다.

위의 코드를 온전히 이해하기까지 시간이 필요할 것 같다.

﻿
- - -
![image](https://user-images.githubusercontent.com/115389450/233525645-a78cabf5-715d-4e17-80c1-ff71d7cb3b6f.png)
```
#include <stdio.h>

int main(void)
{
      char word[100];

      printf("영어(소문자)를 입력해보세요 : ");
      scanf("%s", word);

      for(int i=0; word[i]; i++)   // 반복문을 쓴 이유? 입력한 소문자 asdsafasf를 넣기 위해서?
      {
          if(word[i]>='a' && word[i]<='z')  // 쓴 것 가운데 소문자 판별.?
          {
                  word[i] = word[i] - 'a'+'A';  // ex) word[a]라면 대문자 A가 출력,
                                                       // word[b]라면 b-a할 시 아스키 코드 숫자 1이남고, 그 다음 'A'를 더하면 대문자 'B'
          }
      }
      printf("%s", word);
      return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233525686-266fa000-d288-44cb-9516-1c1878caea8f.png)
```
#include <stdio.h>

int main(void)
{
    char word[100];

    printf("영어를 입력해보세요 : ");
    gets(word);

    for(int i=0; word[i]!='\0'; i++)
    {
        printf("%d번째 아스키코드 :%d\n", i,word[i]);
    }
    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233525731-88e826dc-ccb2-4b24-b9a6-c971cae77d42.png)
```
#include <stdio.h>
void list();

int main(void)
{
    char arr[100];
    printf("입력 해 주세요 : ");
    list(); // 함수 불러 온다는게 이게 맞을까?

    return 0;
}

void list()
{
    char arr[100];
    gets(arr);  // gets 함수 사용한 이유: 띄어쓰기 까지 포함해서 출력하게끔 하려구
    for(int i=0; arr[i]!='\0'; i++) // word[i]!='\0' 의미?  문자열을 출력해서 아스키코드로 바꾸어야 하는데, 
                                           // \0과 같지 않을때까지 반복한다. 즉 문자열 null까지 읽어주어야 하기 때문에 null까지완료되면
                                           // 반복문 종료 ?
        {
            arr[i-1]=0; // 제일 마지막 문자열 전에 수에 0값 입력
            printf("%d번째 입력한 영어 아스키코드로 출력 : %d\n", i, arr[i]);  //  word[i]를 %d로 받으면 ? 아스키코드 숫자출력
            printf("아스키코드 해석 : %c\n", arr[i]); // word[i]를 다시 %c로 받으면? 문자 출력
        }
}
```
![image](https://user-images.githubusercontent.com/115389450/233525765-366ea050-3688-46be-a283-3e30fbaa3f57.png)
![image](https://user-images.githubusercontent.com/115389450/233525840-4ae2ec4e-9f39-406b-bdec-4b1757b9ae08.png)
```
#include <stdio.h>

int main(void)
{
   int num;
   do
   {
      scanf("%d", &num);
      printf("%c", input);
   }while(num!=-1);
  return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233525908-57663167-4db4-4400-8c68-90be4b179416.png)
![image](https://user-images.githubusercontent.com/115389450/233525934-5fce7abf-0049-47de-a55b-522002638d7e.png)
```
#include <stdio.h>

int main(void)
{
    char english[100]; // 문자열을 입력받을 char함수 배열

    printf("영어를 입력하세요 : "); 
    gets(english); // 띄어쓰기까지 출력하려고 gets 함수사용하였습니다

    for(int i=0; english[i]!='\0'; i++) // 이조건식은 외워는게 좋을 것 같다. '\0'이 아닐때까지 반복한다. 즉 문자열끝까지 채워주면 종료
    {
        english[i-1]=0; // 그 마지막값 전에값에 0을 넣어준다. 이유는? 
        printf("%d번째 입력한 영어 아스키코드로 출력 : %d\n", i, english[i]);
        printf("아스키코드 해석 : %c\n", english[i]);
        printf("위 아스키코드에서 +3을 하여 암호코드를 만들겠다:%d\n", english[i]+3);
        printf("암호화한 아스키코드 해석 : %c\n", english[i]+3);
    }
    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233525973-1b5cfe32-6da0-474e-aa9d-2341ad2490f2.png)


