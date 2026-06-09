# Microsoft.Crm.Tools.Admin.OrganizationInfo::set_UpgradeDatabase

- ea: `0x8a90`
- end: `0x8aa7`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::set_UpgradeDatabase`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x75f0`
- `0x16750`

## string_xrefs

- `0x8a96`: `InstallInfo.UpgradeDatabase`

## pseudocode

```c

```

## disassembly

```asm
0x8a90  ldarg.0
0x8a91  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x8a96  ldstr    aInstallinfoUpg// "InstallInfo.UpgradeDatabase"
0x8a9b  ldarg.1
0x8a9c  box      [mscorlib]System.Boolean
0x8aa1  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x8aa6  ret
```
