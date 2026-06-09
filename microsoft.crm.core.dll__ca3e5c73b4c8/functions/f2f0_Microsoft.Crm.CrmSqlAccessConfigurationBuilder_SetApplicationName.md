# Microsoft.Crm.CrmSqlAccessConfigurationBuilder::SetApplicationName

- ea: `0xf2f0`
- end: `0xf327`
- name: `Microsoft.Crm.CrmSqlAccessConfigurationBuilder::SetApplicationName`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf2b0`

## callees

- `0xf2f0`
- `0xf4d0`
- `0x100e0`

## string_xrefs

- `0xf303`: ` ReadOnlyRequested`
- `0xf314`: `GlobalOrg ReadOnlyRequested`

## pseudocode

```c

```

## disassembly

```asm
0xf2f0  call     string Microsoft.Crm.CrmSqlConnectionManagerFactory::get_ApplicationName()
0xf2f5  stloc.0
0xf2f6  ldarg.1
0xf2f7  brfalse.s loc_F31F
0xf2f9  ldloc.0
0xf2fa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf2ff  brtrue.s loc_F313
0xf301  ldarg.0
0xf302  ldloc.0
0xf303  ldstr    aReadonlyreques// " ReadOnlyRequested"
0xf308  call     string [mscorlib]System.String::Concat(string, string)
0xf30d  call     void Microsoft.Crm.CrmSqlAccessConfigurationBuilder::AddApplicationName(class [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder builder, string applicationName)
0xf312  ret
0xf313  ldarg.0
0xf314  ldstr    aGlobalorgReado// "GlobalOrg ReadOnlyRequested"
0xf319  call     void Microsoft.Crm.CrmSqlAccessConfigurationBuilder::AddApplicationName(class [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder builder, string applicationName)
0xf31e  ret
0xf31f  ldarg.0
0xf320  ldloc.0
0xf321  call     void Microsoft.Crm.CrmSqlAccessConfigurationBuilder::AddApplicationName(class [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder builder, string applicationName)
0xf326  ret
```
