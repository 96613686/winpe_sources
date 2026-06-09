# <>c__DisplayClass24_0::<GetConfigStoreDataByKeyNames>b__0

- ea: `0x92e0`
- end: `0x92f9`
- name: `<>c__DisplayClass24_0::<GetConfigStoreDataByKeyNames>b__0`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x71e0`

## pseudocode

```c

```

## disassembly

```asm
0x92e0  ldarg.0
0x92e1  ldfld    class Microsoft.Crm.Sandbox.SandboxSdkListener <>c__DisplayClass24_0::<>4__this
0x92e6  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x92eb  ldarg.1
0x92ec  ldarg.2
0x92ed  ldarg.0
0x92ee  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass24_0::keyNames
0x92f3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService::GetConfigStoreDataByKeyNames(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [mscorlib]System.Collections.Generic.List`1<string> keyNames)
0x92f8  ret
```
