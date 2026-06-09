# <TraverseSelect>d__92::MoveNext

- ea: `0x22cc0`
- end: `0x22de5`
- name: `<TraverseSelect>d__92::MoveNext`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0xa350`
- `0xd5a0`
- `0xd5c0`
- `0x22710`
- `0x22730`
- `0x22c90`
- `0x22cc0`
- `0x22df0`
- `0x22e10`

## pseudocode

```c

```

## disassembly

```asm
0x22cc0  ldarg.0
0x22cc1  ldfld    int32 <TraverseSelect>d__92::<>1__state
0x22cc6  stloc.1
0x22cc7  ldarg.0
0x22cc8  ldfld    class Microsoft.Xrm.Sdk.Linq.QueryProvider <TraverseSelect>d__92::<>4__this
0x22ccd  stloc.2
0x22cce  ldloc.1
0x22ccf  switch   loc_22CE7, loc_22D26, loc_22D9C
0x22ce0  ldc.i4.0
0x22ce1  stloc.0
0x22ce2  leave    loc_22DE3
0x22ce7  ldarg.0
0x22ce8  ldc.i4.m1
0x22ce9  stfld    int32 <TraverseSelect>d__92::<>1__state
0x22cee  ldloc.2
0x22cef  ldarg.0
0x22cf0  ldfld    class [System.Core]System.Linq.Expressions.Expression <TraverseSelect>d__92::exp
0x22cf5  call     instance class EntityColumn Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateSelectColumn(class [System.Core]System.Linq.Expressions.Expression exp)
0x22cfa  stloc.3
0x22cfb  ldloc.3
0x22cfc  brfalse.s loc_22D32
0x22cfe  ldloc.3
0x22cff  callvirt instance bool EntityColumn::get_AllColumns()
0x22d04  brtrue.s loc_22D11
0x22d06  ldloc.3
0x22d07  callvirt instance string EntityColumn::get_Column()
0x22d0c  brfalse  loc_22DD8
0x22d11  ldarg.0
0x22d12  ldloc.3
0x22d13  stfld    class EntityColumn <TraverseSelect>d__92::<>2__current
0x22d18  ldarg.0
0x22d19  ldc.i4.1
0x22d1a  stfld    int32 <TraverseSelect>d__92::<>1__state
0x22d1f  ldc.i4.1
0x22d20  stloc.0
0x22d21  leave    loc_22DE3
0x22d26  ldarg.0
0x22d27  ldc.i4.m1
0x22d28  stfld    int32 <TraverseSelect>d__92::<>1__state
0x22d2d  br       loc_22DD8
0x22d32  ldarg.0
0x22d33  ldarg.0
0x22d34  ldfld    class [System.Core]System.Linq.Expressions.Expression <TraverseSelect>d__92::exp
0x22d39  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression> Microsoft.Xrm.Sdk.Linq.ExpressionExtensions::GetChildren(class [System.Core]System.Linq.Expressions.Expression exp)
0x22d3e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression>::GetEnumerator()
0x22d43  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <TraverseSelect>d__92::<>7__wrap1
0x22d48  ldarg.0
0x22d49  ldc.i4.s 0xFD
0x22d4b  stfld    int32 <TraverseSelect>d__92::<>1__state
0x22d50  br.s     loc_22DBE
0x22d52  ldarg.0
0x22d53  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <TraverseSelect>d__92::<>7__wrap1
0x22d58  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression>::get_Current()
0x22d5d  stloc.s  4
0x22d5f  ldarg.0
0x22d60  ldloc.2
0x22d61  ldloc.s  4
0x22d63  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class EntityColumn> Microsoft.Xrm.Sdk.Linq.QueryProvider::TraverseSelect(class [System.Core]System.Linq.Expressions.Expression exp)
0x22d68  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class EntityColumn>::GetEnumerator()
0x22d6d  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class EntityColumn> <TraverseSelect>d__92::<>7__wrap2
0x22d72  ldarg.0
0x22d73  ldc.i4.s 0xFC
0x22d75  stfld    int32 <TraverseSelect>d__92::<>1__state
0x22d7a  br.s     loc_22DA4
0x22d7c  ldarg.0
0x22d7d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class EntityColumn> <TraverseSelect>d__92::<>7__wrap2
0x22d82  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class EntityColumn>::get_Current()
0x22d87  stloc.s  5
0x22d89  ldarg.0
0x22d8a  ldloc.s  5
0x22d8c  stfld    class EntityColumn <TraverseSelect>d__92::<>2__current
0x22d91  ldarg.0
0x22d92  ldc.i4.2
0x22d93  stfld    int32 <TraverseSelect>d__92::<>1__state
0x22d98  ldc.i4.1
0x22d99  stloc.0
0x22d9a  leave.s  loc_22DE3
0x22d9c  ldarg.0
0x22d9d  ldc.i4.s 0xFC
0x22d9f  stfld    int32 <TraverseSelect>d__92::<>1__state
0x22da4  ldarg.0
0x22da5  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class EntityColumn> <TraverseSelect>d__92::<>7__wrap2
0x22daa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22daf  brtrue.s loc_22D7C
0x22db1  ldarg.0
0x22db2  call     instance void <TraverseSelect>d__92::<>m__Finally2()
0x22db7  ldarg.0
0x22db8  ldnull
0x22db9  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class EntityColumn> <TraverseSelect>d__92::<>7__wrap2
0x22dbe  ldarg.0
0x22dbf  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <TraverseSelect>d__92::<>7__wrap1
0x22dc4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22dc9  brtrue.s loc_22D52
0x22dcb  ldarg.0
0x22dcc  call     instance void <TraverseSelect>d__92::<>m__Finally1()
0x22dd1  ldarg.0
0x22dd2  ldnull
0x22dd3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <TraverseSelect>d__92::<>7__wrap1
0x22dd8  ldc.i4.0
0x22dd9  stloc.0
0x22dda  leave.s  loc_22DE3
0x22ddc  ldarg.0
0x22ddd  call     instance void <TraverseSelect>d__92::System.IDisposable.Dispose()
0x22de2  endfinally
0x22de3  ldloc.0
0x22de4  ret
```
