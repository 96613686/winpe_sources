# <>c__DisplayClass13_0::<SetConfigStoreData>b__0

- ea: `0x96a0`
- end: `0x96bb`
- name: `<>c__DisplayClass13_0::<SetConfigStoreData>b__0`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c

```

## disassembly

```asm
0x96a0  ldarg.0
0x96a1  ldfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass13_0::<>4__this
0x96a6  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_localConfigStoreServices
0x96ab  ldarg.1
0x96ac  ldarg.2
0x96ad  ldarg.0
0x96ae  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass13_0::keyData
0x96b3  ldarg.3
0x96b4  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices::SetData(string, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x96b9  ldnull
0x96ba  ret
```
