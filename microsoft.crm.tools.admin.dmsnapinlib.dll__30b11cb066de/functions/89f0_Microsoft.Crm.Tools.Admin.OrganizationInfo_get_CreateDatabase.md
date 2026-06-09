# Microsoft.Crm.Tools.Admin.OrganizationInfo::get_CreateDatabase

- ea: `0x89f0`
- end: `0x8a01`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::get_CreateDatabase`
- size: `17`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc600`
- `0xcab0`
- `0xcb90`
- `0xcc60`
- `0xcd20`
- `0xd220`

## string_xrefs

- `0x89f1`: `InstallInfo.CreateDatabase`

## pseudocode

```c

```

## disassembly

```asm
0x89f0  ldarg.0
0x89f1  ldstr    aInstallinfoCre// "InstallInfo.CreateDatabase"
0x89f6  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x89fb  unbox.any [mscorlib]System.Boolean
0x8a00  ret
```
