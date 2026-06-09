# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachEntityGraph

- ea: `0x13930`
- end: `0x13969`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachEntityGraph`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x13560`
- `0x13d20`
- `0x14760`

## callees

- `0x14f20`
- `0x233f0`

## pseudocode

```c

```

## disassembly

```asm
0x13930  newobj   instance void <>c__DisplayClass43_0::.ctor()
0x13935  stloc.0
0x13936  ldloc.0
0x13937  ldarg.0
0x13938  stfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <>c__DisplayClass43_0::<>4__this
0x1393d  ldloc.0
0x1393e  ldarg.2
0x1393f  stfld    valuetype Microsoft.Xrm.Sdk.EntityStates <>c__DisplayClass43_0::state
0x13944  ldarg.1
0x13945  ldloc.0
0x13946  ldftn    instance void <>c__DisplayClass43_0::<AttachEntityGraph>b__0(class Microsoft.Xrm.Sdk.Entity entity)
0x1394c  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x13951  ldloc.0
0x13952  ldftn    instance void <>c__DisplayClass43_0::<AttachEntityGraph>b__1(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13958  newobj   instance void class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x1395d  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph(class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity> onEntity, class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> onLink)
0x13962  call     T0x2B00002B
0x13967  pop
0x13968  ret
```
