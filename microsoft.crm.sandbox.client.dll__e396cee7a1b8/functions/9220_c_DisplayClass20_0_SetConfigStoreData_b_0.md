# <>c__DisplayClass20_0::<SetConfigStoreData>b__0

- ea: `0x9220`
- end: `0x9240`
- name: `<>c__DisplayClass20_0::<SetConfigStoreData>b__0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x71a0`

## pseudocode

```c

```

## disassembly

```asm
0x9220  ldarg.0
0x9221  ldfld    class Microsoft.Crm.Sandbox.SandboxSdkListener <>c__DisplayClass20_0::<>4__this
0x9226  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x922b  ldarg.1
0x922c  ldarg.2
0x922d  ldarg.0
0x922e  ldfld    string <>c__DisplayClass20_0::keyName
0x9233  ldarg.0
0x9234  ldfld    unsigned int8[] <>c__DisplayClass20_0::data
0x9239  callvirt instance void Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService::SetConfigStoreData(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, string keyName, unsigned int8[] data)
0x923e  ldnull
0x923f  ret
```
