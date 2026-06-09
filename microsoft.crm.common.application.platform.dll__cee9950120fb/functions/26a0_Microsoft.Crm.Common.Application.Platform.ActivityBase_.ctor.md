# Microsoft.Crm.Common.Application.Platform.ActivityBase::.ctor

- ea: `0x26a0`
- end: `0x26b9`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::.ctor`
- size: `25`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2c50`
- `0x2f40`
- `0x31a0`
- `0x3fd0`
- `0x4160`
- `0x46a0`
- `0x4a90`
- `0x4ad0`
- `0x4b40`

## pseudocode

```c

```

## disassembly

```asm
0x26a0  ldarg.0
0x26a1  ldarg.1
0x26a2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x26a7  ldarg.0
0x26a8  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0x26ad  ldstr    aStatecode// "statecode"
0x26b2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x26b7  pop
0x26b8  ret
```
