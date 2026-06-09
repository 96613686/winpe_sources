# Microsoft.Crm.Tools.Admin.OrganizationInfo::get_UpgradeType

- ea: `0x8e70`
- end: `0x8e87`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::get_UpgradeType`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x92d0`
- `0xd700`

## string_xrefs

- `0x8e71`: `ServerInstallInfo.UpgradeType`

## pseudocode

```c

```

## disassembly

```asm
0x8e70  ldarg.0
0x8e71  ldstr    aServerinstalli// "ServerInstallInfo.UpgradeType"
0x8e76  ldc.i4.0
0x8e77  box      [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.UpgradeType
0x8e7c  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::Get(object, object)
0x8e81  unbox.any [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.UpgradeType
0x8e86  ret
```
