# Microsoft.Crm.Tools.Admin.OrganizationInfo::set_ReportingGroup

- ea: `0x9090`
- end: `0x90a2`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::set_ReportingGroup`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9730`

## string_xrefs

- `0x9096`: `ServerInstallInfo.ReportingGroup`

## pseudocode

```c

```

## disassembly

```asm
0x9090  ldarg.0
0x9091  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x9096  ldstr    aServerinstalli_2// "ServerInstallInfo.ReportingGroup"
0x909b  ldarg.1
0x909c  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x90a1  ret
```
