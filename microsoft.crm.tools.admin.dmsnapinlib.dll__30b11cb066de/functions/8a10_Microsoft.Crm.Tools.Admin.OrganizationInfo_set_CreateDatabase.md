# Microsoft.Crm.Tools.Admin.OrganizationInfo::set_CreateDatabase

- ea: `0x8a10`
- end: `0x8a27`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::set_CreateDatabase`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x12170`
- `0x16750`

## string_xrefs

- `0x8a16`: `InstallInfo.CreateDatabase`

## pseudocode

```c

```

## disassembly

```asm
0x8a10  ldarg.0
0x8a11  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x8a16  ldstr    aInstallinfoCre// "InstallInfo.CreateDatabase"
0x8a1b  ldarg.1
0x8a1c  box      [mscorlib]System.Boolean
0x8a21  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x8a26  ret
```
