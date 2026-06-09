# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetCredentials

- ea: `0x7ed0`
- end: `0x7f8e`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetCredentials`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x7e90`
- `0x80e0`

## string_xrefs

- `0x7eff`: `PluginSecureStoreServiceProvider.GetCredentials - started. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7ed0  newobj   instance void class <>c__DisplayClass22_0`1<mvar<u1>>::.ctor()
0x7ed5  stloc.0
0x7ed6  ldloc.0
0x7ed7  ldarg.0
0x7ed8  stfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider class <>c__DisplayClass22_0`1<mvar<u1>>::<>4__this
0x7edd  ldloc.0
0x7ede  ldarg.1
0x7edf  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo class <>c__DisplayClass22_0`1<mvar<u1>>::callInfo
0x7ee4  ldloc.0
0x7ee5  ldarg.2
0x7ee6  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext class <>c__DisplayClass22_0`1<mvar<u1>>::context
0x7eeb  ldloc.0
0x7eec  ldarg.3
0x7eed  stfld    class [mscorlib]System.Func`3<string, string, var<u1>> class <>c__DisplayClass22_0`1<mvar<u1>>::getCredential
0x7ef2  ldloc.0
0x7ef3  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext class <>c__DisplayClass22_0`1<mvar<u1>>::context
0x7ef8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7efd  ldc.i4.s 0x1F
0x7eff  ldstr    aPluginsecurest_20// "PluginSecureStoreServiceProvider.GetCre"...
0x7f04  ldc.i4.1
0x7f05  newarr   [mscorlib]System.Object
0x7f0a  dup
0x7f0b  ldc.i4.0
0x7f0c  ldloc.0
0x7f0d  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo class <>c__DisplayClass22_0`1<mvar<u1>>::callInfo
0x7f12  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7f17  box      [mscorlib]System.Guid
0x7f1c  stelem.ref
0x7f1d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7f22  ldarg.0
0x7f23  ldloc.0
0x7f24  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo class <>c__DisplayClass22_0`1<mvar<u1>>::callInfo
0x7f29  call     instance void Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::ValidateCallInfo(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo)
0x7f2e  ldloc.0
0x7f2f  ldarg.0
0x7f30  ldloc.0
0x7f31  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo class <>c__DisplayClass22_0`1<mvar<u1>>::callInfo
0x7f36  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x7f3b  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x7f40  ldloc.0
0x7f41  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext class <>c__DisplayClass22_0`1<mvar<u1>>::context
0x7f46  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetAssemblyMetadataAndValidateIsFullySigned(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x7f4b  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData class <>c__DisplayClass22_0`1<mvar<u1>>::assemblyData
0x7f50  ldarg.0
0x7f51  ldloc.0
0x7f52  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo class <>c__DisplayClass22_0`1<mvar<u1>>::callInfo
0x7f57  ldloc.0
0x7f58  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext class <>c__DisplayClass22_0`1<mvar<u1>>::context
0x7f5d  ldtoken  mvar<u1>
0x7f62  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7f67  callvirt instance string [mscorlib]System.Object::ToString()
0x7f6c  ldloc.0
0x7f6d  ldftn    instance var<u1> class <>c__DisplayClass22_0`1<mvar<u1>>::<GetCredentials>b__0()
0x7f73  newobj   instance void class [mscorlib]System.Func`1<mvar<u1>>::.ctor(object, native int)
0x7f78  call     T0x2B000020
0x7f7d  dup
0x7f7e  box      mvar<u1>
0x7f83  ldstr    aCredentials// "credentials"
0x7f88  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7f8d  ret
```
