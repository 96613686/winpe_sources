# Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::UpdateHttpConfigWithDeploymentSettings

- ea: `0x5f20`
- end: `0x5f3b`
- name: `Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::UpdateHttpConfigWithDeploymentSettings`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x5e90`

## callees

- `0x5f70`

## pseudocode

```c

```

## disassembly

```asm
0x5f20  ldarg.0
0x5f21  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x5f26  ldstr    aWebhookendpoin// "WebhookEndpointSettings"
0x5f2b  ldsfld   string [mscorlib]System.String::Empty
0x5f30  callvirt T0x2B000008
0x5f35  call     void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::UpdateHttpConfigFromXmlSettings(class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig httpRequestConfig, string xmlString)
0x5f3a  ret
```
