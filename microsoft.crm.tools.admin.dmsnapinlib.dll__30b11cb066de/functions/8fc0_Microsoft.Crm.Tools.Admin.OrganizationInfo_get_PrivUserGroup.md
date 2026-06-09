# Microsoft.Crm.Tools.Admin.OrganizationInfo::get_PrivUserGroup

- ea: `0x8fc0`
- end: `0x8fe9`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::get_PrivUserGroup`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xdf10`

## callees

- `0x8fc0`
- `0x9730`

## string_xrefs

- `0x8fc6`: `ServerInstallInfo.PrivUserGroup`
- `0x8fd9`: `ServerInstallInfo.PrivUserGroup`

## pseudocode

```c

```

## disassembly

```asm
0x8fc0  ldarg.0
0x8fc1  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x8fc6  ldstr    aServerinstalli_0// "ServerInstallInfo.PrivUserGroup"
0x8fcb  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x8fd0  brtrue.s loc_8FD8
0x8fd2  ldarg.0
0x8fd3  call     instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::RetrieveGroups()
0x8fd8  ldarg.0
0x8fd9  ldstr    aServerinstalli_0// "ServerInstallInfo.PrivUserGroup"
0x8fde  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x8fe3  castclass [mscorlib]System.String
0x8fe8  ret
```
