# Microsoft.Crm.Sandbox.SandboxSdkListener::SetConfigStoreData

- ea: `0x3b10`
- end: `0x3b75`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::SetConfigStoreData`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x9210`

## string_xrefs

- `0x3b31`: `_pluginSecureStoreService`
- `0x3b5d`: `SetConfigStoreData`

## pseudocode

```c

```

## disassembly

```asm
0x3b10  newobj   instance void <>c__DisplayClass20_0::.ctor()
0x3b15  stloc.0
0x3b16  ldloc.0
0x3b17  ldarg.0
0x3b18  stfld    class Microsoft.Crm.Sandbox.SandboxSdkListener <>c__DisplayClass20_0::<>4__this
0x3b1d  ldloc.0
0x3b1e  ldarg.2
0x3b1f  stfld    string <>c__DisplayClass20_0::keyName
0x3b24  ldloc.0
0x3b25  ldarg.3
0x3b26  stfld    unsigned int8[] <>c__DisplayClass20_0::data
0x3b2b  ldarg.0
0x3b2c  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x3b31  ldstr    aPluginsecurest_0// "_pluginSecureStoreService"
0x3b36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3b3b  ldloc.0
0x3b3c  ldfld    string <>c__DisplayClass20_0::keyName
0x3b41  ldstr    aKeyname// "keyName"
0x3b46  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3b4b  ldloc.0
0x3b4c  ldfld    unsigned int8[] <>c__DisplayClass20_0::data
0x3b51  ldstr    aData// "data"
0x3b56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3b5b  ldarg.0
0x3b5c  ldarg.1
0x3b5d  ldstr    aSetconfigstore// "SetConfigStoreData"
0x3b62  ldloc.0
0x3b63  ldftn    instance object <>c__DisplayClass20_0::<SetConfigStoreData>b__0(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo delegateCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x3b69  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, object>::.ctor(object, native int)
0x3b6e  call     T0x2B00000D
0x3b73  pop
0x3b74  ret
```
