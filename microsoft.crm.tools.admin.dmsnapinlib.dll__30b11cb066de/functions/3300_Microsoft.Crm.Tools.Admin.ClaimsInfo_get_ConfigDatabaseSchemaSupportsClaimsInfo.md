# Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ConfigDatabaseSchemaSupportsClaimsInfo

- ea: `0x3300`
- end: `0x3317`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ConfigDatabaseSchemaSupportsClaimsInfo`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x3301`: `ClaimsInfo.ConfigDatabaseSchemaSupportsClaimsInfo`

## pseudocode

```c

```

## disassembly

```asm
0x3300  ldarg.0
0x3301  ldstr    aClaimsinfoConf// "ClaimsInfo.ConfigDatabaseSchemaSupports"...
0x3306  ldc.i4.1
0x3307  box      [mscorlib]System.Boolean
0x330c  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::Get(object, object)
0x3311  unbox.any [mscorlib]System.Boolean
0x3316  ret
```
