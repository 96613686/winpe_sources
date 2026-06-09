# Microsoft.Crm.Tools.Admin.OrganizationOperation::SetOrgVersionInConfigDB

- ea: `0x9e60`
- end: `0x9e87`
- name: `Microsoft.Crm.Tools.Admin.OrganizationOperation::SetOrgVersionInConfigDB`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14d30`

## callees

- `0x110c0`

## string_xrefs

- `0x9e60`: `Setting Org version in config database`
- `0x9e76`: `Org version successfully set in config database`

## pseudocode

```c

```

## disassembly

```asm
0x9e60  ldstr    aSettingOrgVers// "Setting Org version in config database"
0x9e65  ldc.i4.0
0x9e66  newarr   [mscorlib]System.Object
0x9e6b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x9e70  ldarg.0
0x9e71  call     void Microsoft.Crm.Tools.Admin.SetOrgVersionInConfigDBAction::SetOrgVersionInConfigDB(valuetype [mscorlib]System.Guid organizationId)
0x9e76  ldstr    aOrgVersionSucc// "Org version successfully set in config "...
0x9e7b  ldc.i4.0
0x9e7c  newarr   [mscorlib]System.Object
0x9e81  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x9e86  ret
```
