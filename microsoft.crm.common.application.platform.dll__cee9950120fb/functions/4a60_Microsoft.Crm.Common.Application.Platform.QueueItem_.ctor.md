# Microsoft.Crm.Common.Application.Platform.QueueItem::.ctor

- ea: `0x4a60`
- end: `0x4a79`
- name: `Microsoft.Crm.Common.Application.Platform.QueueItem::.ctor`
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
0x4a60  ldarg.0
0x4a61  ldarg.1
0x4a62  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x4a67  ldarg.0
0x4a68  call     instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_RequiredColumns()
0x4a6d  ldstr    aQueueid// "queueid"
0x4a72  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4a77  pop
0x4a78  ret
```
