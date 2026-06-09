# Microsoft.Crm.Tools.Admin.OrganizationInfo::get_UpgradeDatabase

- ea: `0x8a70`
- end: `0x8a87`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::get_UpgradeDatabase`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd220`

## string_xrefs

- `0x8a71`: `InstallInfo.UpgradeDatabase`

## pseudocode

```c

```

## disassembly

```asm
0x8a70  ldarg.0
0x8a71  ldstr    aInstallinfoUpg// "InstallInfo.UpgradeDatabase"
0x8a76  ldc.i4.0
0x8a77  box      [mscorlib]System.Boolean
0x8a7c  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::Get(object, object)
0x8a81  unbox.any [mscorlib]System.Boolean
0x8a86  ret
```
