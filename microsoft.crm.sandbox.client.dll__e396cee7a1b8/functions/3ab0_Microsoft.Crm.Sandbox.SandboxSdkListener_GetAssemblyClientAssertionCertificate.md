# Microsoft.Crm.Sandbox.SandboxSdkListener::GetAssemblyClientAssertionCertificate

- ea: `0x3ab0`
- end: `0x3ad9`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::GetAssemblyClientAssertionCertificate`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x3ab6`: `_pluginSecureStoreService`

## pseudocode

```c

```

## disassembly

```asm
0x3ab0  ldarg.0
0x3ab1  ldfld    class Microsoft.Crm.Sandbox.Service.IPluginSecureStoreService Microsoft.Crm.Sandbox.SandboxSdkListener::_pluginSecureStoreService
0x3ab6  ldstr    aPluginsecurest_0// "_pluginSecureStoreService"
0x3abb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3ac0  ldarg.0
0x3ac1  ldarg.1
0x3ac2  ldstr    aGetassemblycli// "GetAssemblyClientCredential"
0x3ac7  ldarg.0
0x3ac8  ldftn    instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCertificate Microsoft.Crm.Sandbox.SandboxSdkListener::<GetAssemblyClientAssertionCertificate>b__18_0(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo delegateCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x3ace  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCertificate>::.ctor(object, native int)
0x3ad3  call     T0x2B00000E
0x3ad8  ret
```
