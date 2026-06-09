# <>c__DisplayClass12_0::<SetConfigStoreData>b__0

- ea: `0x9650`
- end: `0x9671`
- name: `<>c__DisplayClass12_0::<SetConfigStoreData>b__0`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c

```

## disassembly

```asm
0x9650  ldarg.0
0x9651  ldfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass12_0::<>4__this
0x9656  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_localConfigStoreServices
0x965b  ldarg.1
0x965c  ldarg.2
0x965d  ldarg.0
0x965e  ldfld    string <>c__DisplayClass12_0::keyName
0x9663  ldarg.0
0x9664  ldfld    unsigned int8[] <>c__DisplayClass12_0::data
0x9669  ldarg.3
0x966a  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices::SetData(string, string, string, unsigned int8[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x966f  ldnull
0x9670  ret
```
