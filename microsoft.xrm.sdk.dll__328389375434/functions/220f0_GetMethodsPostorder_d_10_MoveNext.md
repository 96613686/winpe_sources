# <GetMethodsPostorder>d__10::MoveNext

- ea: `0x220f0`
- end: `0x221c9`
- name: `<GetMethodsPostorder>d__10::MoveNext`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xa410`
- `0x220d0`
- `0x220f0`
- `0x221d0`

## pseudocode

```c

```

## disassembly

```asm
0x220f0  ldarg.0
0x220f1  ldfld    int32 <GetMethodsPostorder>d__10::<>1__state
0x220f6  stloc.1
0x220f7  ldloc.1
0x220f8  switch   loc_22110, loc_2217C, loc_221B5
0x22109  ldc.i4.0
0x2210a  stloc.0
0x2210b  leave    loc_221C7
0x22110  ldarg.0
0x22111  ldc.i4.m1
0x22112  stfld    int32 <GetMethodsPostorder>d__10::<>1__state
0x22117  ldarg.0
0x22118  ldarg.0
0x22119  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetMethodsPostorder>d__10::exp
0x2211e  isinst   [System.Core]System.Linq.Expressions.MethodCallExpression
0x22123  stfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPostorder>d__10::<mce>5__2
0x22128  ldarg.0
0x22129  ldfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPostorder>d__10::<mce>5__2
0x2212e  brfalse  loc_221BC
0x22133  ldarg.0
0x22134  ldarg.0
0x22135  ldfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPostorder>d__10::<mce>5__2
0x2213a  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0x2213f  ldc.i4.0
0x22140  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Item(!!T0)
0x22145  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.MethodCallExpression> Microsoft.Xrm.Sdk.Linq.ExpressionExtensions::GetMethodsPostorder(class [System.Core]System.Linq.Expressions.Expression exp)
0x2214a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.MethodCallExpression>::GetEnumerator()
0x2214f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.MethodCallExpression> <GetMethodsPostorder>d__10::<>7__wrap2
0x22154  ldarg.0
0x22155  ldc.i4.s 0xFD
0x22157  stfld    int32 <GetMethodsPostorder>d__10::<>1__state
0x2215c  br.s     loc_22184
0x2215e  ldarg.0
0x2215f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.MethodCallExpression> <GetMethodsPostorder>d__10::<>7__wrap2
0x22164  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.MethodCallExpression>::get_Current()
0x22169  stloc.2
0x2216a  ldarg.0
0x2216b  ldloc.2
0x2216c  stfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPostorder>d__10::<>2__current
0x22171  ldarg.0
0x22172  ldc.i4.1
0x22173  stfld    int32 <GetMethodsPostorder>d__10::<>1__state
0x22178  ldc.i4.1
0x22179  stloc.0
0x2217a  leave.s  loc_221C7
0x2217c  ldarg.0
0x2217d  ldc.i4.s 0xFD
0x2217f  stfld    int32 <GetMethodsPostorder>d__10::<>1__state
0x22184  ldarg.0
0x22185  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.MethodCallExpression> <GetMethodsPostorder>d__10::<>7__wrap2
0x2218a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2218f  brtrue.s loc_2215E
0x22191  ldarg.0
0x22192  call     instance void <GetMethodsPostorder>d__10::<>m__Finally1()
0x22197  ldarg.0
0x22198  ldnull
0x22199  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.MethodCallExpression> <GetMethodsPostorder>d__10::<>7__wrap2
0x2219e  ldarg.0
0x2219f  ldarg.0
0x221a0  ldfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPostorder>d__10::<mce>5__2
0x221a5  stfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPostorder>d__10::<>2__current
0x221aa  ldarg.0
0x221ab  ldc.i4.2
0x221ac  stfld    int32 <GetMethodsPostorder>d__10::<>1__state
0x221b1  ldc.i4.1
0x221b2  stloc.0
0x221b3  leave.s  loc_221C7
0x221b5  ldarg.0
0x221b6  ldc.i4.m1
0x221b7  stfld    int32 <GetMethodsPostorder>d__10::<>1__state
0x221bc  ldc.i4.0
0x221bd  stloc.0
0x221be  leave.s  loc_221C7
0x221c0  ldarg.0
0x221c1  call     instance void <GetMethodsPostorder>d__10::System.IDisposable.Dispose()
0x221c6  endfinally
0x221c7  ldloc.0
0x221c8  ret
```
