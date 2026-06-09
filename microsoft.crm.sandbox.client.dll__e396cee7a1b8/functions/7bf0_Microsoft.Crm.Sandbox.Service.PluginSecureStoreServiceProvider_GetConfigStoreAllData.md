# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetConfigStoreAllData

- ea: `0x7bf0`
- end: `0x7c69`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetConfigStoreAllData`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x7c0e`: `PluginSecureStoreServiceProvider.GetConfigStoreAllData - started. CallInfo {0}`
- `0x7c49`: `PluginSecureStoreServiceProvider.GetConfigStoreAllData - successfully finished. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7bf0  ldarg.1
0x7bf1  ldstr    aCallinfo// "callInfo"
0x7bf6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7bfb  ldarg.2
0x7bfc  ldstr    aContext// "context"
0x7c01  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7c06  ldarg.2
0x7c07  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7c0c  ldc.i4.s 0x1F
0x7c0e  ldstr    aPluginsecurest_13// "PluginSecureStoreServiceProvider.GetCon"...
0x7c13  ldc.i4.1
0x7c14  newarr   [mscorlib]System.Object
0x7c19  dup
0x7c1a  ldc.i4.0
0x7c1b  ldarg.1
0x7c1c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7c21  box      [mscorlib]System.Guid
0x7c26  stelem.ref
0x7c27  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7c2c  ldarg.0
0x7c2d  ldarg.1
0x7c2e  ldarg.2
0x7c2f  ldarg.0
0x7c30  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::<GetConfigStoreAllData>b__15_0(string assemblyName, string publicToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext sqlContext)
0x7c36  newobj   instance void class [mscorlib]System.Func`4<string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>>::.ctor(object, native int)
0x7c3b  call     T0x2B00001F
0x7c40  stloc.0
0x7c41  ldarg.2
0x7c42  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7c47  ldc.i4.s 0x1F
0x7c49  ldstr    aPluginsecurest_14// "PluginSecureStoreServiceProvider.GetCon"...
0x7c4e  ldc.i4.1
0x7c4f  newarr   [mscorlib]System.Object
0x7c54  dup
0x7c55  ldc.i4.0
0x7c56  ldarg.1
0x7c57  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7c5c  box      [mscorlib]System.Guid
0x7c61  stelem.ref
0x7c62  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7c67  ldloc.0
0x7c68  ret
```
