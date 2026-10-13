Bro, got it 😭 You want 20 proper C# logic programs, not basic ones like Hello World or addition. And every program must get input from the user using `Console.ReadLine()` — no hardcoded values.

These are suitable for your C# Console Application in Visual Studio 2015. Each is a separate program, so copy one at a time into `Program.cs`.

# 20 C# logic programs with code

## 1. Fibonacci Series

Enter the number of terms to display.

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter number of terms: ");
        int n = int.Parse(Console.ReadLine());

        int a = 0, b = 1, c;

        for (int i = 1; i <= n; i++)
        {
            Console.Write(a + " ");
            c = a + b;
            a = b;
            b = c;
        }

        Console.ReadLine();
    }
}
```

## 2. Factorial of a Number

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int n = int.Parse(Console.ReadLine());

        long fact = 1;

        for (int i = 1; i <= n; i++)
            fact = fact * i;

        Console.WriteLine("Factorial = " + fact);
        Console.ReadLine();
    }
}
```

## 3. Prime Number Check

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int n = int.Parse(Console.ReadLine());

        bool prime = n >= 2;

        for (int i = 2; i <= n / i; i++)
        {
            if (n % i == 0)
            {
                prime = false;
                break;
            }
        }

        Console.WriteLine(prime ? "Prime" : "Not Prime");
        Console.ReadLine();
    }
}
```

## 4. Armstrong Number

Works for any non-negative integer, such as 153 or 1634.

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int n = int.Parse(Console.ReadLine());

        if (n < 0)
        {
            Console.WriteLine("Invalid number");
            return;
        }

        int temp = n, digits = n.ToString().Length;
        long sum = 0;

        do
        {
            int rem = temp % 10;
            long power = 1;

            for (int i = 1; i <= digits; i++)
                power *= rem;

            sum += power;
            temp /= 10;
        }
        while (temp > 0);

        Console.WriteLine(sum == n
            ? "Armstrong Number"
            : "Not Armstrong");

        Console.ReadLine();
    }
}
```

## 5. Palindrome Number

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int n = int.Parse(Console.ReadLine());

        int temp = n, rev = 0;

        while (temp > 0)
        {
            rev = rev * 10 + temp % 10;
            temp /= 10;
        }

        Console.WriteLine(n >= 0 && n == rev
            ? "Palindrome" : "Not Palindrome");

        Console.ReadLine();
    }
}
```

## 6. Reverse a Number

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int n = int.Parse(Console.ReadLine());

        long rev = 0;
        int temp = Math.Abs(n);

        while (temp > 0)
        {
            rev = rev * 10 + temp % 10;
            temp /= 10;
        }

        if (n < 0) rev = -rev;

        Console.WriteLine("Reverse = " + rev);
        Console.ReadLine();
    }
}
```

## 7. Sum of Digits Until One Digit Remains

Example: `9875 → 9+8+7+5 = 29 → 2+9 = 11 → 1+1 = 2`

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int n = Math.Abs(int.Parse(Console.ReadLine()));

        while (n >= 10)
        {
            int sum = 0;

            while (n > 0)
            {
                sum += n % 10;
                n /= 10;
            }

            n = sum;
        }

        Console.WriteLine("Single digit = " + n);
        Console.ReadLine();
    }
}
```

## 8. GCD and LCM of Two Numbers

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter first number: ");
        int a = int.Parse(Console.ReadLine());

        Console.Write("Enter second number: ");
        int b = int.Parse(Console.ReadLine());

        int x = Math.Abs(a), y = Math.Abs(b);

        while (y != 0)
        {
            int r = x % y;
            x = y;
            y = r;
        }

        int gcd = x;
        long lcm = (a == 0 || b == 0)
            ? 0 : Math.Abs((long)a / gcd * b);

        Console.WriteLine("GCD = " + gcd);
        Console.WriteLine("LCM = " + lcm);
        Console.ReadLine();
    }
}
```

## 9. Perfect Number

