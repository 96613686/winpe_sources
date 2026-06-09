# Microsoft.Crm.Application.Platform.ServiceCommands.AddUserToQueueCommand::.ctor

- ea: `0x70`
- end: `0x9d`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.AddUserToQueueCommand::.ctor`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3040`

## pseudocode

```c

```

## disassembly

```asm
0x70  ldarg.0
0x71  ldstr    aQueue// "queue"
0x76  ldarg.3
0x77  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7c  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddPrincipalToQueueRequest::.ctor()
0x81  stloc.0
0x82  ldloc.0
0x83  ldarg.1
0x84  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddPrincipalToQueueRequest::set_QueueId(valuetype [mscorlib]System.Guid)
0x89  ldloc.0
0x8a  ldarg.2
0x8b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x90  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddPrincipalToQueueRequest::set_Principal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x95  ldarg.0
0x96  ldloc.0
0x97  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x9c  ret
```
