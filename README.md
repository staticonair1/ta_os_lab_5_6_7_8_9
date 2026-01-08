5 -->

1)
init یا systemd با PID=1 اولین فرایند بعد از بوت است که سیستم و سرویس‌ها را راه‌اندازی می‌کند و چون فرایندهای بدون والد به آن واگذار می‌شوند، والد همهٔ فرایندها محسوب می‌شود.




2)
-l, --list [signal]
              List signal names.  This option has optional argument, which will convert signal number to signal name,
              or other way round.

 1) SIGHUP       2) SIGINT       3) SIGQUIT      4) SIGILL       5) SIGTRAP
 6) SIGABRT      7) SIGBUS       8) SIGFPE       9) SIGKILL     10) SIGUSR1
11) SIGSEGV     12) SIGUSR2     13) SIGPIPE     14) SIGALRM     15) SIGTERM
16) SIGSTKFLT   17) SIGCHLD     18) SIGCONT     19) SIGSTOP     20) SIGTSTP
21) SIGTTIN     22) SIGTTOU     23) SIGURG      24) SIGXCPU     25) SIGXFSZ
26) SIGVTALRM   27) SIGPROF     28) SIGWINCH    29) SIGIO       30) SIGPWR
31) SIGSYS      34) SIGRTMIN    35) SIGRTMIN+1  36) SIGRTMIN+2  37) SIGRTMIN+3
38) SIGRTMIN+4  39) SIGRTMIN+5  40) SIGRTMIN+6  41) SIGRTMIN+7  42) SIGRTMIN+8
43) SIGRTMIN+9  44) SIGRTMIN+10 45) SIGRTMIN+11 46) SIGRTMIN+12 47) SIGRTMIN+13
48) SIGRTMIN+14 49) SIGRTMIN+15 50) SIGRTMAX-14 51) SIGRTMAX-13 52) SIGRTMAX-12
53) SIGRTMAX-11 54) SIGRTMAX-10 55) SIGRTMAX-9  56) SIGRTMAX-8  57) SIGRTMAX-7
58) SIGRTMAX-6  59) SIGRTMAX-5  60) SIGRTMAX-4  61) SIGRTMAX-3  62) SIGRTMAX-2
63) SIGRTMAX-1  64) SIGRTMAX

pid:
number 20 

3)
IGTERM سیگنال ملایم و قابل‌مدیریت است که به فرایند فرصت خاتمهٔ تمیز می‌دهد، اما SIGKILL (۹) غیرقابل‌گرفتن و غیرقابل‌نادیده‌گرفتن است و فرایند را فوراً می‌کشد؛ از SIGKILL فقط وقتی استفاده می‌کنیم که فرایند به SIGTERM پاسخ نمی‌دهد یا قفل/هنگ کرده است.

4)
تفاوت اصلی این است که در خط اول grep ورودی را از pipe (stdin) می‌گیرد، اما در خط دوم مستقیماً فایل را خودش باز می‌کند؛ نتیجه یکسان است ولی روش اجرا و مصرف منابع متفاوت است (خط دوم کاراتر و ساده‌تر است).
5)

 <img width="624" height="200" alt="image" src="https://github.com/user-attachments/assets/a2e6ead0-c1d6-4685-a1c0-a39c8e67d4fa" />


6)
تغییر، جایگزینی یا حذف کاراکترها از ورودی استاندارد
یک مجموعه از کاراکترها را می‌گیرد و آن‌ها را به مجموعه دیگری تبدیل می‌کند
برای مثال :
ورودی:
apple
orange
banana

خروجی:
APPLE
BANANA
ORANGE

<img width="624" height="200" alt="image" src="https://github.com/user-attachments/assets/a6b77d08-f401-4138-8f1c-016ec2ea4cef" />

 










6-->

1
سیستم‌عامل‌های لینوکس و یونیکس، شل (Shell) برای اجرای هر دستور، به متغیری به نام PATH$ نگاه می‌کند
وقتی از ./ استفاده می‌کنید، در واقع دارید به شل آدرس دقیق (مسیر نسبی) فایل را می‌دهید و به او می‌گویید: «دقیقاً همین فایلی که در پوشه فعلی است را اجرا کن»، و دیگر نیازی به جستجو در PATH$ نیست.

2

 <img width="975" height="380" alt="image" src="https://github.com/user-attachments/assets/98b9c147-879b-4570-8722-9d54288e9b7e" />


3
هر دو متغیر برای دسترسی به تمام آرگومان‌های ورودی خط فرمان (Command-line arguments) به کار می‌روند، اما تفاوت اصلی آن‌ها زمانی مشخص می‌شود که داخل نقل‌قول دوگانه (Double Quotes) قرار بگیرند:
•	"$*": تمام آرگومان‌ها را به عنوان یک رشته واحد (Single String) در نظر می‌گیرد که با اولین کاراکتر متغیر IFS (معمولاً فاصله) از هم جدا شده‌اند.
•	"$@": هر آرگومان را به صورت یک رشته مجزا (Separate Strings) حفظ می‌کند. این حالت معمولاً در حلقه‌های for ایمن‌تر است، مخصوصاً اگر آرگومان‌ها شامل فاصله باشند.



7-->

1

 <img width="624" height="246" alt="image" src="https://github.com/user-attachments/assets/456a4724-2003-4f7e-bb8a-ca108dd017f5" />


2
•  ممکن است اسکریپت خطا بدهد
•  یا شرط اشتباه تفسیر شود
•  یا رفتار غیرقابل پیش‌بینی داشته باشد

3

<img width="518" height="307" alt="image" src="https://github.com/user-attachments/assets/95f36c95-25ad-47ed-a264-238ca948b964" />



<img width="624" height="246" alt="image" src="https://github.com/user-attachments/assets/a3e615df-85fd-498d-8c0f-e204ba59c3ed" />


 8-->
1
-c به فقط کامپایل میکند و مرلحه لینتک کردن در نظر گرفته نمیشود
یک خروجی .o هم میدهد که برای برای پروژه‌های چندفایلی کامپایل جداگانه هر فایل
افزایش سرعت build
استفاده میشود.

2-->

این دستورات در دیباگر gdb استفاده می‌شوند.

🔹 step

وارد داخل تابع می‌شود

برای بررسی دقیق اجرای توابع

step


📌 اگر خط فعلی شامل فراخوانی تابع باشد، وارد بدنه تابع می‌شود.

🔹 next

تابع را به‌صورت کامل اجرا می‌کند

وارد جزئیات تابع نمی‌شود

next


📌 برای عبور سریع از توابعی که مهم نیستند


3-->

<img width="824" height="528" alt="image" src="https://github.com/user-attachments/assets/d993a0ef-859e-458a-9c59-1f55b9eb544d" />


فایل helper.h
#ifndef HELPER_H
#define HELPER_H

void helper();

#endif


فایل helper.c
#include <stdio.h>
#include "helper.h"

void helper() {
    printf("Hello from helper!\n");
}

فایل main.c
#include "helper.h"

int main() {
    helper();
    return 0;
}

فایل Makefile
CC = gcc
CFLAGS = -Wall

all: program

program: main.o helper.o
	$(CC) main.o helper.o -o program

main.o: main.c helper.h
	$(CC) $(CFLAGS) -c main.c

helper.o: helper.c helper.h
	$(CC) $(CFLAGS) -c helper.c

clean:
	rm -f *.o program

  <img width="599" height="234" alt="image" src="https://github.com/user-attachments/assets/52d87b57-a0c2-4718-9abb-25c7ba1b54bc" />

