# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetAssemblyClientCredential

- ea: `0x7950`
- end: `0x79f1`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetAssemblyClientCredential`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x9600`

## string_xrefs

- `0x798c`: `PluginSecureStoreServiceProvider.GetAssemblyClientCredential - started. CallInfo {0}`
- `0x79d1`: `PluginSecureStoreServiceProvider.GetAssemblyClientCredential - successfully finished. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7950  newobj   instance void <>c__DisplayClass11_0::.ctor()
0x7955  stloc.0
0x7956  ldloc.0
0x7957  ldarg.0
0x7958  stfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass11_0::<>4__this
0x795d  ldloc.0
0x795e  ldarg.2
0x795f  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass11_0::context
0x7964  ldarg.1
0x7965  ldstr    aCallinfo// "callInfo"
0x796a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x796f  ldloc.0
0x7970  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass11_0::context
0x7975  ldstr    aContext// "context"
0x797a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x797f  ldloc.0
0x7980  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass11_0::context
0x7985  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x798a  ldc.i4.s 0x1F
0x798c  ldstr    aPluginsecurest_5// "PluginSecureStoreServiceProvider.GetAss"...
0x7991  ldc.i4.1
0x7992  newarr   [mscorlib]System.Object
0x7997  dup
0x7998  ldc.i4.0
0x7999  ldarg.1
0x799a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x799f  box      [mscorlib]System.Guid
0x79a4  stelem.ref
0x79a5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x79aa  ldarg.0
0x79ab  ldarg.1
0x79ac  ldloc.0
0x79ad  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass11_0::context
0x79b2  ldloc.0
0x79b3  ldftn    instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCredentials <>c__DisplayClass11_0::<GetAssemblyClientCredential>b__0(string shortName, string keyVaultUri)
0x79b9  newobj   instance void class [mscorlib]System.Func`3<string, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCredentials>::.ctor(object, native int)
0x79be  call     T0x2B00001C
0x79c3  stloc.1
0x79c4  ldloc.0
0x79c5  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass11_0::context
0x79ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x79cf  ldc.i4.s 0x1F
0x79d1  ldstr    aPluginsecurest_6// "PluginSecureStoreServiceProvider.GetAss"...
0x79d6  ldc.i4.1
0x79d7  newarr   [mscorlib]System.Object
0x79dc  dup
0x79dd  ldc.i4.0
0x79de  ldarg.1
0x79df  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x79e4  box      [mscorlib]System.Guid
0x79e9  stelem.ref
0x79ea  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x79ef  ldloc.1
0x79f0  ret
```
