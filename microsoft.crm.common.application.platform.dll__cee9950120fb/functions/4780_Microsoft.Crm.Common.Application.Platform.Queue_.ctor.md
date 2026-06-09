# Microsoft.Crm.Common.Application.Platform.Queue::.ctor

- ea: `0x4780`
- end: `0x4799`
- name: `Microsoft.Crm.Common.Application.Platform.Queue::.ctor`
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
0x4780  ldarg.0
0x4781  ldarg.1
0x4782  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x4787  ldarg.0
0x4788  call     instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_RequiredColumns()
0x478d  ldstr    aQueueid// "queueid"
0x4792  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4797  pop
0x4798  ret
```