A perfect number equals the sum of its proper divisors. Example: `6 = 1 + 2 + 3`.

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int n = int.Parse(Console.ReadLine());

        int sum = 0;

        for (int i = 1; i <= n / 2; i++)
        {
            if (n % i == 0)
                sum += i;
        }

        Console.WriteLine(n > 1 && sum == n
            ? "Perfect Number" : "Not Perfect");

        Console.ReadLine();
    }
}
```

## 10. Strong Number

Example: `145 = 1! + 4! + 5! = 145`.

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int n = int.Parse(Console.ReadLine());

        int temp = n, sum = 0;

        while (temp > 0)
        {
            int rem = temp % 10;
            int fact = 1;

            for (int i = 1; i <= rem; i++)
                fact *= i;

            sum += fact;
            temp /= 10;
        }

        Console.WriteLine(n >= 0 && sum == n
            ? "Strong Number" : "Not Strong");

        Console.ReadLine();
    }
}
```

## 11. Convert Decimal to Binary

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a decimal number: ");
        int n = int.Parse(Console.ReadLine());

        if (n == 0)
        {
            Console.WriteLine("Binary = 0");
        }
        else
        {
            string binary = "";
            int temp = Math.Abs(n);

            while (temp > 0)
            {
                binary = (temp % 2) + binary;
                temp /= 2;
            }

            if (n < 0) binary = "-" + binary;

            Console.WriteLine("Binary = " + binary);
        }

        Console.ReadLine();
    }
}
```

## 12. Check Leap Year

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter year: ");
        int year = int.Parse(Console.ReadLine());

        if (year % 400 == 0 ||
            (year % 4 == 0 && year % 100 != 0))
            Console.WriteLine("Leap Year");
        else
            Console.WriteLine("Not a Leap Year");

        Console.ReadLine();
    }
}
```

## 13. Sort an Array in Ascending Order

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter array size: ");
        int n = int.Parse(Console.ReadLine());

        int[] a = new int[n];

        for (int i = 0; i < n; i++)
        {
            Console.Write("Enter element: ");
            a[i] = int.Parse(Console.ReadLine());
        }

        Array.Sort(a);

        Console.WriteLine("Sorted Array:");

        foreach (int x in a)
            Console.Write(x + " ");

        Console.ReadLine();
    }
}
```

## 14. Find the Second Largest Element

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter array size: ");
        int n = int.Parse(Console.ReadLine());

        if (n < 2)
        {
            Console.WriteLine("Enter at least 2 elements");
            return;
        }

        int[] a = new int[n];

        for (int i = 0; i < n; i++)
        {
            Console.Write("Enter element: ");
            a[i] = int.Parse(Console.ReadLine());
        }

        Array.Sort(a);

        int largest = a[n - 1];
        int i = n - 2;

        while (i >= 0 && a[i] == largest)
            i--;

        if (i >= 0)
            Console.WriteLine("Second Largest = " + a[i]);
        else
            Console.WriteLine("No second distinct largest element");

        Console.ReadLine();
    }
}
```

## 15. Search an Element in an Array

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter array size: ");
        int n = int.Parse(Console.ReadLine());

        int[] a = new int[n];

        for (int i = 0; i < n; i++)
        {
            Console.Write("Enter element: ");
            a[i] = int.Parse(Console.ReadLine());
        }

        Console.Write("Enter element to search: ");
        int key = int.Parse(Console.ReadLine());

        int pos = -1;

        for (int i = 0; i < n; i++)
        {
            if (a[i] == key)
            {
                pos = i;
                break;
            }
        }

        if (pos != -1)
            Console.WriteLine("Found at position " + (pos + 1));
        else
            Console.WriteLine("Element not found");

        Console.ReadLine();
    }
}
```

## 16. Check Whether Two Strings Are Anagrams

Example: `listen` and `silent`.

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter first string: ");
        string a = Console.ReadLine().Replace(" ", "").ToLower();

        Console.Write("Enter second string: ");
        string b = Console.ReadLine().Replace(" ", "").ToLower();

        char[] x = a.ToCharArray();
        char[] y = b.ToCharArray();

        Array.Sort(x);
        Array.Sort(y);

        Console.WriteLine(
            new string(x) == new string(y)
            ? "Anagrams" : "Not Anagrams");

        Console.ReadLine();
    }
}
```

