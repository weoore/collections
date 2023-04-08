using System;
using System.Collections.Generic;
using System.Collections;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApplication31
{
    class Program
    {
        static void Main()
        {
            SortedList SL = new SortedList();
            DictionaryEntry[] arr = new DictionaryEntry[10];
            bool Menu = true;
            do
            {
                foreach (DictionaryEntry de in SL)
                {
                    Console.WriteLine("Key = {0}, Value = {1}", de.Key, de.Value);
                }
                Console.WriteLine();
                Console.WriteLine("[1] - Add");
                Console.WriteLine();
                Console.WriteLine("[2] - Remove");
                Console.WriteLine();
                Console.WriteLine("[3] - CopyTo");
                Console.WriteLine();
                Console.WriteLine("[4] - Clear");
                Console.WriteLine();
                Console.WriteLine("[5] - Clone");
                Console.WriteLine();
                Console.WriteLine("[6] - Keys");
                Console.WriteLine();
                Console.WriteLine("[7] - Values");
                Console.WriteLine();
                Console.WriteLine("[8] - Count");
                Console.WriteLine();
                Console.WriteLine("[9] - IsReadOnly");
                Console.WriteLine();
                Console.WriteLine("[10] - IsFixedSize");
                Console.WriteLine();
                Console.WriteLine("[11] - ContainsKey");
                Console.WriteLine();
                Console.WriteLine("[0] - Выход из программы");
                Console.WriteLine();
                int user_input = Convert.ToInt32(Console.ReadLine());
                Console.Clear();
                switch (user_input)
                {
                    case 1:
                        Console.WriteLine("Введите ключ:");
                        string n = Console.ReadLine();
                        Console.WriteLine("Введите значение:");
                        string h = Console.ReadLine();
                        SL.Add(n, h);
                        break;
                    case 2:
                        foreach (DictionaryEntry de in SL)
                        {
                            Console.WriteLine("Key = {0}, Value = {1}", de.Key, de.Value);
                        }
                        Console.WriteLine("Введите ключ который нужно удалить");
                        string j = Console.ReadLine();
                        SL.Remove(j);
                        break;
                    case 3:
                        SL.CopyTo(arr, 3);
                        for (int i = 0; i < 10; i++)
                        {
                            Console.WriteLine(arr[i]);
                        }
                        Console.ReadKey();
                        break;
                    case 4:
                        SL.Clear();
                        break;
                    case 5:
                        SL.Clone();
                        foreach (DictionaryEntry de in SL)
                        {
                            Console.WriteLine("Key = {0}, Value = {1}", de.Key, de.Value);
                        }
                        Console.ReadKey();
                        break;
                    case 6:
                        ICollection g = SL.Keys;
                        foreach (string s in g)
                        {
                            Console.WriteLine(s);
                        }
                        Console.ReadKey();
                        break;
                    case 7:
                        ICollection b = SL.Values;
                        foreach (string s in b)
                        {
                            Console.WriteLine(s);
                        }
                        Console.ReadKey();
                        break;
                    case 8:
                        Console.WriteLine("Количевство пар: " + SL.Count);
                        Console.ReadKey();
                        break;
                    case 9:
                        Console.WriteLine(SL.IsReadOnly);
                        Console.ReadKey();
                        break;
                    case 10:
                        Console.WriteLine(SL.IsFixedSize);
                        Console.ReadKey();
                        break;
                    case 11:
                        Console.WriteLine("Введите ключ");
                        string k = Console.ReadLine();
                        Console.WriteLine(SL.ContainsKey(k));
                        Console.ReadKey();
                        break;
                    case 0:
                        Menu = false;
                        break;
                }
                Console.Clear();
            }
            while (Menu);
        }
    }
}
