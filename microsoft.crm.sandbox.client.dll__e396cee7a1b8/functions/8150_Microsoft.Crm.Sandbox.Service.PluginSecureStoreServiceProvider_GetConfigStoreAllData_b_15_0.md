# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::<GetConfigStoreAllData>b__15_0

- ea: `0x8150`
- end: `0x815f`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::<GetConfigStoreAllData>b__15_0`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x8150  ldarg.0
0x8151  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_localConfigStoreServices
0x8156  ldarg.1
0x8157  ldarg.2
0x8158  ldarg.3
0x8159  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices::GetAllData(string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x815e  ret
```
