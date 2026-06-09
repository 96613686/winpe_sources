# <GetRelevantRequests>d__11::MoveNext

- ea: `0x10280`
- end: `0x10327`
- name: `<GetRelevantRequests>d__11::MoveNext`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x5f60`
- `0x10260`
- `0x10280`
- `0x10330`

## pseudocode

```c

```

## disassembly

```asm
0x10280  ldarg.0
0x10281  ldfld    int32 <GetRelevantRequests>d__11::<>1__state
0x10286  stloc.1
0x10287  ldloc.1
0x10288  brfalse.s loc_10295
0x1028a  ldloc.1
0x1028b  ldc.i4.1
0x1028c  beq.s    loc_102F8
0x1028e  ldc.i4.0
0x1028f  stloc.0
0x10290  leave    loc_10325
0x10295  ldarg.0
0x10296  ldc.i4.m1
0x10297  stfld    int32 <GetRelevantRequests>d__11::<>1__state
0x1029c  ldarg.0
0x1029d  ldfld    class [mscorlib]System.Collections.IDictionary <GetRelevantRequests>d__11::requests
0x102a2  newobj   instance void [mscorlib]System.Collections.SortedList::.ctor(class [mscorlib]System.Collections.IDictionary)
0x102a7  stloc.2
0x102a8  ldarg.0
0x102a9  ldloc.2
0x102aa  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.SortedList::get_Values()
0x102af  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x102b4  stfld    class [mscorlib]System.Collections.IEnumerator <GetRelevantRequests>d__11::<>7__wrap1
0x102b9  ldarg.0
0x102ba  ldc.i4.s 0xFD
0x102bc  stfld    int32 <GetRelevantRequests>d__11::<>1__state
0x102c1  br.s     loc_10300
0x102c3  ldarg.0
0x102c4  ldfld    class [mscorlib]System.Collections.IEnumerator <GetRelevantRequests>d__11::<>7__wrap1
0x102c9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x102ce  castclass Microsoft.Crm.Sdk.RequestDescription
0x102d3  stloc.3
0x102d4  ldloc.3
0x102d5  callvirt instance bool Microsoft.Crm.Sdk.RequestDescription::get_Private()
0x102da  ldc.i4.0
0x102db  ceq
0x102dd  ldarg.0
0x102de  ldfld    bool <GetRelevantRequests>d__11::includePrivate
0x102e3  or
0x102e4  brfalse.s loc_10300
0x102e6  ldarg.0
0x102e7  ldloc.3
0x102e8  stfld    object <GetRelevantRequests>d__11::<>2__current
0x102ed  ldarg.0
0x102ee  ldc.i4.1
0x102ef  stfld    int32 <GetRelevantRequests>d__11::<>1__state
0x102f4  ldc.i4.1
0x102f5  stloc.0
0x102f6  leave.s  loc_10325
0x102f8  ldarg.0
0x102f9  ldc.i4.s 0xFD
0x102fb  stfld    int32 <GetRelevantRequests>d__11::<>1__state
0x10300  ldarg.0
0x10301  ldfld    class [mscorlib]System.Collections.IEnumerator <GetRelevantRequests>d__11::<>7__wrap1
0x10306  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1030b  brtrue.s loc_102C3
0x1030d  ldarg.0
0x1030e  call     instance void <GetRelevantRequests>d__11::<>m__Finally1()
0x10313  ldarg.0
0x10314  ldnull
0x10315  stfld    class [mscorlib]System.Collections.IEnumerator <GetRelevantRequests>d__11::<>7__wrap1
0x1031a  ldc.i4.0
0x1031b  stloc.0
0x1031c  leave.s  loc_10325
0x1031e  ldarg.0
0x1031f  call     instance void <GetRelevantRequests>d__11::System.IDisposable.Dispose()
0x10324  endfinally
0x10325  ldloc.0
0x10326  ret
```
