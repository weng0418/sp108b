# Compiler

```
PS D:\ccc\course\sp\code\c\02-compiler\05-c0c-ir-run> make                            
gcc -std=c99 -O0 map.c util.c ir.c irvm.c lexer.c compiler.c main.c -o compiler       
PS D:\ccc\course\sp\code\c\02-compiler\05-c0c-ir-run> ./compiler test/sum.c -run      
===================irRun()=======================
00: t1 = 0 = 0
01: s = t1 = 0
02: t1 = 1 = 1
03: i = t1 = 1
04: (L1) = 4
05: t2 = i = # Compiler
#### testing sample:(path->test/homework_t)
```
a = 3;
b = 5;
if (a > b){
    t = a;
}
else{
   t = b;
}
```

#### Result:
```
PS D:\ccc\02-compiler\05-compiler-run> ./compiler test/sum.c -run
=======irDump()==========
00: t1 = 3
01: a = t1
02: t1 = 5
03: b = t1
04: t2 = a
05: t3 = b
06: t4 = t2 > t3
07: ifnot t4 goto L1
08: t1 = a
09: t = t1
10: if t4 goto L2
11: (L1)
12: t1 = b
13: t = t1
14: (L2)


PS D:\ccc\02-compiler\05-compiler-run> ./compiler test/sum.c -run
===================irRun()=======================
00: t1 = 3 (3)
01: a = t1 (3)
02: t1 = 5 (5)
03: b = t1 (5)
04: t2 = a (3)
05: t3 = b (5)
06: t4 = t2 > t3 (0)
07: ifnot t4 (0) goto L1 (11)
11: (L1) (11)
12: t1 = b (5)
13: t = t1 (5)
14: (L2) (14)

06: t3 = 10 = 10
07: t4 = t2 <= t3 = 1
08: ifnot t4(=1)  -- fail
09: t1 = s = 0
10: t2 = i = 1
11: t3 = t1 + t2 = 1
12: s = t3 = 1
13: t1 = i = 1
14: t2 = 1 = 1
15: t3 = t1 + t2 = 2
16: i = t3 = 2
17: goto L1 = 4
04: (L1) = 4
05: t2 = i = 2
06: t3 = 10 = 10
07: t4 = t2 <= t3 = 1
08: ifnot t4(=1)  -- fail
09: t1 = s = 1
10: t2 = i = 2
11: t3 = t1 + t2 = 3
12: s = t3 = 3
13: t1 = i = 2
14: t2 = 1 = 1
15: t3 = t1 + t2 = 3
16: i = t3 = 3
17: goto L1 = 4
04: (L1) = 4
05: t2 = i = 3
06: t3 = 10 = 10
07: t4 = t2 <= t3 = 1
08: ifnot t4(=1)  -- fail
09: t1 = s = 3
10: t2 = i = 3
11: t3 = t1 + t2 = 6
12: s = t3 = 6
13: t1 = i = 3
14: t2 = 1 = 1
15: t3 = t1 + t2 = 4
16: i = t3 = 4
17: goto L1 = 4
04: (L1) = 4
05: t2 = i = 4
06: t3 = 10 = 10
07: t4 = t2 <= t3 = 1
08: ifnot t4(=1)  -- fail
09: t1 = s = 6
10: t2 = i = 4
11: t3 = t1 + t2 = 10
12: s = t3 = 10
13: t1 = i = 4
14: t2 = 1 = 1
15: t3 = t1 + t2 = 5
16: i = t3 = 5
17: goto L1 = 4
04: (L1) = 4
05: t2 = i = 5
06: t3 = 10 = 10
07: t4 = t2 <= t3 = 1
08: ifnot t4(=1)  -- fail
09: t1 = s = 10
10: t2 = i = 5
11: t3 = t1 + t2 = 15
12: s = t3 = 15
13: t1 = i = 5
14: t2 = 1 = 1
15: t3 = t1 + t2 = 6
16: i = t3 = 6
17: goto L1 = 4
04: (L1) = 4
05: t2 = i = 6
06: t3 = 10 = 10
07: t4 = t2 <= t3 = 1
08: ifnot t4(=1)  -- fail
09: t1 = s = 15
10: t2 = i = 6
11: t3 = t1 + t2 = 21
12: s = t3 = 21
13: t1 = i = 6
14: t2 = 1 = 1
15: t3 = t1 + t2 = 7
16: i = t3 = 7
17: goto L1 = 4
04: (L1) = 4
05: t2 = i = 7
06: t3 = 10 = 10
07: t4 = t2 <= t3 = 1
08: ifnot t4(=1)  -- fail
09: t1 = s = 21
10: t2 = i = 7
11: t3 = t1 + t2 = 28
12: s = t3 = 28
13: t1 = i = 7
14: t2 = 1 = 1
15: t3 = t1 + t2 = 8
16: i = t3 = 8
17: goto L1 = 4
04: (L1) = 4
05: t2 = i = 8
06: t3 = 10 = 10
07: t4 = t2 <= t3 = 1
08: ifnot t4(=1)  -- fail
09: t1 = s = 28
10: t2 = i = 8
11: t3 = t1 + t2 = 36
12: s = t3 = 36
13: t1 = i = 8
14: t2 = 1 = 1
15: t3 = t1 + t2 = 9
16: i = t3 = 9
17: goto L1 = 4
04: (L1) = 4
05: t2 = i = 9
06: t3 = 10 = 10
07: t4 = t2 <= t3 = 1
08: ifnot t4(=1)  -- fail
09: t1 = s = 36
10: t2 = i = 9
11: t3 = t1 + t2 = 45
12: s = t3 = 45
13: t1 = i = 9
14: t2 = 1 = 1
15: t3 = t1 + t2 = 10
16: i = t3 = 10
17: goto L1 = 4
04: (L1) = 4
05: t2 = i = 10
06: t3 = 10 = 10
07: t4 = t2 <= t3 = 1
08: ifnot t4(=1)  -- fail
09: t1 = s = 45
10: t2 = i = 10
11: t3 = t1 + t2 = 55
12: s = t3 = 55
13: t1 = i = 10
14: t2 = 1 = 1
15: t3 = t1 + t2 = 11
16: i = t3 = 11
17: goto L1 = 4
04: (L1) = 4
05: t2 = i = 11
06: t3 = 10 = 10
07: t4 = t2 <= t3 = 0
08: ifnot t4(=0) goto L2 = 18
18: (L2) = 18
```
