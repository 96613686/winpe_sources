# Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlAccessGroup

- ea: `0x9010`
- end: `0x9039`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlAccessGroup`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xdf10`
- `0x10e80`

## callees

- `0x9010`
- `0x9730`

## string_xrefs

- `0x9016`: `ServerInstallInfo.SqlAccessGroup`
- `0x9029`: `ServerInstallInfo.SqlAccessGroup`

## pseudocode

```c

```

## disassembly

```asm
0x9010  ldarg.0
0x9011  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x9016  ldstr    aServerinstalli_1// "ServerInstallInfo.SqlAccessGroup"
0x901b  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x9020  brtrue.s loc_9028
0x9022  ldarg.0
0x9023  call     instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::RetrieveGroups()
0x9028  ldarg.0
0x9029  ldstr    aServerinstalli_1// "ServerInstallInfo.SqlAccessGroup"
0x902e  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x9033  castclass [mscorlib]System.String
0x9038  ret
```
