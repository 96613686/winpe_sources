# Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMembersListCommand::.ctor

- ea: `0x58d0`
- end: `0x58fe`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMembersListCommand::.ctor`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3070`

## pseudocode

```c

```

## disassembly

```asm
0x58d0  ldarg.0
0x58d1  ldstr    aList// "list"
0x58d6  ldarg.3
0x58d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x58dc  ldarg.3
0x58dd  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x58e2  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddListMembersListRequest::.ctor()
0x58e7  stloc.0
0x58e8  ldloc.0
0x58e9  ldarg.1
0x58ea  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddListMembersListRequest::set_ListId(valuetype [mscorlib]System.Guid)
0x58ef  ldloc.0
0x58f0  ldarg.2
0x58f1  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AddListMembersListRequest::set_MemberIds(valuetype [mscorlib]System.Guid[])
0x58f6  ldarg.0
0x58f7  ldloc.0
0x58f8  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x58fd  ret
```
