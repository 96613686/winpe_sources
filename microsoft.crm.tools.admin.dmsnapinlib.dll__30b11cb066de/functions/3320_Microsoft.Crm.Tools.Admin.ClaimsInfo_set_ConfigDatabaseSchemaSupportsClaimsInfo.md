# Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ConfigDatabaseSchemaSupportsClaimsInfo

- ea: `0x3320`
- end: `0x3337`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ConfigDatabaseSchemaSupportsClaimsInfo`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x3326`: `ClaimsInfo.ConfigDatabaseSchemaSupportsClaimsInfo`

## pseudocode

```c

```

## disassembly

```asm
0x3320  ldarg.0
0x3321  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x3326  ldstr    aClaimsinfoConf// "ClaimsInfo.ConfigDatabaseSchemaSupports"...
0x332b  ldarg.1
0x332c  box      [mscorlib]System.Boolean
0x3331  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3336  ret
```