## 17. Count Vowels and Consonants

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter a string: ");
        string s = Console.ReadLine().ToLower();

        int vowels = 0, consonants = 0;

        foreach (char c in s)
        {
            if (c >= 'a' && c <= 'z')
            {
                if ("aeiou".IndexOf(c) >= 0)
                    vowels++;
                else
                    consonants++;
            }
        }

        Console.WriteLine("Vowels = " + vowels);
        Console.WriteLine("Consonants = " + consonants);

        Console.ReadLine();
    }
}
```

## 18. Addition of Two Matrices

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int r = int.Parse(Console.ReadLine());

        Console.Write("Enter columns: ");
        int c = int.Parse(Console.ReadLine());

        int[,] a = new int[r, c];
        int[,] b = new int[r, c];

        Console.WriteLine("Enter first matrix:");

        for (int i = 0; i < r; i++)
            for (int j = 0; j < c; j++)
                a[i, j] = int.Parse(Console.ReadLine());

        Console.WriteLine("Enter second matrix:");

        for (int i = 0; i < r; i++)
            for (int j = 0; j < c; j++)
                b[i, j] = int.Parse(Console.ReadLine());

        Console.WriteLine("Sum of matrices:");

        for (int i = 0; i < r; i++)
        {
            for (int j = 0; j < c; j++)
                Console.Write((a[i, j] + b[i, j]) + "\t");

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 19. Transpose of a Matrix

Rows become columns and columns become rows.

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int r = int.Parse(Console.ReadLine());

        Console.Write("Enter columns: ");
        int c = int.Parse(Console.ReadLine());

        int[,] a = new int[r, c];

        Console.WriteLine("Enter matrix elements:");

        for (int i = 0; i < r; i++)
            for (int j = 0; j < c; j++)
                a[i, j] = int.Parse(Console.ReadLine());

        Console.WriteLine("Transpose:");

        for (int j = 0; j < c; j++)
        {
            for (int i = 0; i < r; i++)
                Console.Write(a[i, j] + "\t");

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 20. Menu-Driven Calculator

Uses `switch` to perform arithmetic operations selected by the user.

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter first number: ");
        double a = double.Parse(Console.ReadLine());

        Console.Write("Enter second number: ");
        double b = double.Parse(Console.ReadLine());

        Console.WriteLine("1. Addition");
        Console.WriteLine("2. Subtraction");
        Console.WriteLine("3. Multiplication");
        Console.WriteLine("4. Division");

        Console.Write("Enter choice: ");
        int ch = int.Parse(Console.ReadLine());

        switch (ch)
        {
            case 1:
                Console.WriteLine("Result = " + (a + b));
                break;

            case 2:
                Console.WriteLine("Result = " + (a - b));
                break;

            case 3:
                Console.WriteLine("Result = " + (a * b));
                break;

            case 4:
                if (b != 0)
                    Console.WriteLine("Result = " + (a / b));
                else
                    Console.WriteLine("Cannot divide by zero");
                break;

            default:
                Console.WriteLine("Invalid choice");
                break;
        }

        Console.ReadLine();
    }
}
```

## Last-minute practical exam revision

These are the programs I'd prioritise for your exam:

| Priority      | Programs                                           |
| ------------- | -------------------------------------------------- |
| Must practise | Fibonacci, factorial, prime, Armstrong, palindrome |
| Number logic  | Strong number, perfect number, GCD and LCM         |
| Arrays        | Sorting, second largest, searching                 |
| Strings       | Anagram, vowels and consonants                     |
| Matrices      | Matrix addition, transpose                         |
| Other logic   | Decimal to binary, leap year, calculator           |

Bro 😭🔥 yes! Triangle pattern programs are also very common in C# practical exams. Here are 10 triangle programs, all taking the number of rows from the user.

