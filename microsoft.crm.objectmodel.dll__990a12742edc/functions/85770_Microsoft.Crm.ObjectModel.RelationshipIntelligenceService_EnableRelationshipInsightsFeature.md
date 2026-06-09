# Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::EnableRelationshipInsightsFeature

- ea: `0x85770`
- end: `0x85a4e`
- name: `Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::EnableRelationshipInsightsFeature`
- size: `734`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x83720`
- `0x85f80`

## callees

- `0x82a10`
- `0x834c0`
- `0x83620`
- `0x85170`
- `0x85310`
- `0x85370`
- `0x85770`
- `0x85e90`
- `0x862d0`
- `0x862e0`
- `0x86340`
- `0x86380`

## string_xrefs

- `0x8587b`: `Deserialized the requestdata for organization Id {0}.`
- `0x858b5`: `Invalid configData passed in request for organization Id :{0}`
- `0x858e8`: `Invalid configData passed in request`
- `0x858f2`: `Invalid configData passed in request`
- `0x85933`: `PostData To RelationshipIntelligence Service for enabling {0} feature started for organization Id {1} with deployment type {2}.`
- `0x85975`: `PostData To RelationshipIntelligence Service for enabling {0} feature started for organization Id {1} with deployment type {2}.`
- `0x859b7`: `PostData To RelationshipIntelligence Service for enabling {0} feature completed for organization Id {1} with deployment type {2}.`
- `0x859f9`: `PostData To RelationshipIntelligence Service for enabling {0} feature completed for organization Id {1} with deployment type {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x85770  ldarg.0
0x85771  ldarg.3
0x85772  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::GetTenantId(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x85777  stloc.0
0x85778  ldarg.0
0x85779  call     instance bool Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::IsCrmOnline()
0x8577e  brtrue.s loc_85795
0x85780  ldc.i4   0x80044276
0x85785  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x8578a  ldc.i4   0x80044276
0x8578f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x85794  throw
0x85795  ldarg.0
0x85796  ldarg.3
0x85797  call     instance bool Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::IsSystemUserOrAdministrator(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8579c  brtrue.s loc_857D7
0x8579e  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x857a3  ldarg.3
0x857a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x857a9  ldstr    aEnablerelation// "EnableRelationshipInsightsFeature"
0x857ae  ldc.i4   0x80044270
0x857b3  ldc.i4   0x80044270
0x857b8  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x857bd  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogError(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int32 CrmErrorCode, string ErrorDetails)
0x857c2  ldc.i4   0x80044270
0x857c7  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x857cc  ldc.i4   0x80044270
0x857d1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x857d6  throw
0x857d7  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x857dc  stloc.1
0x857dd  call     int32 [Microsoft.Crm]Microsoft.Crm.EndpointUtility::GetEndpointType()
0x857e2  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::GetExternalEndpointProvider(int32)
0x857e7  ldarg.3
0x857e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x857ed  callvirt instance class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::GetWebApplicationUrl(valuetype [mscorlib]System.Guid)
0x857f2  stloc.2
0x857f3  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x857f8  ldarg.3
0x857f9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x857fe  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationName(valuetype [mscorlib]System.Guid)
0x85803  stloc.3
0x85804  ldtoken  Microsoft.Crm.ObjectModel.RelationshipIntelligenceFeatureType
0x85809  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8580e  ldarg.1
0x8580f  box      [mscorlib]System.Int32
0x85814  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x85819  brtrue.s loc_85854
0x8581b  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x85820  ldarg.3
0x85821  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85826  ldstr    aEnablerelation// "EnableRelationshipInsightsFeature"
0x8582b  ldc.i4   0x80044279
0x85830  ldc.i4   0x80044272
0x85835  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x8583a  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogError(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int32 CrmErrorCode, string ErrorDetails)
0x8583f  ldc.i4   0x80044272
0x85844  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x85849  ldc.i4   0x80044272
0x8584e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x85853  throw
0x85854  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85859  stloc.s  4
0x8585b  ldarg.2
0x8585c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x85861  brtrue   loc_85902
0x85866  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x8586b  ldarg.2
0x8586c  call     T0x2B00014A
0x85871  stloc.s  4
0x85873  ldarg.3
0x85874  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85879  ldc.i4.s 0x14
0x8587b  ldstr    aDeserializedTh// "Deserialized the requestdata for organi"...
0x85880  ldc.i4.1
0x85881  newarr   [mscorlib]System.Object
0x85886  dup
0x85887  ldc.i4.0
0x85888  ldarg.3
0x85889  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8588e  box      [mscorlib]System.Guid
0x85893  stelem.ref
0x85894  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x85899  ldloc.s  4
0x8589b  ldstr    aCrmtenantid// "CrmTenantId"
0x858a0  ldloc.0
0x858a1  box      [mscorlib]System.Guid
0x858a6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x858ab  leave.s  loc_85902
0x858ad  ldarg.3
0x858ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x858b3  ldc.i4.s 0x14
0x858b5  ldstr    aInvalidConfigd// "Invalid configData passed in request fo"...
0x858ba  ldc.i4.1
0x858bb  newarr   [mscorlib]System.Object
0x858c0  dup
0x858c1  ldc.i4.0
0x858c2  ldarg.3
0x858c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x858c8  box      [mscorlib]System.Guid
0x858cd  stelem.ref
0x858ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x858d3  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x858d8  ldarg.3
0x858d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x858de  ldstr    aEnablerelation// "EnableRelationshipInsightsFeature"
0x858e3  ldc.i4   0x80044271
0x858e8  ldstr    aInvalidConfigd_0// "Invalid configData passed in request"
0x858ed  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogError(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int32 CrmErrorCode, string ErrorDetails)
0x858f2  ldstr    aInvalidConfigd_0// "Invalid configData passed in request"
0x858f7  ldc.i4   0x80044271
0x858fc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x85901  throw
0x85902  ldarg.3
0x85903  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85908  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x8590d  ldarg.1
0x8590e  ldloc.3
0x8590f  ldloc.2
0x85910  ldloc.s  4
0x85912  newobj   instance void Microsoft.Crm.ObjectModel.RiOrganizationRequest::.ctor(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid requestId, valuetype Microsoft.Crm.ObjectModel.RelationshipIntelligenceFeatureType featureType, string organizationUniqueName, class [System]System.Uri organizationUrl, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> requestData)
0x85917  stloc.s  5
0x85919  ldarg.1
0x8591a  stloc.s  7
0x8591c  ldloca.s 7
0x8591e  constrained. Microsoft.Crm.ObjectModel.RelationshipIntelligenceFeatureType
0x85924  callvirt instance string [mscorlib]System.Object::ToString()
0x85929  stloc.s  6
0x8592b  ldarg.3
0x8592c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85931  ldc.i4.s 0x14
0x85933  ldstr    aPostdataToRela_7// "PostData To RelationshipIntelligence Se"...
0x85938  ldc.i4.3
0x85939  newarr   [mscorlib]System.Object
0x8593e  dup
0x8593f  ldc.i4.0
0x85940  ldloc.s  6
0x85942  stelem.ref
0x85943  dup
0x85944  ldc.i4.1
0x85945  ldarg.3
0x85946  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8594b  box      [mscorlib]System.Guid
0x85950  stelem.ref
0x85951  dup
0x85952  ldc.i4.2
0x85953  ldarg.s  4
0x85955  box      AzureApplicationType
0x8595a  stelem.ref
0x8595b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x85960  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x85965  ldarg.3
0x85966  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8596b  ldstr    aRelationshipin// "RelationshipIntelligenceInformational"
0x85970  ldstr    aEnablerelation// "EnableRelationshipInsightsFeature"
0x85975  ldstr    aPostdataToRela_7// "PostData To RelationshipIntelligence Se"...
0x8597a  ldloc.s  6
0x8597c  ldarg.3
0x8597d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85982  box      [mscorlib]System.Guid
0x85987  ldarg.s  4
0x85989  box      AzureApplicationType
0x8598e  call     string [mscorlib]System.String::Format(string, object, object, object)
0x85993  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogInformation(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string EventDetails)
0x85998  newobj   instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceOdataWrapper::.ctor()
0x8599d  ldarg.0
0x8599e  ldc.i4.3
0x8599f  ldarg.3
0x859a0  ldarg.s  4
0x859a2  call     instance string Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::GetRelationshipInsightsUrl(valuetype RequestType requestType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] valuetype AzureApplicationType type)
0x859a7  ldloc.s  5
0x859a9  ldarg.3
0x859aa  call     instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceOdataWrapper::PostDataToRelationshipIntelligence(string requestUrl, class Microsoft.Crm.ObjectModel.RiOrganizationRequest organizationRequest, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x859af  ldarg.3
0x859b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x859b5  ldc.i4.s 0x14
0x859b7  ldstr    aPostdataToRela_8// "PostData To RelationshipIntelligence Se"...
0x859bc  ldc.i4.3
0x859bd  newarr   [mscorlib]System.Object
0x859c2  dup
0x859c3  ldc.i4.0
0x859c4  ldloc.s  6
0x859c6  stelem.ref
0x859c7  dup
0x859c8  ldc.i4.1
0x859c9  ldarg.3
0x859ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x859cf  box      [mscorlib]System.Guid
0x859d4  stelem.ref
0x859d5  dup
0x859d6  ldc.i4.2
0x859d7  ldarg.s  4
0x859d9  box      AzureApplicationType
0x859de  stelem.ref
0x859df  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x859e4  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x859e9  ldarg.3
0x859ea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x859ef  ldstr    aRelationshipin// "RelationshipIntelligenceInformational"
0x859f4  ldstr    aEnablerelation// "EnableRelationshipInsightsFeature"
0x859f9  ldstr    aPostdataToRela_8// "PostData To RelationshipIntelligence Se"...
0x859fe  ldloc.s  6
0x85a00  ldarg.3
0x85a01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85a06  box      [mscorlib]System.Guid
0x85a0b  ldarg.s  4
0x85a0d  box      AzureApplicationType
0x85a12  call     string [mscorlib]System.String::Format(string, object, object, object)
0x85a17  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogInformation(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string EventDetails)
0x85a1c  ldloc.1
0x85a1d  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x85a22  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x85a27  ldarg.3
0x85a28  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85a2d  ldstr    aTimetakenforen_0// "TimeTakenForEnableRelationshipInsightsF"...
0x85a32  ldarg.1
0x85a33  box      Microsoft.Crm.ObjectModel.RelationshipIntelligenceFeatureType
0x85a38  call     string [mscorlib]System.String::Concat(object, object)
0x85a3d  ldstr    aEnablerelation// "EnableRelationshipInsightsFeature"
0x85a42  ldloc.1
0x85a43  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x85a48  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogTimeTakenInformation(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, int64 TimeTaken)
0x85a4d  ret
```
