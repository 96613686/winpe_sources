# <>c__DisplayClass22_0::<GetConfigStoreData>b__0

- ea: `0x92a0`
- end: `0x92b9`
- name: `<>c__DisplayClass22_0::<GetConfigStoreData>b__0`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x71c0`

## pseudocode

```c

```

## disassembly

```asm
0x92a0  ldarg.0
0x92a1  ldfld    class Microsoft.Crm.Sandbox.SandboxSdkListener <>c__DisplayClass22_0::<>4__this
0x92a6  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x92ab  ldarg.1
0x92ac  ldarg.2
0x92ad  ldarg.0
0x92ae  ldfld    string <>c__DisplayClass22_0::keyName
0x92b3  callvirt instance unsigned int8[] Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService::GetConfigStoreData(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, string keyName)
0x92b8  ret
```