## 1. Right-Angled Star Triangle

Output for 5 rows:

```
*
**
***
****
*****
```

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int n = int.Parse(Console.ReadLine());

        for (int i = 1; i <= n; i++)
        {
            for (int j = 1; j <= i; j++)
                Console.Write("*");

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 2. Inverted Star Triangle

```
*****
****
***
**
*
```

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int n = int.Parse(Console.ReadLine());

        for (int i = n; i >= 1; i--)
        {
            for (int j = 1; j <= i; j++)
                Console.Write("*");

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 3. Pyramid Star Triangle

```
    *
   ***
  *****
 *******
*********
```

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int n = int.Parse(Console.ReadLine());

        for (int i = 1; i <= n; i++)
        {
            for (int j = 1; j <= n - i; j++)
                Console.Write(" ");

            for (int j = 1; j <= 2 * i - 1; j++)
                Console.Write("*");

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 4. Inverted Pyramid

```
*********
 *******
  *****
   ***
    *
```

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int n = int.Parse(Console.ReadLine());

        for (int i = n; i >= 1; i--)
        {
            for (int j = 1; j <= n - i; j++)
                Console.Write(" ");

            for (int j = 1; j <= 2 * i - 1; j++)
                Console.Write("*");

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 5. Number Triangle

```
1
12
123
1234
12345
```

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int n = int.Parse(Console.ReadLine());

        for (int i = 1; i <= n; i++)
        {
            for (int j = 1; j <= i; j++)
                Console.Write(j);

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 6. Same-Number Triangle

```
1
22
333
4444
55555
```

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int n = int.Parse(Console.ReadLine());

        for (int i = 1; i <= n; i++)
        {
            for (int j = 1; j <= i; j++)
                Console.Write(i);

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 7. Inverted Number Triangle

```
12345
1234
123
12
1
```

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int n = int.Parse(Console.ReadLine());

        for (int i = n; i >= 1; i--)
        {
            for (int j = 1; j <= i; j++)
                Console.Write(j);

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 8. Floyd's Triangle

```
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
```

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int n = int.Parse(Console.ReadLine());

        int num = 1;

        for (int i = 1; i <= n; i++)
        {
            for (int j = 1; j <= i; j++)
            {
                Console.Write(num + " ");
                num++;
            }

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 9. Hollow Star Triangle

```
*
**
* *
*  *
*****
```

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows (minimum 2): ");
        int n = int.Parse(Console.ReadLine());

        for (int i = 1; i <= n; i++)
        {
            for (int j = 1; j <= i; j++)
            {
                if (j == 1 || j == i || i == n)
                    Console.Write("*");
                else
                    Console.Write(" ");
            }

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## 10. Pascal's Triangle

```
    1
   1 1
  1 2 1
 1 3 3 1
1 4 6 4 1
```

```
using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter rows: ");
        int n = int.Parse(Console.ReadLine());

        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n - i - 1; j++)
                Console.Write(" ");

            long value = 1;

            for (int j = 0; j <= i; j++)
            {
                Console.Write(value + " ");
                value = value * (i - j) / (j + 1);
            }

            Console.WriteLine();
        }

        Console.ReadLine();
    }
}
```

## The main trick to remember for your exam

| Pattern type        | Outer loop     | Inner loop                    |
| ------------------- | -------------- | ----------------------------- |
| Increasing triangle | `i = 1` to `n` | `j = 1` to `i`                |
| Decreasing triangle | `i = n` to `1` | `j = 1` to `i`                |
| Pyramid             | `i = 1` to `n` | Spaces: `n-i`; stars: `2*i-1` |
| Number triangle     | `i = 1` to `n` | Print `j` or `i`              |
| Floyd's triangle    | `i = 1` to `n` | Print and increment `num`     |

Exam tip: Practise programs 1, 2, 3, 5, 8 and 10 first. Once you understand nested `for` loops, you can build many other patterns by changing the spaces, stars and numbers.
