# <GetMethodsPreorder>d__9::MoveNext

- ea: `0x21f20`
- end: `0x21ff9`
- name: `<GetMethodsPreorder>d__9::MoveNext`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xa400`
- `0x21f00`
- `0x21f20`
- `0x22000`

## pseudocode

```c

```

## disassembly

```asm
0x21f20  ldarg.0
0x21f21  ldfld    int32 <GetMethodsPreorder>d__9::<>1__state
0x21f26  stloc.1
0x21f27  ldloc.1
0x21f28  switch   loc_21F40, loc_21F7A, loc_21FCA
0x21f39  ldc.i4.0
0x21f3a  stloc.0
0x21f3b  leave    loc_21FF7
0x21f40  ldarg.0
0x21f41  ldc.i4.m1
0x21f42  stfld    int32 <GetMethodsPreorder>d__9::<>1__state
0x21f47  ldarg.0
0x21f48  ldarg.0
0x21f49  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetMethodsPreorder>d__9::exp
0x21f4e  isinst   [System.Core]System.Linq.Expressions.MethodCallExpression
0x21f53  stfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPreorder>d__9::<mce>5__2
0x21f58  ldarg.0
0x21f59  ldfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPreorder>d__9::<mce>5__2
0x21f5e  brfalse  loc_21FEC
0x21f63  ldarg.0
0x21f64  ldarg.0
0x21f65  ldfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPreorder>d__9::<mce>5__2
0x21f6a  stfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPreorder>d__9::<>2__current
0x21f6f  ldarg.0
0x21f70  ldc.i4.1
0x21f71  stfld    int32 <GetMethodsPreorder>d__9::<>1__state
0x21f76  ldc.i4.1
0x21f77  stloc.0
0x21f78  leave.s  loc_21FF7
0x21f7a  ldarg.0
0x21f7b  ldc.i4.m1
0x21f7c  stfld    int32 <GetMethodsPreorder>d__9::<>1__state
0x21f81  ldarg.0
0x21f82  ldarg.0
0x21f83  ldfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPreorder>d__9::<mce>5__2
0x21f88  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0x21f8d  ldc.i4.0
0x21f8e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Item(!!T0)
0x21f93  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.MethodCallExpression> Microsoft.Xrm.Sdk.Linq.ExpressionExtensions::GetMethodsPreorder(class [System.Core]System.Linq.Expressions.Expression exp)
0x21f98  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.MethodCallExpression>::GetEnumerator()
0x21f9d  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.MethodCallExpression> <GetMethodsPreorder>d__9::<>7__wrap2
0x21fa2  ldarg.0
0x21fa3  ldc.i4.s 0xFD
0x21fa5  stfld    int32 <GetMethodsPreorder>d__9::<>1__state
0x21faa  br.s     loc_21FD2
0x21fac  ldarg.0
0x21fad  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.MethodCallExpression> <GetMethodsPreorder>d__9::<>7__wrap2
0x21fb2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.MethodCallExpression>::get_Current()
0x21fb7  stloc.2
0x21fb8  ldarg.0
0x21fb9  ldloc.2
0x21fba  stfld    class [System.Core]System.Linq.Expressions.MethodCallExpression <GetMethodsPreorder>d__9::<>2__current
0x21fbf  ldarg.0
0x21fc0  ldc.i4.2
0x21fc1  stfld    int32 <GetMethodsPreorder>d__9::<>1__state
0x21fc6  ldc.i4.1
0x21fc7  stloc.0
0x21fc8  leave.s  loc_21FF7
0x21fca  ldarg.0
0x21fcb  ldc.i4.s 0xFD
0x21fcd  stfld    int32 <GetMethodsPreorder>d__9::<>1__state
0x21fd2  ldarg.0
0x21fd3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.MethodCallExpression> <GetMethodsPreorder>d__9::<>7__wrap2
0x21fd8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21fdd  brtrue.s loc_21FAC
0x21fdf  ldarg.0
0x21fe0  call     instance void <GetMethodsPreorder>d__9::<>m__Finally1()
0x21fe5  ldarg.0
0x21fe6  ldnull
0x21fe7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.MethodCallExpression> <GetMethodsPreorder>d__9::<>7__wrap2
0x21fec  ldc.i4.0
0x21fed  stloc.0
0x21fee  leave.s  loc_21FF7
0x21ff0  ldarg.0
0x21ff1  call     instance void <GetMethodsPreorder>d__9::System.IDisposable.Dispose()
0x21ff6  endfinally
0x21ff7  ldloc.0
0x21ff8  ret
```
