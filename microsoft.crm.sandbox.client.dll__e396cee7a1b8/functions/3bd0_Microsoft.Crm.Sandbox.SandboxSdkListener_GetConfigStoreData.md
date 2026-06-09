# Microsoft.Crm.Sandbox.SandboxSdkListener::GetConfigStoreData

- ea: `0x3bd0`
- end: `0x3c1d`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::GetConfigStoreData`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x9290`

## string_xrefs

- `0x3bea`: `_pluginSecureStoreService`
- `0x3c06`: `GetConfigStoreData`

## pseudocode

```c

```

## disassembly

```asm
0x3bd0  newobj   instance void <>c__DisplayClass22_0::.ctor()
0x3bd5  stloc.0
0x3bd6  ldloc.0
0x3bd7  ldarg.0
0x3bd8  stfld    class Microsoft.Crm.Sandbox.SandboxSdkListener <>c__DisplayClass22_0::<>4__this
0x3bdd  ldloc.0
0x3bde  ldarg.2
0x3bdf  stfld    string <>c__DisplayClass22_0::keyName
0x3be4  ldarg.0
0x3be5  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x3bea  ldstr    aPluginsecurest_0// "_pluginSecureStoreService"
0x3bef  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3bf4  ldloc.0
0x3bf5  ldfld    string <>c__DisplayClass22_0::keyName
0x3bfa  ldstr    aKeyname// "keyName"
0x3bff  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3c04  ldarg.0
0x3c05  ldarg.1
0x3c06  ldstr    aGetconfigstore// "GetConfigStoreData"
0x3c0b  ldloc.0
0x3c0c  ldftn    instance unsigned int8[] <>c__DisplayClass22_0::<GetConfigStoreData>b__0(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo delegateCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x3c12  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, unsigned int8[]>::.ctor(object, native int)
0x3c17  call     T0x2B00000B
0x3c1c  ret
```
