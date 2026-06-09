# Microsoft.Crm.Tools.Admin.OrganizationInfo::set_SqmOptIn

- ea: `0x8d90`
- end: `0x8da7`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::set_SqmOptIn`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x8d96`: `InstallInfo.SqmOptIn`

## pseudocode

```c

```

## disassembly

```asm
0x8d90  ldarg.0
0x8d91  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x8d96  ldstr    aInstallinfoSqm// "InstallInfo.SqmOptIn"
0x8d9b  ldarg.1
0x8d9c  box      [mscorlib]System.Boolean
0x8da1  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x8da6  ret
```
