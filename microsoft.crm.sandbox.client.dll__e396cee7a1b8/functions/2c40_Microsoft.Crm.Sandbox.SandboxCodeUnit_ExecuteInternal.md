# Microsoft.Crm.Sandbox.SandboxCodeUnit::ExecuteInternal

- ea: `0x2c40`
- end: `0x2f69`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::ExecuteInternal`
- size: `809`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x8dc0`

## callees

- `0x480`
- `0x2340`
- `0x2350`
- `0x2360`
- `0x2c40`
- `0x2ff0`
- `0x30f0`
- `0x37c0`

## string_xrefs

- `0x2c99`: `requestContext.OwningExtension`
- `0x2d69`: `Service Bus Issuer Certificate`
- `0x2d7d`: `SandboxCodeUnit.Execute: ServiceBusIssuer Certificate is null.`
- `0x2dce`: `PluginTraceLoggingVerboseEnabled`
- `0x2dfa`: `HostCommunication`

## pseudocode

```c

```

## disassembly

```asm
0x2c40  ldarg.2
0x2c41  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x2c46  stloc.0
0x2c47  ldarg.2
0x2c48  brtrue.s loc_2C51
0x2c4a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2c4f  br.s     loc_2C57
0x2c51  ldarg.2
0x2c52  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x2c57  stloc.1
0x2c58  ldarg.2
0x2c59  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x2c5e  stloc.2
0x2c5f  ldarg.2
0x2c60  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x2c65  stloc.3
0x2c66  ldstr    aClient// "Client"
0x2c6b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.ChaosAgent::ChaosExecution(string)
0x2c70  ldarg.2
0x2c71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x2c76  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsDrawbridgeIsolationEnabled(valuetype [mscorlib]System.Guid)
0x2c7b  stloc.s  4
0x2c7d  ldarg.0
0x2c7e  ldarg.2
0x2c7f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCodeUnit::GetRequestContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x2c84  stloc.s  7
0x2c86  ldloc.s  7
0x2c88  ldstr    aRequestcontext// "requestContext"
0x2c8d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2c92  ldloc.s  7
0x2c94  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x2c99  ldstr    aRequestcontext_0// "requestContext.OwningExtension"
0x2c9e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2ca3  ldstr    aSandboxcodeuni_1// "SandboxCodeUnit.Execute: "
0x2ca8  ldarg.2
0x2ca9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x2cae  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string, valuetype [mscorlib]System.Guid)
0x2cb3  stloc.s  8
0x2cb5  ldloc.s  8
0x2cb7  ldloc.3
0x2cb8  ldarg.0
0x2cb9  ldfld    string Microsoft.Crm.Sandbox.SandboxCodeUnit::_assemblyName
0x2cbe  ldarg.0
0x2cbf  ldfld    string Microsoft.Crm.Sandbox.SandboxCodeUnit::_typeName
0x2cc4  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::AdditionalData(valuetype [mscorlib]System.Guid, string, string)
0x2cc9  ldloc.s  8
0x2ccb  ldarg.1
0x2ccc  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxHost>::get_Destination()
0x2cd1  ldloc.s  7
0x2cd3  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x2cd8  ldloc.3
0x2cd9  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x2cde  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Call(string, int32, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter)
0x2ce3  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x2ce8  brfalse.s loc_2CFC
0x2cea  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x2cef  ldc.i4.1
0x2cf0  ldloc.3
0x2cf1  ldstr    aSandbox// "Sandbox"
0x2cf6  ldc.i4.0
0x2cf7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnBeginRequest(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceTraceType, valuetype [mscorlib]System.Guid, string, int32)
0x2cfc  ldarg.s  4
0x2cfe  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x2d03  ldloc.s  4
0x2d05  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::set_UseDrawBridgeIsolation(bool)
0x2d0a  ldarg.s  4
0x2d0c  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x2d11  ldarg.2
0x2d12  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x2d17  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::GetOrgTraceCategory(valuetype [mscorlib]System.Guid)
0x2d1c  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::set_OrgTraceCategory(string)
0x2d21  ldarg.3
0x2d22  ldarg.s  4
0x2d24  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x2d29  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_OrgTraceCategory()
0x2d2e  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::SetOrgTraceCategory(string)
0x2d33  ldloc.s  4
0x2d35  brtrue.s loc_2D44
0x2d37  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x2d3c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x2d41  ldc.i4.1
0x2d42  bne.un.s loc_2DA4
0x2d44  ldsfld   class [mscorlib]System.Lazy`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> Microsoft.Crm.Sandbox.SandboxSdkListener::ListenerCertificate
0x2d49  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Value()
0x2d4e  stloc.s  0xC
0x2d50  ldloc.s  0xC
0x2d52  brtrue.s loc_2D8F
0x2d54  ldloc.s  0xC
0x2d56  brtrue.s loc_2D75
0x2d58  ldc.i4.2
0x2d59  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x2d5e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x2d63  ldc.i4.2
0x2d64  and
0x2d65  bne.un.s loc_2D75
0x2d67  ldloc.s  0xC
0x2d69  ldstr    aServiceBusIssu// "Service Bus Issuer Certificate"
0x2d6e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2d73  br.s     loc_2DA4
0x2d75  ldarg.2
0x2d76  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x2d7b  ldc.i4.s 0x26
0x2d7d  ldstr    aSandboxcodeuni_2// "SandboxCodeUnit.Execute: ServiceBusIssu"...
0x2d82  ldc.i4.0
0x2d83  newarr   [mscorlib]System.Object
0x2d88  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2d8d  br.s     loc_2DA4
0x2d8f  ldarg.s  4
0x2d91  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x2d96  ldloc.s  0xC
0x2d98  ldc.i4.3
0x2d99  ldc.i4.0
0x2d9a  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::GetNameInfo(valuetype [System]System.Security.Cryptography.X509Certificates.X509NameType, bool)
0x2d9f  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::set_ServiceCertificateDNSName(string)
0x2da4  ldstr    aSabdboxcodeuni// "SabdboxCodeunit.Execute.SerializeForTra"...
0x2da9  ldc.i4.3
0x2daa  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x2daf  stloc.s  0xD
0x2db1  ldarg.0
0x2db2  ldloc.s  7
0x2db4  callvirt instance void Microsoft.Crm.Sandbox.SandboxCodeUnit::SerializeForTransmit(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x2db9  leave.s  loc_2DC7
0x2dbb  ldloc.s  0xD
0x2dbd  brfalse.s loc_2DC6
0x2dbf  ldloc.s  0xD
0x2dc1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2dc6  endfinally
0x2dc7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2dcc  stloc.s  9
0x2dce  ldstr    aPlugintracelog_2// "PluginTraceLoggingVerboseEnabled"
0x2dd3  ldc.i4.0
0x2dd4  call     T0x2B000005
0x2dd9  brfalse.s loc_2DE6
0x2ddb  ldloc.3
0x2ddc  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTraceLogSettingType Microsoft.Crm.Sandbox.SandboxPluginHelper::GetPluginTraceLogSetting(valuetype [mscorlib]System.Guid organizationId)
0x2de1  ldc.i4.2
0x2de2  ceq
0x2de4  br.s     loc_2DE7
0x2de6  ldc.i4.0
0x2de7  stloc.s  0xA
0x2de9  ldstr    aSabdboxcodeuni_0// "SabdboxCodeunit.Execute.Execute"
0x2dee  ldc.i4.3
0x2def  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x2df4  stloc.s  0xD
0x2df6  ldarg.s  7
0x2df8  ldc.i4.0
0x2df9  stind.i1
0x2dfa  ldstr    aHostcommunicat// "HostCommunication"
0x2dff  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.ChaosAgent::ChaosClientCall(string)
0x2e04  ldarg.0
0x2e05  ldarg.1
0x2e06  ldarg.s  4
0x2e08  ldloc.s  7
0x2e0a  ldarg.s  6
0x2e0c  ldloc.s  0xA
0x2e0e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCodeUnit::Execute(class Microsoft.Crm.Sandbox.SandboxClient client, class Microsoft.Crm.Sandbox.SandboxCallTracker callTracker, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext requestContext, string assemblyContents, bool returnTraceInfo)
0x2e13  stloc.s  5
0x2e15  leave.s  loc_2E23
0x2e17  ldloc.s  0xD
0x2e19  brfalse.s loc_2E22
0x2e1b  ldloc.s  0xD
0x2e1d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e22  endfinally
0x2e23  ldloc.s  5
0x2e25  castclass [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext
0x2e2a  stloc.s  6
0x2e2c  ldloc.s  6
0x2e2e  ldloc.s  7
0x2e30  castclass [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext
0x2e35  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::Merge(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext)
0x2e3a  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x2e3f  brfalse.s loc_2E4C
0x2e41  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x2e46  ldc.i4.1
0x2e47  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnEndRequest(bool)
0x2e4c  ldloc.s  8
0x2e4e  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodReturn()
0x2e53  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::get_Instance()
0x2e58  ldloc.3
0x2e59  ldstr    aSandboxClient// "Sandbox Client"
0x2e5e  ldc.i4.1
0x2e5f  ldloc.1
0x2e60  ldarg.2
0x2e61  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x2e66  stloc.s  0xE
0x2e68  ldloca.s 0xE
0x2e6a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x2e6f  brtrue.s loc_2E78
0x2e71  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2e76  br.s     loc_2E87
0x2e78  ldarg.2
0x2e79  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x2e7e  stloc.s  0xE
0x2e80  ldloca.s 0xE
0x2e82  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x2e87  ldsfld   string [mscorlib]System.String::Empty
0x2e8c  ldsfld   string [mscorlib]System.String::Empty
0x2e91  ldsfld   string [mscorlib]System.String::Empty
0x2e96  ldsfld   string [mscorlib]System.String::Empty
0x2e9b  ldarg.s  4
0x2e9d  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x2ea2  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ExecutionTime()
0x2ea7  stloc.s  0xF
0x2ea9  ldloca.s 0xF
0x2eab  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x2eb0  ldloc.2
0x2eb1  ldarg.0
0x2eb2  ldfld    string Microsoft.Crm.Sandbox.SandboxCodeUnit::_assemblyName
0x2eb7  ldarg.0
0x2eb8  ldfld    string Microsoft.Crm.Sandbox.SandboxCodeUnit::_typeName
0x2ebd  ldsfld   string [mscorlib]System.String::Empty
0x2ec2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2ec7  ldc.i4.0
0x2ec8  ldarg.s  4
0x2eca  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x2ecf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x2ed4  ldarg.s  5
0x2ed6  ldsfld   string [mscorlib]System.String::Empty
0x2edb  ldloc.s  4
0x2edd  ldc.i4.0
0x2ede  ldc.i4.0
0x2edf  ldc.i4.0
0x2ee0  ldc.i4.0
0x2ee1  ldc.i4.0
0x2ee2  ldc.i4.0
0x2ee3  ldc.i4.0
0x2ee4  ldc.i4.0
0x2ee5  ldc.i4.0
0x2ee6  ldc.i4.1
0x2ee7  ldarg.2
0x2ee8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x2eed  ldstr    asc_CB5A// ":"
0x2ef2  ldloc.0
0x2ef3  brtrue.s loc_2EF8
0x2ef5  ldc.i4.0
0x2ef6  br.s     loc_2EFE
0x2ef8  ldloc.0
0x2ef9  call     instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_Stage()
0x2efe  box      [mscorlib]System.Int32
0x2f03  call     string [mscorlib]System.String::Concat(object, object, object)
0x2f08  ldnull
0x2f09  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxExecutionDiagnostics(valuetype [mscorlib]System.Guid, string, bool, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, string, string, string, float64, int32, string, string, string, valuetype [mscorlib]System.Guid, int32, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, bool, int32, int32, int32, int32, int32, int32, int32, int32, int32, int32, string, string)
0x2f0e  ldloc.s  5
0x2f10  ldarg.2
0x2f11  call     void Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext sourceContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext destContext)
0x2f16  ldloc.s  5
0x2f18  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext
0x2f1d  stloc.s  0xB
0x2f1f  ldloc.s  0xB
0x2f21  brfalse.s loc_2F3D
0x2f23  ldarg.2
0x2f24  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext
0x2f29  stloc.s  0x10
0x2f2b  ldloc.s  0x10
0x2f2d  brfalse.s loc_2F3D
0x2f2f  ldloc.s  0x10
0x2f31  ldloc.s  0xB
0x2f33  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::get_Arguments()
0x2f38  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::set_Arguments(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection)
0x2f3d  ldloc.s  0xA
0x2f3f  brfalse.s loc_2F64
0x2f41  ldloc.s  6
0x2f43  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_TraceInfo()
0x2f48  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2f4d  brtrue.s loc_2F64
0x2f4f  ldarg.0
0x2f50  ldarg.2
0x2f51  ldloc.s  9
0x2f53  ldloc.s  6
0x2f55  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_TraceInfo()
0x2f5a  ldsfld   string [mscorlib]System.String::Empty
0x2f5f  call     instance void Microsoft.Crm.Sandbox.SandboxCodeUnit::CreatePluginTraceLogRecord(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, valuetype [mscorlib]System.DateTime performanceExecutionStartTime, string traceText, string exceptionDetails)
0x2f64  ldarg.s  8
0x2f66  ldc.i4.1
0x2f67  stind.i1
0x2f68  ret
```
