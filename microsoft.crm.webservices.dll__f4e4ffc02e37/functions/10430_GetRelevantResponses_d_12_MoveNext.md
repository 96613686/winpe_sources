# <GetRelevantResponses>d__12::MoveNext

- ea: `0x10430`
- end: `0x104dc`
- name: `<GetRelevantResponses>d__12::MoveNext`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x5f60`
- `0x5fc0`
- `0x10410`
- `0x10430`
- `0x104e0`

## pseudocode

```c

```

## disassembly

```asm
0x10430  ldarg.0
0x10431  ldfld    int32 <GetRelevantResponses>d__12::<>1__state
0x10436  stloc.1
0x10437  ldloc.1
0x10438  brfalse.s loc_10445
0x1043a  ldloc.1
0x1043b  ldc.i4.1
0x1043c  beq.s    loc_104AD
0x1043e  ldc.i4.0
0x1043f  stloc.0
0x10440  leave    loc_104DA
0x10445  ldarg.0
0x10446  ldc.i4.m1
0x10447  stfld    int32 <GetRelevantResponses>d__12::<>1__state
0x1044c  ldarg.0
0x1044d  ldfld    class [mscorlib]System.Collections.IDictionary <GetRelevantResponses>d__12::requests
0x10452  newobj   instance void [mscorlib]System.Collections.SortedList::.ctor(class [mscorlib]System.Collections.IDictionary)
0x10457  stloc.2
0x10458  ldarg.0
0x10459  ldloc.2
0x1045a  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.SortedList::get_Values()
0x1045f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x10464  stfld    class [mscorlib]System.Collections.IEnumerator <GetRelevantResponses>d__12::<>7__wrap1
0x10469  ldarg.0
0x1046a  ldc.i4.s 0xFD
0x1046c  stfld    int32 <GetRelevantResponses>d__12::<>1__state
0x10471  br.s     loc_104B5
0x10473  ldarg.0
0x10474  ldfld    class [mscorlib]System.Collections.IEnumerator <GetRelevantResponses>d__12::<>7__wrap1
0x10479  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1047e  castclass Microsoft.Crm.Sdk.RequestDescription
0x10483  stloc.3
0x10484  ldloc.3
0x10485  callvirt instance bool Microsoft.Crm.Sdk.RequestDescription::get_Private()
0x1048a  ldc.i4.0
0x1048b  ceq
0x1048d  ldarg.0
0x1048e  ldfld    bool <GetRelevantResponses>d__12::includePrivate
0x10493  or
0x10494  brfalse.s loc_104B5
0x10496  ldarg.0
0x10497  ldloc.3
0x10498  callvirt instance class Microsoft.Crm.Sdk.ResponseDescription Microsoft.Crm.Sdk.RequestDescription::get_ResponseDescription()
0x1049d  stfld    object <GetRelevantResponses>d__12::<>2__current
0x104a2  ldarg.0
0x104a3  ldc.i4.1
0x104a4  stfld    int32 <GetRelevantResponses>d__12::<>1__state
0x104a9  ldc.i4.1
0x104aa  stloc.0
0x104ab  leave.s  loc_104DA
0x104ad  ldarg.0
0x104ae  ldc.i4.s 0xFD
0x104b0  stfld    int32 <GetRelevantResponses>d__12::<>1__state
0x104b5  ldarg.0
0x104b6  ldfld    class [mscorlib]System.Collections.IEnumerator <GetRelevantResponses>d__12::<>7__wrap1
0x104bb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x104c0  brtrue.s loc_10473
0x104c2  ldarg.0
0x104c3  call     instance void <GetRelevantResponses>d__12::<>m__Finally1()
0x104c8  ldarg.0
0x104c9  ldnull
0x104ca  stfld    class [mscorlib]System.Collections.IEnumerator <GetRelevantResponses>d__12::<>7__wrap1
0x104cf  ldc.i4.0
0x104d0  stloc.0
0x104d1  leave.s  loc_104DA
0x104d3  ldarg.0
0x104d4  call     instance void <GetRelevantResponses>d__12::System.IDisposable.Dispose()
0x104d9  endfinally
0x104da  ldloc.0
0x104db  ret
```
