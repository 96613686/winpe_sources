# Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfigurationFactory::UpdateThrottlingConfigWithOrganizationSettings

- ea: `0x2b640`
- end: `0x2b66a`
- name: `Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfigurationFactory::UpdateThrottlingConfigWithOrganizationSettings`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x2b570`

## callees

- `0x2a360`

## string_xrefs

- `0x2b64f`: `UpdateThrottlingConfigWithOrganizationSettings`
- `0x2b654`: `D:\a\1\s\src\Extensibility\Sdk\ODataV4\Throttling\ThrottlingConfigurationFactory.cs`

## pseudocode

```c

```

## disassembly

```asm
0x2b640  ldarg.1
0x2b641  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x2b646  ldarg.2
0x2b647  ldarg.0
0x2b648  ldfld    string Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfigurationFactory::orgConfigKey
0x2b64d  ldc.i4.s 0x42
0x2b64f  ldstr    aUpdatethrottli// "UpdateThrottlingConfigWithOrganizationS"...
0x2b654  ldstr    aDA1SSrcExtensi_3// "D:\\a\\1\\s\\src\\Extensibility\\Sdk\\O"...
0x2b659  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x2b65e  isinst   [mscorlib]System.String
0x2b663  ldarg.2
0x2b664  call     void Microsoft.Crm.Extensibility.ODataV4.Throttling.ConfigParser::ParseThrottlingConfigFromSettings(class Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration odataConfig, string settings, valuetype [mscorlib]System.Guid orgId)
0x2b669  ret
```
