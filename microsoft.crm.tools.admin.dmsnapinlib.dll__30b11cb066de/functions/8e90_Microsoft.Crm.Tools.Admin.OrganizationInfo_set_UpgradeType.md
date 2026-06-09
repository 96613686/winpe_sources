# Microsoft.Crm.Tools.Admin.OrganizationInfo::set_UpgradeType

- ea: `0x8e90`
- end: `0x8ea7`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::set_UpgradeType`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x169a0`

## string_xrefs

- `0x8e96`: `ServerInstallInfo.UpgradeType`

## pseudocode

```c

```

## disassembly

```asm
0x8e90  ldarg.0
0x8e91  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x8e96  ldstr    aServerinstalli// "ServerInstallInfo.UpgradeType"
0x8e9b  ldarg.1
0x8e9c  box      [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.UpgradeType
0x8ea1  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x8ea6  ret
```
