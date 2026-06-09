# <TraverseEntityGraph>d__100::MoveNext

- ea: `0x248a0`
- end: `0x24a0b`
- name: `<TraverseEntityGraph>d__100::MoveNext`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14f30`
- `0x14f60`
- `0x24870`
- `0x248a0`
- `0x24a10`
- `0x24a30`

## pseudocode

```c

```

## disassembly

```asm
0x248a0  ldarg.0
0x248a1  ldfld    int32 <TraverseEntityGraph>d__100::<>1__state
0x248a6  stloc.1
0x248a7  ldloc.1
0x248a8  switch   loc_248C0, loc_248F2, loc_249BF
0x248b9  ldc.i4.0
0x248ba  stloc.0
0x248bb  leave    loc_24A09
0x248c0  ldarg.0
0x248c1  ldc.i4.m1
0x248c2  stfld    int32 <TraverseEntityGraph>d__100::<>1__state
0x248c7  ldarg.0
0x248c8  ldfld    class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity> <TraverseEntityGraph>d__100::onEntity
0x248cd  ldarg.0
0x248ce  ldfld    class Microsoft.Xrm.Sdk.Entity <TraverseEntityGraph>d__100::entity
0x248d3  callvirt instance void class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity>::Invoke(var<u1>)
0x248d8  ldarg.0
0x248d9  ldarg.0
0x248da  ldfld    class Microsoft.Xrm.Sdk.Entity <TraverseEntityGraph>d__100::entity
0x248df  stfld    class Microsoft.Xrm.Sdk.Entity <TraverseEntityGraph>d__100::<>2__current
0x248e4  ldarg.0
0x248e5  ldc.i4.1
0x248e6  stfld    int32 <TraverseEntityGraph>d__100::<>1__state
0x248eb  ldc.i4.1
0x248ec  stloc.0
0x248ed  leave    loc_24A09
0x248f2  ldarg.0
0x248f3  ldc.i4.m1
0x248f4  stfld    int32 <TraverseEntityGraph>d__100::<>1__state
0x248f9  ldarg.0
0x248fa  ldarg.0
0x248fb  ldfld    class Microsoft.Xrm.Sdk.Entity <TraverseEntityGraph>d__100::entity
0x24900  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseRelatedEntities(class Microsoft.Xrm.Sdk.Entity entity)
0x24905  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>>::GetEnumerator()
0x2490a  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>> <TraverseEntityGraph>d__100::<>7__wrap1
0x2490f  ldarg.0
0x24910  ldc.i4.s 0xFD
0x24912  stfld    int32 <TraverseEntityGraph>d__100::<>1__state
0x24917  br       loc_249E1
0x2491c  ldarg.0
0x2491d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>> <TraverseEntityGraph>d__100::<>7__wrap1
0x24922  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>>::get_Current()
0x24927  dup
0x24928  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::get_Item1()
0x2492d  stloc.2
0x2492e  dup
0x2492f  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::get_Item2()
0x24934  stloc.3
0x24935  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::get_Item3()
0x2493a  stloc.s  4
0x2493c  ldarg.0
0x2493d  ldfld    class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> <TraverseEntityGraph>d__100::onLink
0x24942  ldloc.2
0x24943  ldloc.3
0x24944  ldloc.s  4
0x24946  callvirt instance void class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::Invoke(var<u1>, !!T0, var<u1>)
0x2494b  ldarg.0
0x2494c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <TraverseEntityGraph>d__100::path
0x24951  ldloc.s  4
0x24953  call     T0x2B00007F
0x24958  brtrue   loc_249E1
0x2495d  ldarg.0
0x2495e  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <TraverseEntityGraph>d__100::path
0x24963  ldc.i4.1
0x24964  newarr   Microsoft.Xrm.Sdk.Entity
0x24969  dup
0x2496a  ldc.i4.0
0x2496b  ldloc.s  4
0x2496d  stelem.ref
0x2496e  call     T0x2B000080
0x24973  stloc.s  5
0x24975  ldarg.0
0x24976  ldloc.s  4
0x24978  ldarg.0
0x24979  ldfld    class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity> <TraverseEntityGraph>d__100::onEntity
0x2497e  ldarg.0
0x2497f  ldfld    class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> <TraverseEntityGraph>d__100::onLink
0x24984  ldloc.s  5
0x24986  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph(class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity> onEntity, class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> onLink, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path)
0x2498b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x24990  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Entity> <TraverseEntityGraph>d__100::<>7__wrap2
0x24995  ldarg.0
0x24996  ldc.i4.s 0xFC
0x24998  stfld    int32 <TraverseEntityGraph>d__100::<>1__state
0x2499d  br.s     loc_249C7
0x2499f  ldarg.0
0x249a0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Entity> <TraverseEntityGraph>d__100::<>7__wrap2
0x249a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Entity>::get_Current()
0x249aa  stloc.s  6
0x249ac  ldarg.0
0x249ad  ldloc.s  6
0x249af  stfld    class Microsoft.Xrm.Sdk.Entity <TraverseEntityGraph>d__100::<>2__current
0x249b4  ldarg.0
0x249b5  ldc.i4.2
0x249b6  stfld    int32 <TraverseEntityGraph>d__100::<>1__state
0x249bb  ldc.i4.1
0x249bc  stloc.0
0x249bd  leave.s  loc_24A09
0x249bf  ldarg.0
0x249c0  ldc.i4.s 0xFC
0x249c2  stfld    int32 <TraverseEntityGraph>d__100::<>1__state
0x249c7  ldarg.0
0x249c8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Entity> <TraverseEntityGraph>d__100::<>7__wrap2
0x249cd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x249d2  brtrue.s loc_2499F
0x249d4  ldarg.0
0x249d5  call     instance void <TraverseEntityGraph>d__100::<>m__Finally2()
0x249da  ldarg.0
0x249db  ldnull
0x249dc  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Entity> <TraverseEntityGraph>d__100::<>7__wrap2
0x249e1  ldarg.0
0x249e2  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>> <TraverseEntityGraph>d__100::<>7__wrap1
0x249e7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x249ec  brtrue   loc_2491C
0x249f1  ldarg.0
0x249f2  call     instance void <TraverseEntityGraph>d__100::<>m__Finally1()
0x249f7  ldarg.0
0x249f8  ldnull
0x249f9  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>> <TraverseEntityGraph>d__100::<>7__wrap1
0x249fe  ldc.i4.0
0x249ff  stloc.0
0x24a00  leave.s  loc_24A09
0x24a02  ldarg.0
0x24a03  call     instance void <TraverseEntityGraph>d__100::System.IDisposable.Dispose()
0x24a08  endfinally
0x24a09  ldloc.0
0x24a0a  ret
```
