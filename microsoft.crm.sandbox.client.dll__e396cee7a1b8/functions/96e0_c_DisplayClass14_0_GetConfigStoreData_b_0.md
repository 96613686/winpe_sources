# <>c__DisplayClass14_0::<GetConfigStoreData>b__0

- ea: `0x96e0`
- end: `0x96fa`
- name: `<>c__DisplayClass14_0::<GetConfigStoreData>b__0`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c

```

## disassembly

```asm
0x96e0  ldarg.0
0x96e1  ldfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass14_0::<>4__this
0x96e6  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_localConfigStoreServices
0x96eb  ldarg.1
0x96ec  ldarg.2
0x96ed  ldarg.0
0x96ee  ldfld    string <>c__DisplayClass14_0::keyName
0x96f3  ldarg.3
0x96f4  callvirt instance unsigned int8[] [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices::GetData(string, string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x96f9  ret
```
