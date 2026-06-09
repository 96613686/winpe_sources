# Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemRouteToCommand::.ctor

- ea: `0x1b0`
- end: `0x1d8`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemRouteToCommand::.ctor`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3000`

## pseudocode

```c

```

## disassembly

```asm
0x1b0  ldarg.0
0x1b1  ldstr    aQueueitem// "queueitem"
0x1b6  ldarg.3
0x1b7  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1bc  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RouteToRequest::.ctor()
0x1c1  stloc.0
0x1c2  ldloc.0
0x1c3  ldarg.1
0x1c4  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RouteToRequest::set_QueueItemId(valuetype [mscorlib]System.Guid)
0x1c9  ldloc.0
0x1ca  ldarg.2
0x1cb  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RouteToRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x1d0  ldarg.0
0x1d1  ldloc.0
0x1d2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x1d7  ret
```
