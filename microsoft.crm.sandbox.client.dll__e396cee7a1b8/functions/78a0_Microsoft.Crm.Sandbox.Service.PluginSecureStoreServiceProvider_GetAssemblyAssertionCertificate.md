# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetAssemblyAssertionCertificate

- ea: `0x78a0`
- end: `0x7941`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetAssemblyAssertionCertificate`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x95c0`

## string_xrefs

- `0x78dc`: `PluginSecureStoreServiceProvider.GetAssemblyClientCredential - started. CallInfo {0}`
- `0x7921`: `PluginSecureStoreServiceProvider.GetAssemblyClientCredential - successfully finished. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x78a0  newobj   instance void <>c__DisplayClass10_0::.ctor()
0x78a5  stloc.0
0x78a6  ldloc.0
0x78a7  ldarg.0
0x78a8  stfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass10_0::<>4__this
0x78ad  ldloc.0
0x78ae  ldarg.2
0x78af  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass10_0::context
0x78b4  ldarg.1
0x78b5  ldstr    aCallinfo// "callInfo"
0x78ba  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x78bf  ldloc.0
0x78c0  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass10_0::context
0x78c5  ldstr    aContext// "context"
0x78ca  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x78cf  ldloc.0
0x78d0  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass10_0::context
0x78d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x78da  ldc.i4.s 0x1F
0x78dc  ldstr    aPluginsecurest_5// "PluginSecureStoreServiceProvider.GetAss"...
0x78e1  ldc.i4.1
0x78e2  newarr   [mscorlib]System.Object
0x78e7  dup
0x78e8  ldc.i4.0
0x78e9  ldarg.1
0x78ea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x78ef  box      [mscorlib]System.Guid
0x78f4  stelem.ref
0x78f5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x78fa  ldarg.0
0x78fb  ldarg.1
0x78fc  ldloc.0
0x78fd  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass10_0::context
0x7902  ldloc.0
0x7903  ldftn    instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCertificate <>c__DisplayClass10_0::<GetAssemblyAssertionCertificate>b__0(string shortName, string keyVaultUri)
0x7909  newobj   instance void class [mscorlib]System.Func`3<string, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCertificate>::.ctor(object, native int)
0x790e  call     T0x2B00001B
0x7913  stloc.1
0x7914  ldloc.0
0x7915  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass10_0::context
0x791a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x791f  ldc.i4.s 0x1F
0x7921  ldstr    aPluginsecurest_6// "PluginSecureStoreServiceProvider.GetAss"...
0x7926  ldc.i4.1
0x7927  newarr   [mscorlib]System.Object
0x792c  dup
0x792d  ldc.i4.0
0x792e  ldarg.1
0x792f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7934  box      [mscorlib]System.Guid
0x7939  stelem.ref
0x793a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x793f  ldloc.1
0x7940  ret
```
