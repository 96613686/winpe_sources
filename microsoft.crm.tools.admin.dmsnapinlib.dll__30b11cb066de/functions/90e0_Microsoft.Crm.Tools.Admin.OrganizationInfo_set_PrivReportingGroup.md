# Microsoft.Crm.Tools.Admin.OrganizationInfo::set_PrivReportingGroup

- ea: `0x90e0`
- end: `0x90f2`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::set_PrivReportingGroup`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9730`

## string_xrefs

- `0x90e6`: `ServerInstallInfo.PrivReportingGroup`

## pseudocode

```c

```

## disassembly

```asm
0x90e0  ldarg.0
0x90e1  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x90e6  ldstr    aServerinstalli_3// "ServerInstallInfo.PrivReportingGroup"
0x90eb  ldarg.1
0x90ec  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x90f1  ret
```
