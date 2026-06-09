# Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMemberListCommand::.ctor

- ea: `0x5800`
- end: `0x582e`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMemberListCommand::.ctor`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3060`

## pseudocode

```c

```

## disassembly

```asm
0x5800  ldarg.0
0x5801  ldstr    aList// "list"
0x5806  ldarg.3
0x5807  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x580c  ldarg.3
0x580d  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5812  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddMemberListRequest::.ctor()
0x5817  stloc.0
0x5818  ldloc.0
0x5819  ldarg.1
0x581a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddMemberListRequest::set_ListId(valuetype [mscorlib]System.Guid)
0x581f  ldloc.0
0x5820  ldarg.2
0x5821  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddMemberListRequest::set_EntityId(valuetype [mscorlib]System.Guid)
0x5826  ldarg.0
0x5827  ldloc.0
0x5828  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x582d  ret
```
