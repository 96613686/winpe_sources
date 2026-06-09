# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::SetSecret

- ea: `0x77c0`
- end: `0x78a0`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::SetSecret`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x7120`
- `0x9560`

## string_xrefs

- `0x7813`: `PluginSecureStoreServiceProvider.SetSecret - started. CallInfo {0}`
- `0x787c`: `PluginSecureStoreServiceProvider.SetSecret - successfully finished. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x77c0  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x77c5  stloc.0
0x77c6  ldloc.0
0x77c7  ldarg.0
0x77c8  stfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass9_0::<>4__this
0x77cd  ldloc.0
0x77ce  ldarg.1
0x77cf  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass9_0::callInfo
0x77d4  ldloc.0
0x77d5  ldarg.2
0x77d6  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass9_0::context
0x77db  ldloc.0
0x77dc  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass9_0::callInfo
0x77e1  ldstr    aCallinfo// "callInfo"
0x77e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x77eb  ldloc.0
0x77ec  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass9_0::context
0x77f1  ldstr    aContext// "context"
0x77f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x77fb  ldarg.3
0x77fc  ldstr    aSecretname// "secretName"
0x7801  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7806  ldloc.0
0x7807  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass9_0::context
0x780c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7811  ldc.i4.s 0x1F
0x7813  ldstr    aPluginsecurest_3// "PluginSecureStoreServiceProvider.SetSec"...
0x7818  ldc.i4.1
0x7819  newarr   [mscorlib]System.Object
0x781e  dup
0x781f  ldc.i4.0
0x7820  ldloc.0
0x7821  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass9_0::callInfo
0x7826  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x782b  box      [mscorlib]System.Guid
0x7830  stelem.ref
0x7831  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7836  ldarg.0
0x7837  ldloc.0
0x7838  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass9_0::callInfo
0x783d  ldloc.0
0x783e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass9_0::context
0x7843  ldstr    aKvaddress// "kvAddress"
0x7848  ldloc.0
0x7849  ldftn    instance string <>c__DisplayClass9_0::<SetSecret>b__0()
0x784f  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x7854  call     T0x2B00001A
0x7859  stloc.1
0x785a  ldarg.0
0x785b  ldfld    class Microsoft.Crm.Sandbox.Service.IKeyVaultService Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_keyVaultService
0x7860  ldloc.1
0x7861  ldarg.3
0x7862  ldarg.s  4
0x7864  ldloc.0
0x7865  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass9_0::context
0x786a  callvirt instance void Microsoft.Crm.Sandbox.Service.IKeyVaultService::SetSecret(string tpsAwareKeyVaultAddress, string secretName, string secretValue, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x786f  ldloc.0
0x7870  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass9_0::context
0x7875  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x787a  ldc.i4.s 0x1F
0x787c  ldstr    aPluginsecurest_4// "PluginSecureStoreServiceProvider.SetSec"...
0x7881  ldc.i4.1
0x7882  newarr   [mscorlib]System.Object
0x7887  dup
0x7888  ldc.i4.0
0x7889  ldloc.0
0x788a  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass9_0::callInfo
0x788f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7894  box      [mscorlib]System.Guid
0x7899  stelem.ref
0x789a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x789f  ret
```
