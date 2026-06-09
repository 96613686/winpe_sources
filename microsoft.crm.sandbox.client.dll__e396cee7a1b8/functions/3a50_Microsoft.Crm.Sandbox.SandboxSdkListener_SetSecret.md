# Microsoft.Crm.Sandbox.SandboxSdkListener::SetSecret

- ea: `0x3a50`
- end: `0x3aa5`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::SetSecret`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x91d0`

## string_xrefs

- `0x3a71`: `_pluginSecureStoreService`

## pseudocode

```c

```

## disassembly

```asm
0x3a50  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x3a55  stloc.0
0x3a56  ldloc.0
0x3a57  ldarg.0
0x3a58  stfld    class Microsoft.Crm.Sandbox.SandboxSdkListener <>c__DisplayClass17_0::<>4__this
0x3a5d  ldloc.0
0x3a5e  ldarg.2
0x3a5f  stfld    string <>c__DisplayClass17_0::secretName
0x3a64  ldloc.0
0x3a65  ldarg.3
0x3a66  stfld    string <>c__DisplayClass17_0::secretValue
0x3a6b  ldarg.0
0x3a6c  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x3a71  ldstr    aPluginsecurest_0// "_pluginSecureStoreService"
0x3a76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3a7b  ldloc.0
0x3a7c  ldfld    string <>c__DisplayClass17_0::secretName
0x3a81  ldstr    aSecretname// "secretName"
0x3a86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3a8b  ldarg.0
0x3a8c  ldarg.1
0x3a8d  ldstr    aSetsecret// "SetSecret"
0x3a92  ldloc.0
0x3a93  ldftn    instance object <>c__DisplayClass17_0::<SetSecret>b__0(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo delegateCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x3a99  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, object>::.ctor(object, native int)
0x3a9e  call     T0x2B00000D
0x3aa3  pop
0x3aa4  ret
```
