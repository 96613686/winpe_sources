# Microsoft.Crm.Common.Application.Platform.ServiceCommands.CopyMembersListCommand::.ctor

- ea: `0x5ac0`
- end: `0x5aee`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.CopyMembersListCommand::.ctor`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fb0`

## pseudocode

```c

```

## disassembly

```asm
0x5ac0  ldarg.0
0x5ac1  ldstr    aList// "list"
0x5ac6  ldarg.3
0x5ac7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5acc  ldarg.3
0x5acd  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5ad2  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CopyMembersListRequest::.ctor()
0x5ad7  stloc.0
0x5ad8  ldloc.0
0x5ad9  ldarg.1
0x5ada  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CopyMembersListRequest::set_SourceListId(valuetype [mscorlib]System.Guid)
0x5adf  ldloc.0
0x5ae0  ldarg.2
0x5ae1  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CopyMembersListRequest::set_TargetListId(valuetype [mscorlib]System.Guid)
0x5ae6  ldarg.0
0x5ae7  ldloc.0
0x5ae8  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x5aed  ret
```
