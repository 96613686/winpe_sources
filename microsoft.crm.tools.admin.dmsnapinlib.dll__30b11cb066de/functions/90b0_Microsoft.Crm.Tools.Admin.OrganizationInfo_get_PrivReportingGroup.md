# Microsoft.Crm.Tools.Admin.OrganizationInfo::get_PrivReportingGroup

- ea: `0x90b0`
- end: `0x90d9`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::get_PrivReportingGroup`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xdf10`
- `0x10e80`

## callees

- `0x90b0`
- `0x9730`

## string_xrefs

- `0x90b6`: `ServerInstallInfo.PrivReportingGroup`
- `0x90c9`: `ServerInstallInfo.PrivReportingGroup`

## pseudocode

```c

```

## disassembly

```asm
0x90b0  ldarg.0
0x90b1  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x90b6  ldstr    aServerinstalli_3// "ServerInstallInfo.PrivReportingGroup"
0x90bb  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x90c0  brtrue.s loc_90C8
0x90c2  ldarg.0
0x90c3  call     instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::RetrieveGroups()
0x90c8  ldarg.0
0x90c9  ldstr    aServerinstalli_3// "ServerInstallInfo.PrivReportingGroup"
0x90ce  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x90d3  castclass [mscorlib]System.String
0x90d8  ret
```
