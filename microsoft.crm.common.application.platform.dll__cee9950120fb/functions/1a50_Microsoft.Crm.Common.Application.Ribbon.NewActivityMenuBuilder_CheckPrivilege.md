# Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::CheckPrivilege

- ea: `0x1a50`
- end: `0x1b06`
- name: `Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::CheckPrivilege`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1500`

## callees

- `0x1a50`

## pseudocode

```c

```

## disassembly

```asm
0x1a50  ldc.i4.1
0x1a51  stloc.0
0x1a52  ldloc.0
0x1a53  brfalse.s loc_1A65
0x1a55  ldarg.1
0x1a56  ldc.i4.s 0x20
0x1a58  ldarg.0
0x1a59  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1a5e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a63  br.s     loc_1A66
0x1a65  ldc.i4.0
0x1a66  stloc.0
0x1a67  ldloc.0
0x1a68  brfalse.s loc_1A79
0x1a6a  ldarg.1
0x1a6b  ldc.i4.1
0x1a6c  ldarg.0
0x1a6d  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1a72  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a77  br.s     loc_1A7A
0x1a79  ldc.i4.0
0x1a7a  stloc.0
0x1a7b  ldarg.1
0x1a7c  ldc.i4   0x1076
0x1a81  bne.un.s loc_1AB4
0x1a83  ldloc.0
0x1a84  brfalse.s loc_1A99
0x1a86  ldc.i4   0xFA1
0x1a8b  ldc.i4.1
0x1a8c  ldarg.0
0x1a8d  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1a92  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a97  br.s     loc_1A9A
0x1a99  ldc.i4.0
0x1a9a  stloc.0
0x1a9b  ldloc.0
0x1a9c  brfalse.s loc_1AB2
0x1a9e  ldc.i4   0xFA1
0x1aa3  ldc.i4.s 0x10
0x1aa5  ldarg.0
0x1aa6  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1aab  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ab0  br.s     loc_1AB3
0x1ab2  ldc.i4.0
0x1ab3  stloc.0
0x1ab4  ldarg.1
0x1ab5  ldc.i4   0x1131
0x1aba  bne.un.s loc_1B04
0x1abc  ldloc.0
0x1abd  brfalse.s loc_1AD2
0x1abf  ldc.i4   0x1068
0x1ac4  ldc.i4.4
0x1ac5  ldarg.0
0x1ac6  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1acb  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ad0  br.s     loc_1AD3
0x1ad2  ldc.i4.0
0x1ad3  stloc.0
0x1ad4  ldloc.0
0x1ad5  brfalse.s loc_1B02
0x1ad7  ldc.i4   0x1130
0x1adc  ldc.i4.s 0x10
0x1ade  ldarg.0
0x1adf  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1ae4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ae9  brtrue.s loc_1AFF
0x1aeb  ldc.i4   0x1068
0x1af0  ldc.i4.s 0x10
0x1af2  ldarg.0
0x1af3  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_Context()
0x1af8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1afd  br.s     loc_1B03
0x1aff  ldc.i4.1
0x1b00  br.s     loc_1B03
0x1b02  ldc.i4.0
0x1b03  stloc.0
0x1b04  ldloc.0
0x1b05  ret
```
