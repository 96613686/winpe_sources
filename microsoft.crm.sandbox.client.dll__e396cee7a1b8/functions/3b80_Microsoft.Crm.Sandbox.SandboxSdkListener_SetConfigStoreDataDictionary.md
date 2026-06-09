# Microsoft.Crm.Sandbox.SandboxSdkListener::SetConfigStoreDataDictionary

- ea: `0x3b80`
- end: `0x3bce`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::SetConfigStoreDataDictionary`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x9250`

## string_xrefs

- `0x3b9a`: `_pluginSecureStoreService`
- `0x3bb6`: `SetConfigStoreData_Dictionary`

## pseudocode

```c

```

## disassembly

```asm
0x3b80  newobj   instance void <>c__DisplayClass21_0::.ctor()
0x3b85  stloc.0
0x3b86  ldloc.0
0x3b87  ldarg.0
0x3b88  stfld    class Microsoft.Crm.Sandbox.SandboxSdkListener <>c__DisplayClass21_0::<>4__this
0x3b8d  ldloc.0
0x3b8e  ldarg.2
0x3b8f  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass21_0::keyData
0x3b94  ldarg.0
0x3b95  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x3b9a  ldstr    aPluginsecurest_0// "_pluginSecureStoreService"
0x3b9f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3ba4  ldloc.0
0x3ba5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass21_0::keyData
0x3baa  ldstr    aKeydata// "keyData"
0x3baf  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3bb4  ldarg.0
0x3bb5  ldarg.1
0x3bb6  ldstr    aSetconfigstore_0// "SetConfigStoreData_Dictionary"
0x3bbb  ldloc.0
0x3bbc  ldftn    instance object <>c__DisplayClass21_0::<SetConfigStoreDataDictionary>b__0(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo delegateCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x3bc2  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, object>::.ctor(object, native int)
0x3bc7  call     T0x2B00000D
0x3bcc  pop
0x3bcd  ret
```
