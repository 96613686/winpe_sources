# Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemPickCommand::.ctor

- ea: `0xc0`
- end: `0xf0`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemPickCommand::.ctor`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3010`

## pseudocode

```c

```

## disassembly

```asm
0xc0  ldarg.0
0xc1  ldstr    aQueueitem// "queueitem"
0xc6  ldarg.s  4
0xc8  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcd  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.PickFromQueueRequest::.ctor()
0xd2  stloc.0
0xd3  ldloc.0
0xd4  ldarg.1
0xd5  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.PickFromQueueRequest::set_QueueItemId(valuetype [mscorlib]System.Guid)
0xda  ldloc.0
0xdb  ldarg.2
0xdc  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.PickFromQueueRequest::set_WorkerId(valuetype [mscorlib]System.Guid)
0xe1  ldloc.0
0xe2  ldarg.3
0xe3  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.PickFromQueueRequest::set_RemoveQueueItem(bool)
0xe8  ldarg.0
0xe9  ldloc.0
0xea  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xef  ret
```
