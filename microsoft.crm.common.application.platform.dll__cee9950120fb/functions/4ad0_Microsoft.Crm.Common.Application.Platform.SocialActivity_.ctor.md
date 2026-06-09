# Microsoft.Crm.Common.Application.Platform.SocialActivity::.ctor

- ea: `0x4ad0`
- end: `0x4ae9`
- name: `Microsoft.Crm.Common.Application.Platform.SocialActivity::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2c70`

## callees

- `0x26a0`

## pseudocode

```c

```

## disassembly

```asm
0x4ad0  ldarg.0
0x4ad1  ldarg.1
0x4ad2  call     instance void Microsoft.Crm.Common.Application.Platform.ActivityBase::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType entityType)
0x4ad7  ldarg.0
0x4ad8  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0x4add  ldstr    aStatuscode// "statuscode"
0x4ae2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4ae7  pop
0x4ae8  ret
```
