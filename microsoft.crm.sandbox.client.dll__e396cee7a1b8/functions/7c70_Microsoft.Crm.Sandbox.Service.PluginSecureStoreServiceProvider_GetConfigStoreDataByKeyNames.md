# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetConfigStoreDataByKeyNames

- ea: `0x7c70`
- end: `0x7d0d`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetConfigStoreDataByKeyNames`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x9710`

## string_xrefs

- `0x7cb2`: `PluginSecureStoreServiceProvider.GetConfigStoreDataByKeyNames - started. CallInfo {0}`
- `0x7ced`: `PluginSecureStoreServiceProvider.GetConfigStoreDataByKeyNames - successfully finished. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7c70  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x7c75  stloc.0
0x7c76  ldloc.0
0x7c77  ldarg.0
0x7c78  stfld    class Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider <>c__DisplayClass16_0::<>4__this
0x7c7d  ldloc.0
0x7c7e  ldarg.3
0x7c7f  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass16_0::keyNames
0x7c84  ldarg.1
0x7c85  ldstr    aCallinfo// "callInfo"
0x7c8a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7c8f  ldarg.2
0x7c90  ldstr    aContext// "context"
0x7c95  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7c9a  ldloc.0
0x7c9b  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass16_0::keyNames
0x7ca0  ldstr    aKeynames// "keyNames"
0x7ca5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7caa  ldarg.2
0x7cab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7cb0  ldc.i4.s 0x1F
0x7cb2  ldstr    aPluginsecurest_15// "PluginSecureStoreServiceProvider.GetCon"...
0x7cb7  ldc.i4.1
0x7cb8  newarr   [mscorlib]System.Object
0x7cbd  dup
0x7cbe  ldc.i4.0
0x7cbf  ldarg.1
0x7cc0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7cc5  box      [mscorlib]System.Guid
0x7cca  stelem.ref
0x7ccb  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7cd0  ldarg.0
0x7cd1  ldarg.1
0x7cd2  ldarg.2
0x7cd3  ldloc.0
0x7cd4  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass16_0::<GetConfigStoreDataByKeyNames>b__0(string assemblyName, string publicToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext sqlContext)
0x7cda  newobj   instance void class [mscorlib]System.Func`4<string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>>::.ctor(object, native int)
0x7cdf  call     T0x2B00001F
0x7ce4  stloc.1
0x7ce5  ldarg.2
0x7ce6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7ceb  ldc.i4.s 0x1F
0x7ced  ldstr    aPluginsecurest_16// "PluginSecureStoreServiceProvider.GetCon"...
0x7cf2  ldc.i4.1
0x7cf3  newarr   [mscorlib]System.Object
0x7cf8  dup
0x7cf9  ldc.i4.0
0x7cfa  ldarg.1
0x7cfb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7d00  box      [mscorlib]System.Guid
0x7d05  stelem.ref
0x7d06  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7d0b  ldloc.1
0x7d0c  ret
```
