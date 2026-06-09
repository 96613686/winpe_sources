# <>c__DisplayClass21_0::<SetConfigStoreDataDictionary>b__0

- ea: `0x9260`
- end: `0x927a`
- name: `<>c__DisplayClass21_0::<SetConfigStoreDataDictionary>b__0`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x71b0`

## pseudocode

```c

```

## disassembly

```asm
0x9260  ldarg.0
0x9261  ldfld    class Microsoft.Crm.Sandbox.SandboxSdkListener <>c__DisplayClass21_0::<>4__this
0x9266  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x926b  ldarg.1
0x926c  ldarg.2
0x926d  ldarg.0
0x926e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass21_0::keyData
0x9273  callvirt instance void Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService::SetConfigStoreData(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> keyData)
0x9278  ldnull
0x9279  ret
```
