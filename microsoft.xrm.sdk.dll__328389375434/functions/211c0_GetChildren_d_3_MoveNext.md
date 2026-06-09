# <GetChildren>d__3::MoveNext

- ea: `0x211c0`
- end: `0x21875`
- name: `<GetChildren>d__3::MoveNext`
- size: `1717`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0xa360`
- `0xa390`
- `0x21110`
- `0x211c0`
- `0x21880`
- `0x218a0`
- `0x218c0`
- `0x218e0`
- `0x21900`
- `0x21920`
- `0x21940`

## pseudocode

```c

```

## disassembly

```asm
0x211c0  ldarg.0
0x211c1  ldfld    int32 <GetChildren>d__3::<>1__state
0x211c6  stloc.1
0x211c7  ldloc.1
0x211c8  switch   loc_2122C, loc_21264, loc_212A4, loc_212CF, loc_212FA, loc_21337, loc_21377, loc_213A2, loc_213CD, loc_2140B, loc_2144C, loc_2149A, loc_214F6, loc_21544, loc_215C1, loc_2163E, loc_2169A, loc_216EA, loc_21746, loc_2179B, loc_217F4, loc_21846
0x21225  ldc.i4.0
0x21226  stloc.0
0x21227  leave    loc_21873
0x2122c  ldarg.0
0x2122d  ldc.i4.m1
0x2122e  stfld    int32 <GetChildren>d__3::<>1__state
0x21233  ldarg.0
0x21234  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x21239  isinst   [System.Core]System.Linq.Expressions.UnaryExpression
0x2123e  brfalse.s loc_21270
0x21240  ldarg.0
0x21241  ldarg.0
0x21242  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x21247  castclass [System.Core]System.Linq.Expressions.UnaryExpression
0x2124c  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.UnaryExpression::get_Operand()
0x21251  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x21256  ldarg.0
0x21257  ldc.i4.1
0x21258  stfld    int32 <GetChildren>d__3::<>1__state
0x2125d  ldc.i4.1
0x2125e  stloc.0
0x2125f  leave    loc_21873
0x21264  ldarg.0
0x21265  ldc.i4.m1
0x21266  stfld    int32 <GetChildren>d__3::<>1__state
0x2126b  br       loc_21868
0x21270  ldarg.0
0x21271  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x21276  isinst   [System.Core]System.Linq.Expressions.BinaryExpression
0x2127b  brfalse  loc_21306
0x21280  ldarg.0
0x21281  ldarg.0
0x21282  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x21287  castclass [System.Core]System.Linq.Expressions.BinaryExpression
0x2128c  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0x21291  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x21296  ldarg.0
0x21297  ldc.i4.2
0x21298  stfld    int32 <GetChildren>d__3::<>1__state
0x2129d  ldc.i4.1
0x2129e  stloc.0
0x2129f  leave    loc_21873
0x212a4  ldarg.0
0x212a5  ldc.i4.m1
0x212a6  stfld    int32 <GetChildren>d__3::<>1__state
0x212ab  ldarg.0
0x212ac  ldarg.0
0x212ad  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x212b2  castclass [System.Core]System.Linq.Expressions.BinaryExpression
0x212b7  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Right()
0x212bc  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x212c1  ldarg.0
0x212c2  ldc.i4.3
0x212c3  stfld    int32 <GetChildren>d__3::<>1__state
0x212c8  ldc.i4.1
0x212c9  stloc.0
0x212ca  leave    loc_21873
0x212cf  ldarg.0
0x212d0  ldc.i4.m1
0x212d1  stfld    int32 <GetChildren>d__3::<>1__state
0x212d6  ldarg.0
0x212d7  ldarg.0
0x212d8  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x212dd  castclass [System.Core]System.Linq.Expressions.BinaryExpression
0x212e2  callvirt instance class [System.Core]System.Linq.Expressions.LambdaExpression [System.Core]System.Linq.Expressions.BinaryExpression::get_Conversion()
0x212e7  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x212ec  ldarg.0
0x212ed  ldc.i4.4
0x212ee  stfld    int32 <GetChildren>d__3::<>1__state
0x212f3  ldc.i4.1
0x212f4  stloc.0
0x212f5  leave    loc_21873
0x212fa  ldarg.0
0x212fb  ldc.i4.m1
0x212fc  stfld    int32 <GetChildren>d__3::<>1__state
0x21301  br       loc_21868
0x21306  ldarg.0
0x21307  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x2130c  isinst   [System.Core]System.Linq.Expressions.TypeBinaryExpression
0x21311  brfalse.s loc_21343
0x21313  ldarg.0
0x21314  ldarg.0
0x21315  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x2131a  castclass [System.Core]System.Linq.Expressions.TypeBinaryExpression
0x2131f  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.TypeBinaryExpression::get_Expression()
0x21324  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x21329  ldarg.0
0x2132a  ldc.i4.5
0x2132b  stfld    int32 <GetChildren>d__3::<>1__state
0x21330  ldc.i4.1
0x21331  stloc.0
0x21332  leave    loc_21873
0x21337  ldarg.0
0x21338  ldc.i4.m1
0x21339  stfld    int32 <GetChildren>d__3::<>1__state
0x2133e  br       loc_21868
0x21343  ldarg.0
0x21344  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x21349  isinst   [System.Core]System.Linq.Expressions.ConditionalExpression
0x2134e  brfalse  loc_213D9
0x21353  ldarg.0
0x21354  ldarg.0
0x21355  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x2135a  castclass [System.Core]System.Linq.Expressions.ConditionalExpression
0x2135f  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.ConditionalExpression::get_Test()
0x21364  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x21369  ldarg.0
0x2136a  ldc.i4.6
0x2136b  stfld    int32 <GetChildren>d__3::<>1__state
0x21370  ldc.i4.1
0x21371  stloc.0
0x21372  leave    loc_21873
0x21377  ldarg.0
0x21378  ldc.i4.m1
0x21379  stfld    int32 <GetChildren>d__3::<>1__state
0x2137e  ldarg.0
0x2137f  ldarg.0
0x21380  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x21385  castclass [System.Core]System.Linq.Expressions.ConditionalExpression
0x2138a  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.ConditionalExpression::get_IfTrue()
0x2138f  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x21394  ldarg.0
0x21395  ldc.i4.7
0x21396  stfld    int32 <GetChildren>d__3::<>1__state
0x2139b  ldc.i4.1
0x2139c  stloc.0
0x2139d  leave    loc_21873
0x213a2  ldarg.0
0x213a3  ldc.i4.m1
0x213a4  stfld    int32 <GetChildren>d__3::<>1__state
0x213a9  ldarg.0
0x213aa  ldarg.0
0x213ab  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x213b0  castclass [System.Core]System.Linq.Expressions.ConditionalExpression
0x213b5  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.ConditionalExpression::get_IfFalse()
0x213ba  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x213bf  ldarg.0
0x213c0  ldc.i4.8
0x213c1  stfld    int32 <GetChildren>d__3::<>1__state
0x213c6  ldc.i4.1
0x213c7  stloc.0
0x213c8  leave    loc_21873
0x213cd  ldarg.0
0x213ce  ldc.i4.m1
0x213cf  stfld    int32 <GetChildren>d__3::<>1__state
0x213d4  br       loc_21868
0x213d9  ldarg.0
0x213da  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x213df  isinst   [System.Core]System.Linq.Expressions.MemberExpression
0x213e4  brfalse.s loc_21417
0x213e6  ldarg.0
0x213e7  ldarg.0
0x213e8  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x213ed  castclass [System.Core]System.Linq.Expressions.MemberExpression
0x213f2  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MemberExpression::get_Expression()
0x213f7  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x213fc  ldarg.0
0x213fd  ldc.i4.s 9
0x213ff  stfld    int32 <GetChildren>d__3::<>1__state
0x21404  ldc.i4.1
0x21405  stloc.0
0x21406  leave    loc_21873
0x2140b  ldarg.0
0x2140c  ldc.i4.m1
0x2140d  stfld    int32 <GetChildren>d__3::<>1__state
0x21412  br       loc_21868
0x21417  ldarg.0
0x21418  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x2141d  isinst   [System.Core]System.Linq.Expressions.MethodCallExpression
0x21422  brfalse  loc_214C1
0x21427  ldarg.0
0x21428  ldarg.0
0x21429  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x2142e  castclass [System.Core]System.Linq.Expressions.MethodCallExpression
0x21433  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MethodCallExpression::get_Object()
0x21438  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x2143d  ldarg.0
0x2143e  ldc.i4.s 0xA
0x21440  stfld    int32 <GetChildren>d__3::<>1__state
0x21445  ldc.i4.1
0x21446  stloc.0
0x21447  leave    loc_21873
0x2144c  ldarg.0
0x2144d  ldc.i4.m1
0x2144e  stfld    int32 <GetChildren>d__3::<>1__state
0x21453  ldarg.0
0x21454  ldarg.0
0x21455  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x2145a  castclass [System.Core]System.Linq.Expressions.MethodCallExpression
0x2145f  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0x21464  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::GetEnumerator()
0x21469  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__3::<>7__wrap1
0x2146e  ldarg.0
0x2146f  ldc.i4.s 0xFD
0x21471  stfld    int32 <GetChildren>d__3::<>1__state
0x21476  br.s     loc_214A2
0x21478  ldarg.0
0x21479  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__3::<>7__wrap1
0x2147e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression>::get_Current()
0x21483  stloc.2
0x21484  ldarg.0
0x21485  ldloc.2
0x21486  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x2148b  ldarg.0
0x2148c  ldc.i4.s 0xB
0x2148e  stfld    int32 <GetChildren>d__3::<>1__state
0x21493  ldc.i4.1
0x21494  stloc.0
0x21495  leave    loc_21873
0x2149a  ldarg.0
0x2149b  ldc.i4.s 0xFD
0x2149d  stfld    int32 <GetChildren>d__3::<>1__state
0x214a2  ldarg.0
0x214a3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__3::<>7__wrap1
0x214a8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x214ad  brtrue.s loc_21478
0x214af  ldarg.0
0x214b0  call     instance void <GetChildren>d__3::<>m__Finally1()
0x214b5  ldarg.0
0x214b6  ldnull
0x214b7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__3::<>7__wrap1
0x214bc  br       loc_21868
0x214c1  ldarg.0
0x214c2  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x214c7  isinst   [System.Core]System.Linq.Expressions.LambdaExpression
0x214cc  brfalse  loc_2156B
0x214d1  ldarg.0
0x214d2  ldarg.0
0x214d3  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x214d8  castclass [System.Core]System.Linq.Expressions.LambdaExpression
0x214dd  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.LambdaExpression::get_Body()
0x214e2  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x214e7  ldarg.0
0x214e8  ldc.i4.s 0xC
0x214ea  stfld    int32 <GetChildren>d__3::<>1__state
0x214ef  ldc.i4.1
0x214f0  stloc.0
0x214f1  leave    loc_21873
0x214f6  ldarg.0
0x214f7  ldc.i4.m1
0x214f8  stfld    int32 <GetChildren>d__3::<>1__state
0x214fd  ldarg.0
0x214fe  ldarg.0
0x214ff  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x21504  castclass [System.Core]System.Linq.Expressions.LambdaExpression
0x21509  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.ParameterExpression> [System.Core]System.Linq.Expressions.LambdaExpression::get_Parameters()
0x2150e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.ParameterExpression>::GetEnumerator()
0x21513  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.ParameterExpression> <GetChildren>d__3::<>7__wrap2
0x21518  ldarg.0
0x21519  ldc.i4.s 0xFC
0x2151b  stfld    int32 <GetChildren>d__3::<>1__state
0x21520  br.s     loc_2154C
0x21522  ldarg.0
0x21523  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.ParameterExpression> <GetChildren>d__3::<>7__wrap2
0x21528  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.ParameterExpression>::get_Current()
0x2152d  stloc.3
0x2152e  ldarg.0
0x2152f  ldloc.3
0x21530  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::<>2__current
0x21535  ldarg.0
0x21536  ldc.i4.s 0xD
0x21538  stfld    int32 <GetChildren>d__3::<>1__state
0x2153d  ldc.i4.1
0x2153e  stloc.0
0x2153f  leave    loc_21873
0x21544  ldarg.0
0x21545  ldc.i4.s 0xFC
0x21547  stfld    int32 <GetChildren>d__3::<>1__state
0x2154c  ldarg.0
0x2154d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.ParameterExpression> <GetChildren>d__3::<>7__wrap2
0x21552  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21557  brtrue.s loc_21522
0x21559  ldarg.0
0x2155a  call     instance void <GetChildren>d__3::<>m__Finally2()
0x2155f  ldarg.0
0x21560  ldnull
0x21561  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.ParameterExpression> <GetChildren>d__3::<>7__wrap2
0x21566  br       loc_21868
0x2156b  ldarg.0
0x2156c  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x21571  isinst   [System.Core]System.Linq.Expressions.NewExpression
0x21576  brfalse.s loc_215E8
0x21578  ldarg.0
0x21579  ldarg.0
0x2157a  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__3::exp
0x2157f  castclass [System.Core]System.Linq.Expressions.NewExpression
0x21584  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.NewExpression::get_Arguments()
0x21589  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::GetEnumerator()
0x2158e  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__3::<>7__wrap1
0x21593  ldarg.0
0x21594  ldc.i4.s 0xFB
0x21596  stfld    int32 <GetChildren>d__3::<>1__state
0x2159b  br.s     loc_215C9
0x2159d  ldarg.0
0x2159e  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__3::<>7__wrap1
  ... truncated ...
```
