# Microsoft.Crm.Sandbox.SandboxSdkListener::GetConfigStoreDataByKeyNames

- ea: `0x3c50`
- end: `0x3c9d`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::GetConfigStoreDataByKeyNames`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x92d0`

## string_xrefs

- `0x3c6a`: `_pluginSecureStoreService`
- `0x3c86`: `GetConfigStoreDataByKeyNames`

## pseudocode

```c

```

## disassembly

```asm
0x3c50  newobj   instance void <>c__DisplayClass24_0::.ctor()
0x3c55  stloc.0
0x3c56  ldloc.0
0x3c57  ldarg.0
0x3c58  stfld    class Microsoft.Crm.Sandbox.SandboxSdkListener <>c__DisplayClass24_0::<>4__this
0x3c5d  ldloc.0
0x3c5e  ldarg.2
0x3c5f  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass24_0::keyNames
0x3c64  ldarg.0
0x3c65  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x3c6a  ldstr    aPluginsecurest_0// "_pluginSecureStoreService"
0x3c6f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3c74  ldloc.0
0x3c75  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass24_0::keyNames
0x3c7a  ldstr    aKeynames// "keyNames"
0x3c7f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3c84  ldarg.0
0x3c85  ldarg.1
0x3c86  ldstr    aGetconfigstore_1// "GetConfigStoreDataByKeyNames"
0x3c8b  ldloc.0
0x3c8c  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass24_0::<GetConfigStoreDataByKeyNames>b__0(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo delegateCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x3c92  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>>::.ctor(object, native int)
0x3c97  call     T0x2B000010
0x3c9c  ret
```
