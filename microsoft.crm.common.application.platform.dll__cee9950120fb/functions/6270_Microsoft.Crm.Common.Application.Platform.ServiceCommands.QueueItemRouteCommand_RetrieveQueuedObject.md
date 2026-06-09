# Microsoft.Crm.Common.Application.Platform.ServiceCommands.QueueItemRouteCommand::RetrieveQueuedObject

- ea: `0x6270`
- end: `0x629a`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.QueueItemRouteCommand::RetrieveQueuedObject`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x6170`

## pseudocode

```c

```

## disassembly

```asm
0x6270  ldc.i4.2
0x6271  newarr   [mscorlib]System.String
0x6276  dup
0x6277  ldc.i4.0
0x6278  ldstr    aObjectid// "objectid"
0x627d  stelem.ref
0x627e  dup
0x627f  ldc.i4.1
0x6280  ldstr    aQueueid// "queueid"
0x6285  stelem.ref
0x6286  stloc.0
0x6287  ldstr    aQueueitem// "queueitem"
0x628c  ldarg.1
0x628d  ldloc.0
0x628e  ldarg.0
0x628f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_OrganizationContext()
0x6294  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6299  ret
```
