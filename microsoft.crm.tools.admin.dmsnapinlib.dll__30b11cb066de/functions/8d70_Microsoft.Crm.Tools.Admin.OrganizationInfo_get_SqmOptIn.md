# Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqmOptIn

- ea: `0x8d70`
- end: `0x8d87`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqmOptIn`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10880`

## string_xrefs

- `0x8d71`: `InstallInfo.SqmOptIn`

## pseudocode

```c

```

## disassembly

```asm
0x8d70  ldarg.0
0x8d71  ldstr    aInstallinfoSqm// "InstallInfo.SqmOptIn"
0x8d76  ldc.i4.0
0x8d77  box      [mscorlib]System.Boolean
0x8d7c  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::Get(object, object)
0x8d81  unbox.any [mscorlib]System.Boolean
0x8d86  ret
```
