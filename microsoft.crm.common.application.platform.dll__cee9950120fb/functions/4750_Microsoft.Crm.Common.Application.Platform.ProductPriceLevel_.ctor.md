# Microsoft.Crm.Common.Application.Platform.ProductPriceLevel::.ctor

- ea: `0x4750`
- end: `0x4769`
- name: `Microsoft.Crm.Common.Application.Platform.ProductPriceLevel::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2c70`

## pseudocode

```c

```

## disassembly

```asm
0x4750  ldarg.0
0x4751  ldarg.1
0x4752  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x4757  ldarg.0
0x4758  call     instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_RequiredColumns()
0x475d  ldstr    aProductid// "productid"
0x4762  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4767  pop
0x4768  ret
```
