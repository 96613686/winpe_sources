# Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyMembersListCommand::.ctor

- ea: `0x6110`
- end: `0x6147`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyMembersListCommand::.ctor`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3080`

## pseudocode

```c

```

## disassembly

```asm
0x6110  ldarg.0
0x6111  ldstr    aList// "list"
0x6116  ldarg.s  4
0x6118  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x611d  ldarg.s  4
0x611f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6124  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyMemberListRequest::.ctor()
0x6129  stloc.0
0x612a  ldloc.0
0x612b  ldarg.1
0x612c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyMemberListRequest::set_ListId(valuetype [mscorlib]System.Guid)
0x6131  ldloc.0
0x6132  ldarg.2
0x6133  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyMemberListRequest::set_MembersId(valuetype [mscorlib]System.Guid[])
0x6138  ldloc.0
0x6139  ldarg.3
0x613a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QualifyMemberListRequest::set_OverrideorRemove(bool)
0x613f  ldarg.0
0x6140  ldloc.0
0x6141  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x6146  ret
```
