# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ValidateAttach

- ea: `0x138d0`
- end: `0x13928`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ValidateAttach`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x13560`
- `0x13d20`

## callees

- `0x138d0`
- `0x14f20`
- `0x23210`

## pseudocode

```c

```

## disassembly

```asm
0x138d0  newobj   instance void <>c__DisplayClass42_0::.ctor()
0x138d5  stloc.0
0x138d6  ldloc.0
0x138d7  ldarg.1
0x138d8  stfld    class Microsoft.Xrm.Sdk.Entity <>c__DisplayClass42_0::graph
0x138dd  ldloc.0
0x138de  ldarg.0
0x138df  stfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <>c__DisplayClass42_0::<>4__this
0x138e4  ldloc.0
0x138e5  ldarg.2
0x138e6  stfld    valuetype Microsoft.Xrm.Sdk.EntityStates <>c__DisplayClass42_0::state
0x138eb  ldloc.0
0x138ec  ldfld    class Microsoft.Xrm.Sdk.Entity <>c__DisplayClass42_0::graph
0x138f1  ldloc.0
0x138f2  ldftn    instance void <>c__DisplayClass42_0::<ValidateAttach>b__0(class Microsoft.Xrm.Sdk.Entity entity)
0x138f8  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x138fd  ldsfld   class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> <>c::<>9__42_1
0x13902  dup
0x13903  brtrue.s loc_1391C
0x13905  pop
0x13906  ldsfld   class <>c <>c::<>9
0x1390b  ldftn    instance void <>c::<ValidateAttach>b__42_1(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13911  newobj   instance void class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x13916  dup
0x13917  stsfld   class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> <>c::<>9__42_1
0x1391c  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph(class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity> onEntity, class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> onLink)
0x13921  call     T0x2B00002B
0x13926  pop
0x13927  ret
```
