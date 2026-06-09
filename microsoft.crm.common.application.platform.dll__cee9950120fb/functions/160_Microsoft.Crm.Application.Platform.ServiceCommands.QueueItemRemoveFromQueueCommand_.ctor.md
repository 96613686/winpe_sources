# Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemRemoveFromQueueCommand::.ctor

- ea: `0x160`
- end: `0x181`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemRemoveFromQueueCommand::.ctor`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3030`

## pseudocode

```c

```

## disassembly

```asm
0x160  ldarg.0
0x161  ldstr    aQueueitem// "queueitem"
0x166  ldarg.2
0x167  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16c  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RemoveFromQueueRequest::.ctor()
0x171  stloc.0
0x172  ldloc.0
0x173  ldarg.1
0x174  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RemoveFromQueueRequest::set_QueueItemId(valuetype [mscorlib]System.Guid)
0x179  ldarg.0
0x17a  ldloc.0
0x17b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x180  ret
```
