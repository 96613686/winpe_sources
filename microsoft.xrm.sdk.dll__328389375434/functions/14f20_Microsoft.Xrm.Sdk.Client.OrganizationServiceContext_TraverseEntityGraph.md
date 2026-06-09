# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph

- ea: `0x14f20`
- end: `0x14f2f`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph`
- size: `15`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x138d0`
- `0x13930`
- `0x14010`
- `0x14410`
- `0x15000`

## callees

- `0x14f30`

## pseudocode

```c

```

## disassembly

```asm
0x14f20  ldarg.0
0x14f21  ldarg.1
0x14f22  ldarg.2
0x14f23  ldc.i4.0
0x14f24  newarr   Microsoft.Xrm.Sdk.Entity
0x14f29  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseEntityGraph(class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Action`1<class Microsoft.Xrm.Sdk.Entity> onEntity, class [mscorlib]System.Action`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> onLink, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path)
0x14f2e  ret
```
