# Microsoft.Crm.Sandbox.SandboxSdkListener::GetSecret

- ea: `0x3a00`
- end: `0x3a4d`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::GetSecret`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x9190`

## string_xrefs

- `0x3a1a`: `_pluginSecureStoreService`

## pseudocode

```c

```

## disassembly

```asm
0x3a00  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x3a05  stloc.0
0x3a06  ldloc.0
0x3a07  ldarg.0
0x3a08  stfld    class Microsoft.Crm.Sandbox.SandboxSdkListener <>c__DisplayClass16_0::<>4__this
0x3a0d  ldloc.0
0x3a0e  ldarg.2
0x3a0f  stfld    string <>c__DisplayClass16_0::secretName
0x3a14  ldarg.0
0x3a15  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x3a1a  ldstr    aPluginsecurest_0// "_pluginSecureStoreService"
0x3a1f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3a24  ldloc.0
0x3a25  ldfld    string <>c__DisplayClass16_0::secretName
0x3a2a  ldstr    aSecretname// "secretName"
0x3a2f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3a34  ldarg.0
0x3a35  ldarg.1
0x3a36  ldstr    aGetsecret// "GetSecret"
0x3a3b  ldloc.0
0x3a3c  ldftn    instance string <>c__DisplayClass16_0::<GetSecret>b__0(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo delegateCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x3a42  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, string>::.ctor(object, native int)
0x3a47  call     T0x2B00000C
0x3a4c  ret
```
