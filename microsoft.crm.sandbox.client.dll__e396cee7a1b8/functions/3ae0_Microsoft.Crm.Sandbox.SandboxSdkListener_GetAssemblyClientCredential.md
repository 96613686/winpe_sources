# Microsoft.Crm.Sandbox.SandboxSdkListener::GetAssemblyClientCredential

- ea: `0x3ae0`
- end: `0x3b09`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::GetAssemblyClientCredential`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x3ae6`: `_pluginSecureStoreService`

## pseudocode

```c

```

## disassembly

```asm
0x3ae0  ldarg.0
0x3ae1  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x3ae6  ldstr    aPluginsecurest_0// "_pluginSecureStoreService"
0x3aeb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3af0  ldarg.0
0x3af1  ldarg.1
0x3af2  ldstr    aGetassemblycli// "GetAssemblyClientCredential"
0x3af7  ldarg.0
0x3af8  ldftn    instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCredentials Microsoft.Crm.Sandbox.SandboxSdkListener::<GetAssemblyClientCredential>b__19_0(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo delegateCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x3afe  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCredentials>::.ctor(object, native int)
0x3b03  call     T0x2B00000F
0x3b08  ret
```
