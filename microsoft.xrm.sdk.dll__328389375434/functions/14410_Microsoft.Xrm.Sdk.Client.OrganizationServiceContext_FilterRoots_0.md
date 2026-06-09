# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::FilterRoots_0

- ea: `0x14410`
- end: `0x14495`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::FilterRoots_0`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x143f0`

## callees

- `0x14410`
- `0x14f20`
- `0x23450`

## pseudocode

```c

```

## disassembly

```asm
0x14410  newobj   instance void <>c__DisplayClass72_0::.ctor()
0x14415  stloc.0
0x14416  ldloc.0
0x14417  ldarg.0
0x14418  stfld    class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass72_0::filtered
0x1441d  ldloc.0
0x1441e  ldarg.1
0x1441f  stfld    class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass72_0::unfiltered
0x14424  ldloc.0
0x14425  ldloc.0
0x14426  ldfld    class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass72_0::unfiltered
0x1442b  call     T0x2B000050
0x14430  stfld    class Microsoft.Xrm.Sdk.Entity <>c__DisplayClass72_0::root
0x14435  ldloc.0
0x14436  ldfld    class Microsoft.Xrm.Sdk.Entity <>c__DisplayClass72_0::root
0x1443b  ldloc.0
0x1443c  ldftn    instance void <>c__DisplayClass72_0::<FilterRoots>b__0(class Microsoft.Xrm.Sdk.Entity entity)
0x14442  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x14447  ldsfld   class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> <>c::<>9__72_1
0x1444c  dup
0x1444d  brtrue.s loc_14466
0x1444f  pop
0x14450  ldsfld   class <>c <>c::<>9
0x14455  ldftn    instance void <>c::<FilterRoots>b__72_1(class Microsoft.Xrm.Sdk.Entity s, class Microsoft.Xrm.Sdk.Relationship r, class Microsoft.Xrm.Sdk.Entity t)
0x1445b  newobj   instance void class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x14460  dup
0x14461  stsfld   class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> <>c::<>9__72_1
0x14466  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph(class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity> onEntity, class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> onLink)
0x1446b  call     T0x2B00002B
0x14470  pop
0x14471  ldloc.0
0x14472  ldfld    class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass72_0::unfiltered
0x14477  ldloc.0
0x14478  ldfld    class Microsoft.Xrm.Sdk.Entity <>c__DisplayClass72_0::root
0x1447d  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.Entity>::Remove(var<u1>)
0x14482  pop
0x14483  ldloc.0
0x14484  ldfld    class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass72_0::filtered
0x14489  ldloc.0
0x1448a  ldfld    class Microsoft.Xrm.Sdk.Entity <>c__DisplayClass72_0::root
0x1448f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x14494  ret
```
