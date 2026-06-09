# Microsoft.Crm.Application.Platform.ServiceCommands.RetrievePrivilegeMaxDepthFromTeamRolesCommand::.ctor

- ea: `0x952f0`
- end: `0x95326`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.RetrievePrivilegeMaxDepthFromTeamRolesCommand::.ctor`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x152b0`

## callees

- `0x6a810`
- `0x90d10`
- `0x90e40`

## string_xrefs

- `0x952f1`: `privilege`
- `0x95302`: `RetrievePrivilegeMaxDepthFromTeamRoles`

## pseudocode

```c

```

## disassembly

```asm
0x952f0  ldarg.0
0x952f1  ldstr    aPrivilege_0// "privilege"
0x952f6  ldarg.2
0x952f7  call     class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityType::Create(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x952fc  ldarg.2
0x952fd  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class Microsoft.Crm.Application.Platform.EntityType entityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x95302  ldstr    aRetrieveprivil// "RetrievePrivilegeMaxDepthFromTeamRoles"
0x95307  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor(string)
0x9530c  stloc.0
0x9530d  ldloc.0
0x9530e  ldstr    aUserid// "UserId"
0x95313  ldarg.1
0x95314  box      [mscorlib]System.Guid
0x95319  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x9531e  ldarg.0
0x9531f  ldloc.0
0x95320  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest value)
0x95325  ret
```
