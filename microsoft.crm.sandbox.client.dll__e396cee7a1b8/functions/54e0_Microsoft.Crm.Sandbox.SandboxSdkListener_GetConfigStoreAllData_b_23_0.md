# Microsoft.Crm.Sandbox.SandboxSdkListener::<GetConfigStoreAllData>b__23_0

- ea: `0x54e0`
- end: `0x54ee`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::<GetConfigStoreAllData>b__23_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x71d0`

## pseudocode

```c

```

## disassembly

```asm
0x54e0  ldarg.0
0x54e1  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x54e6  ldarg.1
0x54e7  ldarg.2
0x54e8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService::GetConfigStoreAllData(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x54ed  ret
```
