# <>c__DisplayClass16_0::<GetConfigStoreDataByKeyNames>b__0

- ea: `0x9720`
- end: `0x973a`
- name: `<>c__DisplayClass16_0::<GetConfigStoreDataByKeyNames>b__0`
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
0x9720  ldarg.0
0x9721  ldfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass16_0::<>4__this
0x9726  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_localConfigStoreServices
0x972b  ldarg.1
0x972c  ldarg.2
0x972d  ldarg.0
0x972e  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass16_0::keyNames
0x9733  ldarg.3
0x9734  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices::GetDataByKeyNames(string, string, class [mscorlib]System.Collections.Generic.List`1<string>, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9739  ret
```
