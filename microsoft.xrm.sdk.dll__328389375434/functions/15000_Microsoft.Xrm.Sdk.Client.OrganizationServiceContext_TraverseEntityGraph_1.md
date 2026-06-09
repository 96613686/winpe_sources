# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph_1

- ea: `0x15000`
- end: `0x1503a`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph_1`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x13b00`
- `0x13f10`
- `0x14050`

## callees

- `0x14f20`
- `0x24b40`

## pseudocode

```c

```

## disassembly

```asm
0x15000  newobj   instance void <>c__DisplayClass102_0::.ctor()
0x15005  stloc.0
0x15006  ldloc.0
0x15007  ldarg.0
0x15008  stfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <>c__DisplayClass102_0::<>4__this
0x1500d  ldloc.0
0x1500e  ldarg.2
0x1500f  stfld    class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.EntityDescriptor> <>c__DisplayClass102_0::onEntity
0x15014  ldloc.0
0x15015  ldarg.3
0x15016  stfld    class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <>c__DisplayClass102_0::onLink
0x1501b  ldarg.1
0x1501c  ldloc.0
0x1501d  ldftn    instance void <>c__DisplayClass102_0::<TraverseEntityGraph>b__0(class Microsoft.Xrm.Sdk.Entity entity)
0x15023  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x15028  ldloc.0
0x15029  ldftn    instance void <>c__DisplayClass102_0::<TraverseEntityGraph>b__1(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x1502f  newobj   instance void class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x15034  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph(class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity> onEntity, class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> onLink)
0x15039  ret
```
