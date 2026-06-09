# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetSecret

- ea: `0x76e0`
- end: `0x77c0`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetSecret`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x7110`
- `0x9500`

## string_xrefs

- `0x7733`: `PluginSecureStoreServiceProvider.GetSecret - started. CallInfo {0}`
- `0x779b`: `PluginSecureStoreServiceProvider.GetSecret - successfully finished. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x76e0  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x76e5  stloc.0
0x76e6  ldloc.0
0x76e7  ldarg.0
0x76e8  stfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass8_0::<>4__this
0x76ed  ldloc.0
0x76ee  ldarg.1
0x76ef  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass8_0::callInfo
0x76f4  ldloc.0
0x76f5  ldarg.2
0x76f6  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass8_0::context
0x76fb  ldloc.0
0x76fc  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass8_0::callInfo
0x7701  ldstr    aCallinfo// "callInfo"
0x7706  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x770b  ldloc.0
0x770c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass8_0::context
0x7711  ldstr    aContext// "context"
0x7716  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x771b  ldarg.3
0x771c  ldstr    aSecretname// "secretName"
0x7721  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7726  ldloc.0
0x7727  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass8_0::context
0x772c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7731  ldc.i4.s 0x1F
0x7733  ldstr    aPluginsecurest_1// "PluginSecureStoreServiceProvider.GetSec"...
0x7738  ldc.i4.1
0x7739  newarr   [mscorlib]System.Object
0x773e  dup
0x773f  ldc.i4.0
0x7740  ldloc.0
0x7741  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass8_0::callInfo
0x7746  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x774b  box      [mscorlib]System.Guid
0x7750  stelem.ref
0x7751  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7756  ldarg.0
0x7757  ldloc.0
0x7758  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass8_0::callInfo
0x775d  ldloc.0
0x775e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass8_0::context
0x7763  ldstr    aKvaddress// "kvAddress"
0x7768  ldloc.0
0x7769  ldftn    instance string <>c__DisplayClass8_0::<GetSecret>b__0()
0x776f  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x7774  call     T0x2B00001A
0x7779  stloc.1
0x777a  ldarg.0
0x777b  ldfld    class Microsoft.Crm.Sandbox.Service.IKeyVaultService Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_keyVaultService
0x7780  ldloc.1
0x7781  ldarg.3
0x7782  ldloc.0
0x7783  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass8_0::context
0x7788  callvirt instance string Microsoft.Crm.Sandbox.Service.IKeyVaultService::GetSecret(string tpsAwareKeyVaultAddress, string secretName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x778d  stloc.2
0x778e  ldloc.0
0x778f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass8_0::context
0x7794  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7799  ldc.i4.s 0x1F
0x779b  ldstr    aPluginsecurest_2// "PluginSecureStoreServiceProvider.GetSec"...
0x77a0  ldc.i4.1
0x77a1  newarr   [mscorlib]System.Object
0x77a6  dup
0x77a7  ldc.i4.0
0x77a8  ldloc.0
0x77a9  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass8_0::callInfo
0x77ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x77b3  box      [mscorlib]System.Guid
0x77b8  stelem.ref
0x77b9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x77be  ldloc.2
0x77bf  ret
```
