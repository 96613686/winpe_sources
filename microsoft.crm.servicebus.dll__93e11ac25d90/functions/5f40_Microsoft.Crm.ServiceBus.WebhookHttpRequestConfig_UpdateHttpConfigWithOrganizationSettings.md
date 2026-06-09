# Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::UpdateHttpConfigWithOrganizationSettings

- ea: `0x5f40`
- end: `0x5f68`
- name: `Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::UpdateHttpConfigWithOrganizationSettings`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x5e90`

## callees

- `0x5f70`

## string_xrefs

- `0x5f4e`: `UpdateHttpConfigWithOrganizationSettings`
- `0x5f53`: `D:\a\1\s\src\Shared\ServiceBus\Webhooks\WebhookHttpRequestConfig.cs`

## pseudocode

```c

```

## disassembly

```asm
0x5f40  ldarg.0
0x5f41  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x5f46  ldarg.1
0x5f47  ldstr    aOrgwebhookendp// "OrgWebhookEndpointSettings"
0x5f4c  ldc.i4.s 0x4B
0x5f4e  ldstr    aUpdatehttpconf// "UpdateHttpConfigWithOrganizationSetting"...
0x5f53  ldstr    aDA1SSrcSharedS_0// "D:\\a\\1\\s\\src\\Shared\\ServiceBus\\W"...
0x5f58  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x5f5d  isinst   [mscorlib]System.String
0x5f62  call     void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::UpdateHttpConfigFromXmlSettings(class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig httpRequestConfig, string xmlString)
0x5f67  ret
```
