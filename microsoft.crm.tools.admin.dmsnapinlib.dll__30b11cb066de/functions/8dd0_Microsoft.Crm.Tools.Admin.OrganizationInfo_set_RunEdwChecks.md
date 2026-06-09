# Microsoft.Crm.Tools.Admin.OrganizationInfo::set_RunEdwChecks

- ea: `0x8dd0`
- end: `0x8de7`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::set_RunEdwChecks`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x8dd6`: `InstallInfo.RunEdwChecks`

## pseudocode

```c

```

## disassembly

```asm
0x8dd0  ldarg.0
0x8dd1  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x8dd6  ldstr    aInstallinfoRun// "InstallInfo.RunEdwChecks"
0x8ddb  ldarg.1
0x8ddc  box      [mscorlib]System.Boolean
0x8de1  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x8de6  ret
```
