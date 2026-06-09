# Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::ExecuteMultiple

- ea: `0x4f00`
- end: `0x5125`
- name: `Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::ExecuteMultiple`
- size: `549`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x4f00`
- `0x5130`
- `0x51f0`
- `0x52b0`
- `0x9e50`
- `0xace0`
- `0xb160`
- `0xb1b0`
- `0xb1f0`
- `0xb230`

## string_xrefs

- `0x500c`: `ExecuteMultiple Requests may not be executed inside of an ExecuteMultiple request!`

## pseudocode

```c

```

## disassembly

```asm
0x4f00  ldarg.1
0x4f01  ldstr    aRequests// "requests"
0x4f06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4f0b  ldarg.2
0x4f0c  ldstr    aSettings// "settings"
0x4f11  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4f16  ldarg.3
0x4f17  ldc.i4.0
0x4f18  stind.i1
0x4f19  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0x4f1e  stloc.0
0x4f1f  ldloc.0
0x4f20  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x4f25  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.DisasterRecoveryUtility::CheckIfIncorrectDatacenter(valuetype [mscorlib]System.Guid)
0x4f2a  ldloc.0
0x4f2b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::GetTargetUserId(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth)
0x4f30  stloc.1
0x4f31  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::GetTargetCallerRegardingObject()
0x4f36  stloc.2
0x4f37  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserType Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::GetTargetUserType()
0x4f3c  stloc.3
0x4f3d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x4f42  ldloc.0
0x4f43  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x4f48  ldloc.0
0x4f49  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x4f4e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4f53  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x4f58  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_ExecuteMultipleMaxBatchSize()
0x4f5d  stloc.s  4
0x4f5f  ldloc.s  4
0x4f61  ldc.i4.0
0x4f62  blt.s    loc_4F90
0x4f64  ldarg.1
0x4f65  call     int32 Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::GetRequestCollectionBatchSize(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequestCollection requests)
0x4f6a  ldloc.s  4
0x4f6c  ble.s    loc_4F90
0x4f6e  ldstr    aExecutemultipl// "ExecuteMultiple Request batch size exce"...
0x4f73  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x4f78  dup
0x4f79  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x4f7e  ldstr    aMaxbatchsize// "MaxBatchSize"
0x4f83  ldloc.s  4
0x4f85  box      [mscorlib]System.Int32
0x4f8a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::Add(var<u1>, !!T0)
0x4f8f  throw
0x4f90  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItemCollection::.ctor()
0x4f95  stloc.s  5
0x4f97  ldc.i4.0
0x4f98  stloc.s  6
0x4f9a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::.ctor()
0x4f9f  stloc.s  7
0x4fa1  ldarg.1
0x4fa2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest>::GetEnumerator()
0x4fa7  stloc.s  8
0x4fa9  br       loc_5108
0x4fae  ldloc.s  8
0x4fb0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest>::get_Current()
0x4fb5  stloc.s  9
0x4fb7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem::.ctor()
0x4fbc  dup
0x4fbd  ldloc.s  6
0x4fbf  dup
0x4fc0  ldc.i4.1
0x4fc1  add
0x4fc2  stloc.s  6
0x4fc4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem::set_RequestIndex(int32)
0x4fc9  stloc.s  0xA
0x4fcb  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0x4fd0  stloc.s  0xB
0x4fd2  ldloc.s  0xB
0x4fd4  ldloc.0
0x4fd5  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::GetOrganizationContext(class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken correlationToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth)
0x4fda  stloc.s  0xC
0x4fdc  ldloc.s  9
0x4fde  ldstr    aRequest// "Request"
0x4fe3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4fe8  ldloc.s  9
0x4fea  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x4fef  ldstr    aRequestRequest// "Request.RequestName"
0x4ff4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x4ff9  ldloc.s  9
0x4ffb  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x5000  ldstr    aExecutemultipl_0// "ExecuteMultiple"
0x5005  call     bool [mscorlib]System.String::op_Equality(string, string)
0x500a  brfalse.s loc_5017
0x500c  ldstr    aExecutemultipl_1// "ExecuteMultiple Requests may not be exe"...
0x5011  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x5016  throw
0x5017  ldarg.2
0x5018  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleSettings::get_ReturnResponses()
0x501d  brfalse.s loc_5065
0x501f  ldloc.s  9
0x5021  ldloc.s  0xC
0x5023  ldloc.s  7
0x5025  call     void Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::ChainRowVersionToRequests(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest organizationRequest, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> entityRowVersions)
0x502a  ldloc.s  0xA
0x502c  ldloc.s  9
0x502e  ldloc.s  0xB
0x5030  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.Extensibility.OrganizationSdkService::get_CallerOriginToken()
0x5035  ldc.i4.0
0x5036  ldloc.0
0x5037  ldloc.1
0x5038  ldloc.2
0x5039  ldloc.3
0x503a  ldloc.s  0xC
0x503c  ldc.i4.1
0x503d  ldc.i4.0
0x503e  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::ExecuteRequest(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken callerOriginToken, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType serviceType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid targetUserId, valuetype [mscorlib]System.Guid targetCallerRegardingObjectId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserType targetUserType, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context, bool returnResponse, bool checkAdminMode)
0x5043  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem::set_Response(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse)
0x5048  ldloc.s  9
0x504a  ldloc.s  0xA
0x504c  ldloc.s  7
0x504e  ldloc.s  0xA
0x5050  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem::get_Fault()
0x5055  call     void Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::UpdateRowVersions(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest organizationRequest, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem responseObject, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> entityRowVersions, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault organizationServiceFault)
0x505a  ldloc.s  5
0x505c  ldloc.s  0xA
0x505e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem>::Add(var<u1>)
0x5063  br.s     loc_507D
0x5065  ldloc.s  9
0x5067  ldloc.s  0xB
0x5069  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.Extensibility.OrganizationSdkService::get_CallerOriginToken()
0x506e  ldc.i4.0
0x506f  ldloc.0
0x5070  ldloc.1
0x5071  ldloc.2
0x5072  ldloc.3
0x5073  ldloc.s  0xC
0x5075  ldc.i4.0
0x5076  ldc.i4.0
0x5077  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::ExecuteRequest(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken callerOriginToken, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType serviceType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid targetUserId, valuetype [mscorlib]System.Guid targetCallerRegardingObjectId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserType targetUserType, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context, bool returnResponse, bool checkAdminMode)
0x507c  pop
0x507d  leave    loc_5108
0x5082  stloc.s  0xD
0x5084  ldloc.s  0xD
0x5086  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Watson.ExceptionManager::IsUnknownException(class [mscorlib]System.Exception)
0x508b  brfalse.s loc_50B5
0x508d  ldloc.s  0xD
0x508f  ldstr    aRequestname0// "RequestName: {0} "
0x5094  ldc.i4.1
0x5095  newarr   [mscorlib]System.Object
0x509a  dup
0x509b  ldc.i4.0
0x509c  ldloc.s  9
0x509e  brtrue.s loc_50A7
0x50a0  ldsfld   string [mscorlib]System.String::Empty
0x50a5  br.s     loc_50AE
0x50a7  ldloc.s  9
0x50a9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x50ae  stelem.ref
0x50af  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Watson.ExceptionManager::ReportException(class [mscorlib]System.Exception, string, object[])
0x50b4  pop
0x50b5  ldloc.s  0xD
0x50b7  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.FaultHelper::ConvertToFault(class [mscorlib]System.Exception)
0x50bc  stloc.s  0xE
0x50be  ldloc.s  0xA
0x50c0  ldloc.s  0xE
0x50c2  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x50c7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem::set_Fault(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault)
0x50cc  ldloc.s  5
0x50ce  ldloc.s  0xA
0x50d0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem>::Add(var<u1>)
0x50d5  ldarg.3
0x50d6  ldc.i4.1
0x50d7  stind.i1
0x50d8  ldarg.2
0x50d9  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleSettings::get_ContinueOnError()
0x50de  brfalse.s loc_50F4
0x50e0  ldloc.s  9
0x50e2  ldloc.s  0xA
0x50e4  ldloc.s  7
0x50e6  ldloc.s  0xA
0x50e8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem::get_Fault()
0x50ed  call     void Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::UpdateRowVersions(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest organizationRequest, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem responseObject, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> entityRowVersions, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault organizationServiceFault)
0x50f2  leave.s  loc_5108
0x50f4  ldloc.s  9
0x50f6  ldloc.s  0xA
0x50f8  ldloc.s  7
0x50fa  ldloc.s  0xA
0x50fc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem::get_Fault()
0x5101  call     void Microsoft.Crm.Extensibility.ExecuteMultipleProcessor::UpdateRowVersions(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest organizationRequest, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteMultipleResponseItem responseObject, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> entityRowVersions, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault organizationServiceFault)
0x5106  leave.s  loc_5122
0x5108  ldloc.s  8
0x510a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x510f  brtrue   loc_4FAE
0x5114  leave.s  loc_5122
0x5116  ldloc.s  8
0x5118  brfalse.s loc_5121
0x511a  ldloc.s  8
0x511c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5121  endfinally
0x5122  ldloc.s  5
0x5124  ret
```
