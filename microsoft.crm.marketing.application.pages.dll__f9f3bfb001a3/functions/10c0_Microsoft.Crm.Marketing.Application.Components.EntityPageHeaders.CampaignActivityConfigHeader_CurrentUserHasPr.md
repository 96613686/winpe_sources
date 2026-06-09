# Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::CurrentUserHasPrivilege

- ea: `0x10c0`
- end: `0x10cc`
- name: `Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::CurrentUserHasPrivilege`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0xf10`

## pseudocode

```c

```

## disassembly

```asm
0x10c0  ldarg.0
0x10c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10c6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10cb  ret
```
