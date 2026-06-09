# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::ExecuteIfAssemblyIsValid

- ea: `0x7d10`
- end: `0x7dbb`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::ExecuteIfAssemblyIsValid`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x7d10`
- `0x7dc0`
- `0x7dd0`
- `0x7de0`
- `0x7e90`
- `0x8090`
- `0x80e0`

## string_xrefs

- `0x7d18`: `PluginSecureStoreServiceProvider.ExecuteIfAssemblyIsValid - started. CallInfo {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7d10  ldarg.2
0x7d11  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7d16  ldc.i4.s 0x1F
0x7d18  ldstr    aPluginsecurest_17// "PluginSecureStoreServiceProvider.Execut"...
0x7d1d  ldc.i4.1
0x7d1e  newarr   [mscorlib]System.Object
0x7d23  dup
0x7d24  ldc.i4.0
0x7d25  ldarg.1
0x7d26  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7d2b  box      [mscorlib]System.Guid
0x7d30  stelem.ref
0x7d31  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7d36  ldarg.0
0x7d37  ldarg.1
0x7d38  call     instance void Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::ValidateCallInfo(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo)
0x7d3d  ldarg.0
0x7d3e  ldarg.1
0x7d3f  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x7d44  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x7d49  ldarg.2
0x7d4a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetAssemblyMetadataAndValidateIsFullySigned(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x7d4f  stloc.0
0x7d50  ldarg.0
0x7d51  ldloc.0
0x7d52  ldarg.1
0x7d53  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x7d58  ldarg.2
0x7d59  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7d5e  call     instance void Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::ValidateAssemblyData(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData assemblyData, valuetype [mscorlib]System.Guid callInfoId, valuetype [mscorlib]System.Guid orgId)
0x7d63  ldarg.0
0x7d64  ldarg.2
0x7d65  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetTransactionContextId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x7d6a  stloc.1
0x7d6b  ldarg.0
0x7d6c  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ITransactedMessageContextFactory Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_transactedMessageContextFactory
0x7d71  ldarg.2
0x7d72  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7d77  ldloc.1
0x7d78  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ITransactedMessageContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ITransactedMessageContextFactory::Create(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7d7d  stloc.2
0x7d7e  ldloc.2
0x7d7f  ldc.i4.0
0x7d80  ldc.i4.0
0x7d81  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ITransactedMessageContext::OpenContext(bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x7d86  stloc.3
0x7d87  ldarg.0
0x7d88  ldloc.3
0x7d89  ldc.i4.1
0x7d8a  call     instance void Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::TryBeginRequest(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext, bool startTransaction)
0x7d8f  ldarg.3
0x7d90  ldloc.0
0x7d91  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PluginAssemblySimpleName()
0x7d96  ldloc.0
0x7d97  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData::get_PublicKeyToken()
0x7d9c  ldloc.3
0x7d9d  callvirt instance var<u1> class [mscorlib]System.Func`4<string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, mvar<u1>>::Invoke(char, var<u1>, !!T0)
0x7da2  stloc.s  4
0x7da4  leave.s  loc_7DB8
0x7da6  ldarg.0
0x7da7  ldloc.3
0x7da8  call     instance void Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::TryEndRequest(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x7dad  endfinally
0x7dae  ldloc.2
0x7daf  brfalse.s loc_7DB7
0x7db1  ldloc.2
0x7db2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7db7  endfinally
0x7db8  ldloc.s  4
0x7dba  ret
```
