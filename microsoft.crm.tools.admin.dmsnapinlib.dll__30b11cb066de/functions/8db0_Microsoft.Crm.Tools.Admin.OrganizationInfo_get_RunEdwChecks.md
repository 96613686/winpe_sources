# Microsoft.Crm.Tools.Admin.OrganizationInfo::get_RunEdwChecks

- ea: `0x8db0`
- end: `0x8dc7`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::get_RunEdwChecks`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x8db1`: `InstallInfo.RunEdwChecks`

## pseudocode

```c

```

## disassembly

```asm
0x8db0  ldarg.0
0x8db1  ldstr    aInstallinfoRun// "InstallInfo.RunEdwChecks"
0x8db6  ldc.i4.1
0x8db7  box      [mscorlib]System.Boolean
0x8dbc  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::Get(object, object)
0x8dc1  unbox.any [mscorlib]System.Boolean
0x8dc6  ret
```
