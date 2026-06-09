# Microsoft.Crm.Sandbox.SandboxSdkListener::GetConfigStoreAllData

- ea: `0x3c20`
- end: `0x3c49`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::GetConfigStoreAllData`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x3c26`: `_pluginSecureStoreService`
- `0x3c32`: `GetConfigStoreAllData`

## pseudocode

```c

```

## disassembly

```asm
0x3c20  ldarg.0
0x3c21  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x3c26  ldstr    aPluginsecurest_0// "_pluginSecureStoreService"
0x3c2b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3c30  ldarg.0
0x3c31  ldarg.1
0x3c32  ldstr    aGetconfigstore_0// "GetConfigStoreAllData"
0x3c37  ldarg.0
0x3c38  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> Microsoft.Crm.Sandbox.SandboxSdkListener::<GetConfigStoreAllData>b__23_0(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo delegateCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x3c3e  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>>::.ctor(object, native int)
0x3c43  call     T0x2B000010
0x3c48  ret
```
