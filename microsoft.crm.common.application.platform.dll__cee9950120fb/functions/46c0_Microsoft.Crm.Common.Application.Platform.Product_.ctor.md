# Microsoft.Crm.Common.Application.Platform.Product::.ctor

- ea: `0x46c0`
- end: `0x46fb`
- name: `Microsoft.Crm.Common.Application.Platform.Product::.ctor`
- size: `59`
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
0x46c0  ldarg.0
0x46c1  ldarg.1
0x46c2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x46c7  ldarg.0
0x46c8  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0x46cd  ldstr    aStatecode// "statecode"
0x46d2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x46d7  pop
0x46d8  ldarg.0
0x46d9  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0x46de  ldstr    aIskit// "iskit"
0x46e3  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x46e8  pop
0x46e9  ldarg.0
0x46ea  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0x46ef  ldstr    aProductstructu// "productstructure"
0x46f4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x46f9  pop
0x46fa  ret
```
