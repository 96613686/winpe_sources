# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::CheckPrivileges

- ea: `0x4120`
- end: `0x4143`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::CheckPrivileges`
- size: `35`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x3450`
- `0x37d0`
- `0x3880`

## callees

- `0x4120`

## pseudocode

```c

```

## disassembly

```asm
0x4120  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteEntity()
0x4125  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x412a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x412f  brtrue.s loc_4142
0x4131  ldc.i4   0x80040277
0x4136  ldc.i4.0
0x4137  newarr   [mscorlib]System.Object
0x413c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x4141  throw
0x4142  ret
```
