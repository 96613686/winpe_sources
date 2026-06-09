# <GetChildren>d__5::MoveNext

- ea: `0x21a50`
- end: `0x21bb6`
- name: `<GetChildren>d__5::MoveNext`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0xa360`
- `0xa390`
- `0x21a10`
- `0x21a50`
- `0x21bc0`
- `0x21be0`

## pseudocode

```c

```

## disassembly

```asm
0x21a50  ldarg.0
0x21a51  ldfld    int32 <GetChildren>d__5::<>1__state
0x21a56  stloc.1
0x21a57  ldloc.1
0x21a58  switch   loc_21A74, loc_21AC2, loc_21B19, loc_21B87
0x21a6d  ldc.i4.0
0x21a6e  stloc.0
0x21a6f  leave    loc_21BB4
0x21a74  ldarg.0
0x21a75  ldc.i4.m1
0x21a76  stfld    int32 <GetChildren>d__5::<>1__state
0x21a7b  ldarg.0
0x21a7c  ldfld    class [System.Core]System.Linq.Expressions.MemberBinding <GetChildren>d__5::binding
0x21a81  callvirt instance valuetype [System.Core]System.Linq.Expressions.MemberBindingType [System.Core]System.Linq.Expressions.MemberBinding::get_BindingType()
0x21a86  stloc.2
0x21a87  ldloc.2
0x21a88  switch   loc_21A9E, loc_21ACE, loc_21B3D
0x21a99  br       loc_21BA9
0x21a9e  ldarg.0
0x21a9f  ldarg.0
0x21aa0  ldfld    class [System.Core]System.Linq.Expressions.MemberBinding <GetChildren>d__5::binding
0x21aa5  castclass [System.Core]System.Linq.Expressions.MemberAssignment
0x21aaa  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MemberAssignment::get_Expression()
0x21aaf  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__5::<>2__current
0x21ab4  ldarg.0
0x21ab5  ldc.i4.1
0x21ab6  stfld    int32 <GetChildren>d__5::<>1__state
0x21abb  ldc.i4.1
0x21abc  stloc.0
0x21abd  leave    loc_21BB4
0x21ac2  ldarg.0
0x21ac3  ldc.i4.m1
0x21ac4  stfld    int32 <GetChildren>d__5::<>1__state
0x21ac9  br       loc_21BA9
0x21ace  ldarg.0
0x21acf  ldarg.0
0x21ad0  ldfld    class [System.Core]System.Linq.Expressions.MemberBinding <GetChildren>d__5::binding
0x21ad5  castclass [System.Core]System.Linq.Expressions.MemberMemberBinding
0x21ada  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.MemberBinding> [System.Core]System.Linq.Expressions.MemberMemberBinding::get_Bindings()
0x21adf  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression> Microsoft.Xrm.Sdk.Linq.ExpressionExtensions::GetChildren(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.MemberBinding> bindings)
0x21ae4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression>::GetEnumerator()
0x21ae9  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__5::<>7__wrap1
0x21aee  ldarg.0
0x21aef  ldc.i4.s 0xFD
0x21af1  stfld    int32 <GetChildren>d__5::<>1__state
0x21af6  br.s     loc_21B21
0x21af8  ldarg.0
0x21af9  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__5::<>7__wrap1
0x21afe  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression>::get_Current()
0x21b03  stloc.3
0x21b04  ldarg.0
0x21b05  ldloc.3
0x21b06  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__5::<>2__current
0x21b0b  ldarg.0
0x21b0c  ldc.i4.2
0x21b0d  stfld    int32 <GetChildren>d__5::<>1__state
0x21b12  ldc.i4.1
0x21b13  stloc.0
0x21b14  leave    loc_21BB4
0x21b19  ldarg.0
0x21b1a  ldc.i4.s 0xFD
0x21b1c  stfld    int32 <GetChildren>d__5::<>1__state
0x21b21  ldarg.0
0x21b22  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__5::<>7__wrap1
0x21b27  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21b2c  brtrue.s loc_21AF8
0x21b2e  ldarg.0
0x21b2f  call     instance void <GetChildren>d__5::<>m__Finally1()
0x21b34  ldarg.0
0x21b35  ldnull
0x21b36  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__5::<>7__wrap1
0x21b3b  br.s     loc_21BA9
0x21b3d  ldarg.0
0x21b3e  ldarg.0
0x21b3f  ldfld    class [System.Core]System.Linq.Expressions.MemberBinding <GetChildren>d__5::binding
0x21b44  castclass [System.Core]System.Linq.Expressions.MemberListBinding
0x21b49  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.ElementInit> [System.Core]System.Linq.Expressions.MemberListBinding::get_Initializers()
0x21b4e  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression> Microsoft.Xrm.Sdk.Linq.ExpressionExtensions::GetChildren(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.ElementInit> initializers)
0x21b53  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.Expressions.Expression>::GetEnumerator()
0x21b58  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__5::<>7__wrap1
0x21b5d  ldarg.0
0x21b5e  ldc.i4.s 0xFC
0x21b60  stfld    int32 <GetChildren>d__5::<>1__state
0x21b65  br.s     loc_21B8F
0x21b67  ldarg.0
0x21b68  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__5::<>7__wrap1
0x21b6d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression>::get_Current()
0x21b72  stloc.s  4
0x21b74  ldarg.0
0x21b75  ldloc.s  4
0x21b77  stfld    class [System.Core]System.Linq.Expressions.Expression <GetChildren>d__5::<>2__current
0x21b7c  ldarg.0
0x21b7d  ldc.i4.3
0x21b7e  stfld    int32 <GetChildren>d__5::<>1__state
0x21b83  ldc.i4.1
0x21b84  stloc.0
0x21b85  leave.s  loc_21BB4
0x21b87  ldarg.0
0x21b88  ldc.i4.s 0xFC
0x21b8a  stfld    int32 <GetChildren>d__5::<>1__state
0x21b8f  ldarg.0
0x21b90  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__5::<>7__wrap1
0x21b95  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21b9a  brtrue.s loc_21B67
0x21b9c  ldarg.0
0x21b9d  call     instance void <GetChildren>d__5::<>m__Finally2()
0x21ba2  ldarg.0
0x21ba3  ldnull
0x21ba4  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression> <GetChildren>d__5::<>7__wrap1
0x21ba9  ldc.i4.0
0x21baa  stloc.0
0x21bab  leave.s  loc_21BB4
0x21bad  ldarg.0
0x21bae  call     instance void <GetChildren>d__5::System.IDisposable.Dispose()
0x21bb3  endfinally
0x21bb4  ldloc.0
0x21bb5  ret
```
