# Microsoft.Crm.Extensibility.ExecuteTransactionProcessor::ExecuteTransaction

- ea: `0x5430`
- end: `0x560a`
- name: `Microsoft.Crm.Extensibility.ExecuteTransactionProcessor::ExecuteTransaction`
- size: `474`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x5430`
- `0x5610`
- `0x5660`
- `0xace0`
- `0xb1b0`
- `0xb1f0`
- `0xb230`

## string_xrefs

- `0x5579`: `RequestName : {0} Request inside an ExecuteTransactionRequest, RequestId : {1}, CorrelationId : {2}`

## pseudocode

```c

```

## disassembly

```asm
0x5430  ldarg.1
0x5431  ldstr    aRequests// "requests"
0x5436  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x543b  ldarg.2
0x543c  ldstr    aContext// "context"
0x5441  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5446  ldarg.1
0x5447  call     void Microsoft.Crm.Extensibility.ExecuteTransactionProcessor::ThrowIfAnyRequestUnsupported(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequestCollection requests)
0x544c  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0x5451  stloc.0
0x5452  ldarg.1
0x5453  ldloc.0
0x5454  call     void Microsoft.Crm.Extensibility.ExecuteTransactionProcessor::ValidateRequestBatchSize(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequestCollection requests, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth)
0x5459  ldloc.0
0x545a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x545f  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.DisasterRecoveryUtility::CheckIfIncorrectDatacenter(valuetype [mscorlib]System.Guid)
0x5464  ldloc.0
0x5465  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::GetTargetUserId(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth)
0x546a  stloc.1
0x546b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::GetTargetCallerRegardingObject()
0x5470  stloc.2
0x5471  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserType Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::GetTargetUserType()
0x5476  stloc.3
0x5477  ldloca.s 4
0x5479  ldc.i4.1
0x547a  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x547f  ldarg.2
0x5480  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x5485  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x548a  ldstr    aReturnresponse// "ReturnResponses"
0x548f  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5494  brfalse.s loc_54CC
0x5496  ldloca.s 4
0x5498  ldarg.2
0x5499  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x549e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x54a3  ldstr    aReturnresponse// "ReturnResponses"
0x54a8  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x54ad  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x54b2  stloc.s  7
0x54b4  ldloca.s 7
0x54b6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x54bb  brtrue.s loc_54C0
0x54bd  ldc.i4.1
0x54be  br.s     loc_54C7
0x54c0  ldloca.s 7
0x54c2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x54c7  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x54cc  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponseCollection::.ctor()
0x54d1  stloc.s  5
0x54d3  ldnull
0x54d4  stloc.s  6
0x54d6  ldc.i4.0
0x54d7  stloc.s  8
0x54d9  br       loc_55FA
0x54de  ldarg.1
0x54df  ldloc.s  8
0x54e1  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest>::get_Item(!!T0)
0x54e6  stloc.s  9
0x54e8  ldloc.s  9
0x54ea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54ef  ldstr    aRequestIndexed// "Request indexed at {0} in ExecuteTransa"...
0x54f4  ldc.i4.1
0x54f5  newarr   [mscorlib]System.Object
0x54fa  dup
0x54fb  ldc.i4.0
0x54fc  ldloc.s  8
0x54fe  box      [mscorlib]System.Int32
0x5503  stelem.ref
0x5504  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5509  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x550e  ldarg.2
0x550f  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0x5514  ldc.i4.0
0x5515  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_Depth(int32)
0x551a  ldloca.s 4
0x551c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5521  brfalse.s loc_554B
0x5523  ldloc.s  9
0x5525  ldarg.2
0x5526  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0x552b  ldarg.2
0x552c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerOriginToken()
0x5531  ldc.i4.0
0x5532  ldloc.0
0x5533  ldloc.1
0x5534  ldloc.2
0x5535  ldloc.3
0x5536  ldarg.2
0x5537  ldc.i4.1
0x5538  ldc.i4.0
0x5539  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::ExecuteRequest(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken callerOriginToken, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType serviceType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid targetUserId, valuetype [mscorlib]System.Guid targetCallerRegardingObjectId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserType targetUserType, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context, bool returnResponse, bool checkAdminMode)
0x553e  stloc.s  6
0x5540  ldloc.s  5
0x5542  ldloc.s  6
0x5544  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse>::Add(var<u1>)
0x5549  br.s     loc_5567
0x554b  ldloc.s  9
0x554d  ldarg.2
0x554e  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0x5553  ldarg.2
0x5554  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerOriginToken()
0x5559  ldc.i4.0
0x555a  ldloc.0
0x555b  ldloc.1
0x555c  ldloc.2
0x555d  ldloc.3
0x555e  ldarg.2
0x555f  ldc.i4.0
0x5560  ldc.i4.0
0x5561  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::ExecuteRequest(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken callerOriginToken, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType serviceType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid targetUserId, valuetype [mscorlib]System.Guid targetCallerRegardingObjectId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserType targetUserType, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context, bool returnResponse, bool checkAdminMode)
0x5566  pop
0x5567  leave    loc_55F4
0x556c  stloc.s  0xA
0x556e  ldloc.s  0xA
0x5570  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Watson.ExceptionManager::IsUnknownException(class [mscorlib]System.Exception)
0x5575  brfalse.s loc_55B6
0x5577  ldloc.s  0xA
0x5579  ldstr    aRequestname0Re// "RequestName : {0} Request inside an Exe"...
0x557e  ldc.i4.3
0x557f  newarr   [mscorlib]System.Object
0x5584  dup
0x5585  ldc.i4.0
0x5586  ldloc.s  9
0x5588  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x558d  stelem.ref
0x558e  dup
0x558f  ldc.i4.1
0x5590  ldloc.s  9
0x5592  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestId()
0x5597  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x559c  stelem.ref
0x559d  dup
0x559e  ldc.i4.2
0x559f  ldarg.2
0x55a0  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0x55a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_CorrelationId()
0x55aa  box      [mscorlib]System.Guid
0x55af  stelem.ref
0x55b0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Watson.ExceptionManager::ReportException(class [mscorlib]System.Exception, string, object[])
0x55b5  pop
0x55b6  ldloc.s  0xA
0x55b8  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.FaultHelper::ConvertToFault(class [mscorlib]System.Exception)
0x55bd  stloc.s  0xB
0x55bf  ldloc.s  0xB
0x55c1  brfalse.s loc_55F2
0x55c3  ldloc.s  0xB
0x55c5  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x55ca  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteTransactionFault [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.FaultHelper::ConvertToExecuteTransactionFault(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault)
0x55cf  dup
0x55d0  ldloc.s  8
0x55d2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ExecuteTransactionFault::set_FaultedRequestIndex(int32)
0x55d7  ldloc.s  0xB
0x55d9  callvirt instance class [System.ServiceModel]System.ServiceModel.FaultReason [System.ServiceModel]System.ServiceModel.FaultException::get_Reason()
0x55de  ldloc.s  0xB
0x55e0  callvirt instance class [System.ServiceModel]System.ServiceModel.FaultCode [System.ServiceModel]System.ServiceModel.FaultException::get_Code()
0x55e5  ldloc.s  0xB
0x55e7  callvirt instance string [System.ServiceModel]System.ServiceModel.FaultException::get_Action()
0x55ec  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::.ctor(var<u1>, !!T0, class [System.ServiceModel]System.ServiceModel.FaultReason, class [System.ServiceModel]System.ServiceModel.FaultCode)
0x55f1  throw
0x55f2  rethrow
0x55f4  ldloc.s  8
0x55f6  ldc.i4.1
0x55f7  add
0x55f8  stloc.s  8
0x55fa  ldloc.s  8
0x55fc  ldarg.1
0x55fd  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest>::get_Count()
0x5602  blt      loc_54DE
0x5607  ldloc.s  5
0x5609  ret
```
