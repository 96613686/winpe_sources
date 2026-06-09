# Microsoft.Crm.CrmSqlAcccessTimeoutConfig::GetOrganizationCommandTimeoutOrInvalidValueInSecond

- ea: `0xf9a0`
- end: `0xf9c9`
- name: `Microsoft.Crm.CrmSqlAcccessTimeoutConfig::GetOrganizationCommandTimeoutOrInvalidValueInSecond`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xdc30`
- `0xf900`

## callees

- `0x1010`
- `0x1470`
- `0xf9a0`

## string_xrefs

- `0xf9a6`: `SqlCommandTimeout`
- `0xf9ad`: `GetOrganizationCommandTimeoutOrInvalidValueInSecond`
- `0xf9b2`: `D:\a\1\s\src\Platform\Core\DataServices\Connection\CrmSqlAcccessTimeoutConfig.cs`

## pseudocode

```c

```

## disassembly

```asm
0xf9a0  call     class Microsoft.Crm.IOrganizationSettingsProvider Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xf9a5  ldarg.0
0xf9a6  ldstr    aSqlcommandtime// "SqlCommandTimeout"
0xf9ab  ldc.i4.s 0x7F
0xf9ad  ldstr    aGetorganizatio_11// "GetOrganizationCommandTimeoutOrInvalidV"...
0xf9b2  ldstr    aDA1SSrcPlatfor_7// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xf9b7  callvirt instance object Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid organizationId, string settingName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xf9bc  stloc.0
0xf9bd  ldloc.0
0xf9be  brfalse.s loc_F9C7
0xf9c0  ldloc.0
0xf9c1  unbox.any [mscorlib]System.Int32
0xf9c6  ret
0xf9c7  ldc.i4.m1
0xf9c8  ret
```
