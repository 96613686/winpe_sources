# Microsoft.Crm.Sandbox.SandboxSdkListener::HandleSecurityAndExceptionConvertion

- ea: `0x3ca0`
- end: `0x3fff`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::HandleSecurityAndExceptionConvertion`
- size: `863`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x3ca0`
- `0x5180`
- `0x53f0`
- `0x5620`
- `0x5630`
- `0x56a0`

## string_xrefs

- `0x3ca0`: `SandboxSdkListener.HandleSecurityAndExceptionConvertion[]`

## pseudocode

```c

```

## disassembly

```asm
0x3ca0  ldstr    aSandboxsdklist// "SandboxSdkListener.HandleSecurityAndExc"...
0x3ca5  ldarg.2
0x3ca6  brfalse.s loc_3CAB
0x3ca8  ldarg.2
0x3ca9  br.s     loc_3CB0
0x3cab  ldstr    aNull// "null"
0x3cb0  call     string [mscorlib]System.String::Concat(string, string)
0x3cb5  ldarg.1
0x3cb6  brtrue.s loc_3CBF
0x3cb8  ldsfld   string [mscorlib]System.String::Empty
0x3cbd  br.s     loc_3CC5
0x3cbf  ldarg.1
0x3cc0  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_OrgTraceCategory()
0x3cc5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3cca  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3ccf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3cd4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3cd9  ldarg.1
0x3cda  brtrue.s loc_3CE3
0x3cdc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3ce1  br.s     loc_3CF1
0x3ce3  ldarg.1
0x3ce4  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ActivityId()
0x3ce9  stloc.1
0x3cea  ldloca.s 1
0x3cec  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x3cf1  ldc.i4.m1
0x3cf2  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x3cf7  stloc.0
0x3cf8  ldarg.1
0x3cf9  ldstr    aCallinfo// "callInfo"
0x3cfe  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3d03  ldarg.1
0x3d04  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x3d09  ldstr    aCallinfoParent// "callInfo.ParentCallInfo"
0x3d0e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3d13  ldarg.1
0x3d14  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x3d19  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x3d1e  ldstr    aCallinfoParent_0// "callInfo.ParentCallInfo.ParentCallInfo"
0x3d23  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3d28  ldarg.2
0x3d29  ldstr    aTracename// "traceName"
0x3d2e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3d33  ldarg.3
0x3d34  ldstr    aExpression// "expression"
0x3d39  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3d3e  ldstr    aSandbox_0// "sandbox"
0x3d43  stloc.2
0x3d44  ldarg.1
0x3d45  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x3d4a  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_PluginInfo()
0x3d4f  stloc.3
0x3d50  ldstr    aIsandboxsdklis// "ISandboxSdkListener.{0}"
0x3d55  ldarg.2
0x3d56  call     string [mscorlib]System.String::Format(string, object)
0x3d5b  stloc.s  4
0x3d5d  ldloc.s  4
0x3d5f  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string)
0x3d64  stloc.s  5
0x3d66  ldarg.0
0x3d67  ldarg.1
0x3d68  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxSdkListener::GetPluginExecutionIdFromCallInfo(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo)
0x3d6d  stloc.s  6
0x3d6f  ldloc.0
0x3d70  ldloc.s  6
0x3d72  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::SetExecutionId(valuetype [mscorlib]System.Guid)
0x3d77  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x3d7c  stloc.s  7
0x3d7e  ldloca.s 8
0x3d80  initobj  mvar<u1>
0x3d86  ldnull
0x3d87  stloc.s  9
0x3d89  ldsfld   string [mscorlib]System.String::Empty
0x3d8e  stloc.s  0xA
0x3d90  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3d95  stloc.s  0xB
0x3d97  ldarg.1
0x3d98  ldnull
0x3d99  ldnull
0x3d9a  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxSdkListener::AuthenticateCaller(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext requestContext, string operation)
0x3d9f  stloc.s  9
0x3da1  ldloc.s  9
0x3da3  ldstr    aContext// "context"
0x3da8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3dad  ldloc.s  9
0x3daf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3db4  brfalse.s loc_3DCE
0x3db6  ldloc.s  9
0x3db8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3dbd  ldstr    aParentexecutio// "parentExecutionId"
0x3dc2  ldloc.s  0xB
0x3dc4  box      [mscorlib]System.Guid
0x3dc9  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x3dce  ldloc.s  9
0x3dd0  brfalse.s loc_3E01
0x3dd2  ldloc.0
0x3dd3  ldloc.s  9
0x3dd5  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x3dda  stloc.1
0x3ddb  ldloca.s 1
0x3ddd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x3de2  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::SetRequestId(valuetype [mscorlib]System.Guid)
0x3de7  ldloc.0
0x3de8  ldloc.s  9
0x3dea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x3def  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::SetTrackingId(valuetype [mscorlib]System.Guid)
0x3df4  ldloc.0
0x3df5  ldloc.s  9
0x3df7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x3dfc  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::SetOrganizationId(valuetype [mscorlib]System.Guid)
0x3e01  ldloc.s  5
0x3e03  ldloc.s  9
0x3e05  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x3e0a  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::AdditionalData(valuetype [mscorlib]System.Guid)
0x3e0f  ldloc.s  5
0x3e11  ldloc.s  9
0x3e13  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x3e18  ldarg.1
0x3e19  ldloc.s  9
0x3e1b  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x3e20  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Enter(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, int32)
0x3e25  ldloc.s  7
0x3e27  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x3e2c  ldarg.3
0x3e2d  ldarg.1
0x3e2e  ldloc.s  9
0x3e30  callvirt instance var<u1> class [mscorlib]System.Func`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, mvar<u1>>::Invoke(bool, var<u1>)
0x3e35  stloc.s  8
0x3e37  ldloc.s  7
0x3e39  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3e3e  ldloc.s  5
0x3e40  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodExit()
0x3e45  call     class Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::get_Instance()
0x3e4a  ldloc.s  9
0x3e4c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x3e51  ldloc.2
0x3e52  ldloc.3
0x3e53  ldloc.s  9
0x3e55  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityName()
0x3e5a  ldloc.s  9
0x3e5c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x3e61  ldloc.s  4
0x3e63  ldloc.s  7
0x3e65  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x3e6a  ldloc.s  9
0x3e6c  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x3e71  stloc.1
0x3e72  ldloca.s 1
0x3e74  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x3e79  ldloc.s  6
0x3e7b  ldloc.s  0xB
0x3e7d  ldarg.1
0x3e7e  brtrue.s loc_3E83
0x3e80  ldc.i4.0
0x3e81  br.s     loc_3E89
0x3e83  ldarg.1
0x3e84  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x3e89  callvirt instance void Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::OperationSuccess(valuetype [mscorlib]System.Guid organizationId, string isolationMode, string pluginInfo, string primaryEntityName, valuetype [mscorlib]System.Guid trackingId, string operation, int64 executionTime, valuetype [mscorlib]System.Guid requestId, valuetype [mscorlib]System.Guid executionId, valuetype [mscorlib]System.Guid parentExecutionId, bool useDrawBridgeIsolation)
0x3e8e  leave    loc_3FEC
0x3e93  stloc.s  0xC
0x3e95  ldloc.s  7
0x3e97  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3e9c  ldloc.s  9
0x3e9e  brtrue.s loc_3EA7
0x3ea0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3ea5  br.s     loc_3EAE
0x3ea7  ldloc.s  9
0x3ea9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x3eae  stloc.s  0xD
0x3eb0  ldloc.s  9
0x3eb2  brtrue.s loc_3EBB
0x3eb4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3eb9  br.s     loc_3EC2
0x3ebb  ldloc.s  9
0x3ebd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x3ec2  stloc.s  0xE
0x3ec4  ldloc.s  0xC
0x3ec6  ldloc.s  0xD
0x3ec8  ldc.i4.s 0x21
0x3eca  ldstr    aSandboxsdklist_0// "SandboxSdkListener.{0}: {1}"
0x3ecf  ldc.i4.2
0x3ed0  newarr   [mscorlib]System.Object
0x3ed5  dup
0x3ed6  ldc.i4.0
0x3ed7  ldarg.2
0x3ed8  stelem.ref
0x3ed9  dup
0x3eda  ldc.i4.1
0x3edb  ldloc.s  0xC
0x3edd  stelem.ref
0x3ede  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3ee3  ldloc.s  5
0x3ee5  ldloc.s  0xC
0x3ee7  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::BadExit(class [mscorlib]System.Exception)
0x3eec  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter Microsoft.Crm.Sandbox.SandboxSdkListener::_exceptionConverter
0x3ef1  ldloc.s  0xC
0x3ef3  ldc.i4.1
0x3ef4  ldloca.s 0xF
0x3ef6  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToFaultException(class [mscorlib]System.Exception, bool, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0x3efb  brfalse  loc_3F80
0x3f00  ldloc.s  0xF
0x3f02  brfalse.s loc_3F0D
0x3f04  ldloc.s  0xF
0x3f06  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x3f0b  brtrue.s loc_3F10
0x3f0d  ldc.i4.0
0x3f0e  br.s     loc_3F1C
0x3f10  ldloc.s  0xF
0x3f12  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x3f17  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x3f1c  stloc.s  0x10
0x3f1e  ldloc.s  0x10
0x3f20  call     int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmDatacenterService::ClassifyErrorCode(int32)
0x3f25  stloc.s  0x11
0x3f27  call     class Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::get_Instance()
0x3f2c  ldloc.s  0xD
0x3f2e  ldloc.2
0x3f2f  ldloc.3
0x3f30  ldloc.s  0xA
0x3f32  ldloc.s  0xE
0x3f34  ldloc.s  4
0x3f36  ldloc.s  7
0x3f38  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x3f3d  ldloc.s  0x11
0x3f3f  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::ConvertOperationResult(int32)
0x3f44  ldloc.s  0x10
0x3f46  ldloc.s  0xC
0x3f48  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x3f4d  callvirt instance string [mscorlib]System.Object::ToString()
0x3f52  ldloc.s  0xC
0x3f54  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3f59  ldloc.s  9
0x3f5b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x3f60  stloc.1
0x3f61  ldloca.s 1
0x3f63  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x3f68  ldloc.s  6
0x3f6a  ldloc.s  0xB
0x3f6c  ldarg.1
0x3f6d  brtrue.s loc_3F72
0x3f6f  ldc.i4.0
0x3f70  br.s     loc_3F78
0x3f72  ldarg.1
0x3f73  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x3f78  callvirt instance void Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::OperationFailure(valuetype [mscorlib]System.Guid organizationId, string isolationMode, string pluginInfo, string primaryEntityName, valuetype [mscorlib]System.Guid trackingId, string operation, int64 executionTime, string errorCategory, int32 errorCode, string exceptionType, string exceptionMessage, valuetype [mscorlib]System.Guid requestId, valuetype [mscorlib]System.Guid executionId, valuetype [mscorlib]System.Guid parentExecutionId, bool useDrawBridgeIsolation)
0x3f7d  ldloc.s  0xF
0x3f7f  throw
0x3f80  ldloc.s  0xC
0x3f82  ldloc.s  0xD
0x3f84  ldc.i4.s 0x21
0x3f86  ldstr    aUnexpectedExce// "UNEXPECTED: exception not converted"
0x3f8b  ldc.i4.0
0x3f8c  newarr   [mscorlib]System.Object
0x3f91  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3f96  call     class Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::get_Instance()
0x3f9b  ldloc.s  0xD
0x3f9d  ldloc.2
0x3f9e  ldloc.3
0x3f9f  ldloc.s  0xA
0x3fa1  ldloc.s  0xE
0x3fa3  ldloc.s  4
0x3fa5  ldloc.s  7
0x3fa7  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x3fac  ldc.i4.0
0x3fad  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::ConvertOperationResult(int32)
0x3fb2  ldc.i4.0
0x3fb3  ldloc.s  0xC
0x3fb5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x3fba  callvirt instance string [mscorlib]System.Object::ToString()
0x3fbf  ldloc.s  0xC
0x3fc1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3fc6  ldloc.s  9
0x3fc8  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x3fcd  stloc.1
0x3fce  ldloca.s 1
0x3fd0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x3fd5  ldloc.s  6
0x3fd7  ldloc.s  0xB
0x3fd9  ldarg.1
0x3fda  brtrue.s loc_3FDF
0x3fdc  ldc.i4.0
0x3fdd  br.s     loc_3FE5
0x3fdf  ldarg.1
0x3fe0  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x3fe5  callvirt instance void Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::OperationFailure(valuetype [mscorlib]System.Guid organizationId, string isolationMode, string pluginInfo, string primaryEntityName, valuetype [mscorlib]System.Guid trackingId, string operation, int64 executionTime, string errorCategory, int32 errorCode, string exceptionType, string exceptionMessage, valuetype [mscorlib]System.Guid requestId, valuetype [mscorlib]System.Guid executionId, valuetype [mscorlib]System.Guid parentExecutionId, bool useDrawBridgeIsolation)
0x3fea  rethrow
0x3fec  ldloc.s  8
0x3fee  stloc.s  0x12
0x3ff0  leave.s  loc_3FFC
0x3ff2  ldloc.0
0x3ff3  brfalse.s loc_3FFB
0x3ff5  ldloc.0
0x3ff6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3ffb  endfinally
0x3ffc  ldloc.s  0x12
0x3ffe  ret
```
