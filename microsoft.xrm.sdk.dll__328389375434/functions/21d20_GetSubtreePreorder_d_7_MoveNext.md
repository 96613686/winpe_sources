# <GetSubtreePreorder>d__7::MoveNext

- ea: `0x21d20`
- end: `0x21df9`
- name: `<GetSubtreePreorder>d__7::MoveNext`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xa350`
- `0x21d00`
- `0x21d20`
- `0x21e00`

## pseudocode

```c

```

## disassembly

```asm
0x21d20  ldarg.0
0x21d21  ldfld    int32 <GetSubtreePreorder>d__7::<>1__state
0x21d26  stloc.1
0x21d27  ldloc.1
0x21d28  switch   loc_21D40, loc_21D61, loc_21DCA
0x21d39  ldc.i4.0
0x21d3a  stloc.0
0x21d3b  leave    loc_21DF7
0x21d40  ldarg.0
0x21d41  ldc.i4.m1
0x21d42  stfld    int32 <GetSubtreePreorder>d__7::<>1__state
0x21d47  ldarg.0
0x21d48  ldarg.0
0x21d49  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetSubtreePreorder>d__7::exp
0x21d4e  stfld    class [System.Core]System.Linq.Expressions.Expression <GetSubtreePreorder>d__7::<>2__current
0x21d53  ldarg.0
0x21d54  ldc.i4.1
0x21d55  stfld    int32 <GetSubtreePreorder>d__7::<>1__state
0x21d5a  ldc.i4.1
0x21d5b  stloc.0
0x21d5c  leave    loc_21DF7
0x21d61  ldarg.0
0x21d62  ldc.i4.m1
0x21d63  stfld    int32 <GetSubtreePreorder>d__7::<>1__state
0x21d68  ldarg.0
0x21d69  ldarg.0
0x21d6a  ldfld    class [System.Core]System.Linq.Expressions.Expression <GetSubtreePreorder>d__7::exp
0x21d6f  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression> Microsoft.Xrm.Sdk.Linq.ExpressionExtensions::GetChildren(class [System.Core]System.Linq.Expressions.Expression exp)
0x21d74  ldsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression>> <>c::<>9__7_0
0x21d79  dup
0x21d7a  brtrue.s loc_21D93
0x21d7c  pop
0x21d7d  ldsfld   class <>c <>c::<>9
0x21d82  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression> <>c::<GetSubtreePreorder>b__7_0(class [System.Core]System.Linq.Expressions.Expression child)
0x21d88  newobj   instance void class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression>>::.ctor(object, native int)
0x21d8d  dup
0x21d8e  stsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression>> <>c::<>9__7_0
0x21d93  call     T0x2B000078
0x21d98  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression>::GetEnumerator()
0x21d9d  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetSubtreePreorder>d__7::<>7__wrap1
0x21da2  ldarg.0
0x21da3  ldc.i4.s 0xFD
0x21da5  stfld    int32 <GetSubtreePreorder>d__7::<>1__state
0x21daa  br.s     loc_21DD2
0x21dac  ldarg.0
0x21dad  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetSubtreePreorder>d__7::<>7__wrap1
0x21db2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression>::get_Current()
0x21db7  stloc.2
0x21db8  ldarg.0
0x21db9  ldloc.2
0x21dba  stfld    class [System.Core]System.Linq.Expressions.Expression <GetSubtreePreorder>d__7::<>2__current
0x21dbf  ldarg.0
0x21dc0  ldc.i4.2
0x21dc1  stfld    int32 <GetSubtreePreorder>d__7::<>1__state
0x21dc6  ldc.i4.1
0x21dc7  stloc.0
0x21dc8  leave.s  loc_21DF7
0x21dca  ldarg.0
0x21dcb  ldc.i4.s 0xFD
0x21dcd  stfld    int32 <GetSubtreePreorder>d__7::<>1__state
0x21dd2  ldarg.0
0x21dd3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetSubtreePreorder>d__7::<>7__wrap1
0x21dd8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21ddd  brtrue.s loc_21DAC
0x21ddf  ldarg.0
0x21de0  call     instance void <GetSubtreePreorder>d__7::<>m__Finally1()
0x21de5  ldarg.0
0x21de6  ldnull
0x21de7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetSubtreePreorder>d__7::<>7__wrap1
0x21dec  ldc.i4.0
0x21ded  stloc.0
0x21dee  leave.s  loc_21DF7
0x21df0  ldarg.0
0x21df1  call     instance void <GetSubtreePreorder>d__7::System.IDisposable.Dispose()
0x21df6  endfinally
0x21df7  ldloc.0
0x21df8  ret
```
