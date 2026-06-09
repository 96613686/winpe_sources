# Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemReleaseToQueueCommand::.ctor

- ea: `0x110`
- end: `0x131`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemReleaseToQueueCommand::.ctor`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3020`

## pseudocode

```c

```

## disassembly

```asm
0x110  ldarg.0
0x111  ldstr    aQueueitem// "queueitem"
0x116  ldarg.2
0x117  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11c  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ReleaseToQueueRequest::.ctor()
0x121  stloc.0
0x122  ldloc.0
0x123  ldarg.1
0x124  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ReleaseToQueueRequest::set_QueueItemId(valuetype [mscorlib]System.Guid)
0x129  ldarg.0
0x12a  ldloc.0
0x12b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x130  ret
```
