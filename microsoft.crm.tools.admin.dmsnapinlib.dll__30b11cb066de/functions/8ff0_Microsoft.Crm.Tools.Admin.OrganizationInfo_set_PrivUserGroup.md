# Microsoft.Crm.Tools.Admin.OrganizationInfo::set_PrivUserGroup

- ea: `0x8ff0`
- end: `0x9002`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::set_PrivUserGroup`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9730`

## string_xrefs

- `0x8ff6`: `ServerInstallInfo.PrivUserGroup`

## pseudocode

```c

```

## disassembly

```asm
0x8ff0  ldarg.0
0x8ff1  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x8ff6  ldstr    aServerinstalli_0// "ServerInstallInfo.PrivUserGroup"
0x8ffb  ldarg.1
0x8ffc  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x9001  ret
```
