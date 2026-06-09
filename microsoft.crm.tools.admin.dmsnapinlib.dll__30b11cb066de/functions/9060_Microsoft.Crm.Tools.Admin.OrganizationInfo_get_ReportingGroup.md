# Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingGroup

- ea: `0x9060`
- end: `0x9089`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingGroup`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xdf10`
- `0x10e80`

## callees

- `0x9060`
- `0x9730`

## string_xrefs

- `0x9066`: `ServerInstallInfo.ReportingGroup`
- `0x9079`: `ServerInstallInfo.ReportingGroup`

## pseudocode

```c

```

## disassembly

```asm
0x9060  ldarg.0
0x9061  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x9066  ldstr    aServerinstalli_2// "ServerInstallInfo.ReportingGroup"
0x906b  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x9070  brtrue.s loc_9078
0x9072  ldarg.0
0x9073  call     instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::RetrieveGroups()
0x9078  ldarg.0
0x9079  ldstr    aServerinstalli_2// "ServerInstallInfo.ReportingGroup"
0x907e  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x9083  castclass [mscorlib]System.String
0x9088  ret
```
