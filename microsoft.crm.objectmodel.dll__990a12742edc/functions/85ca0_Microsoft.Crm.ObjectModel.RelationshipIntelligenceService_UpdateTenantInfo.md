# Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::UpdateTenantInfo

- ea: `0x85ca0`
- end: `0x85e81`
- name: `Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::UpdateTenantInfo`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x84810`

## callees

- `0x82a10`
- `0x834c0`
- `0x83620`
- `0x85170`
- `0x85310`
- `0x85370`
- `0x85ca0`
- `0x862d0`
- `0x862e0`
- `0x86340`
- `0x86380`

## string_xrefs

- `0x85cd3`: `UpdateTenantInfo`
- `0x85db3`: `UpdateTenantInfo`
- `0x85e02`: `UpdateTenantInfo`
- `0x85e70`: `UpdateTenantInfo`
- `0x85d7a`: `Starting posting a request to RI service for updating the tenant info for organization Id {0} with deployment type {1}.`
- `0x85db8`: `Starting posting a request to RI service for updating the tenant info for organization Id {0} with deployment type {1}.`
- `0x85e07`: `Successfully posted a request to RI service for updating the tenant info for organization Id {0} with deployment type {1}.`
- `0x85e37`: `Successfully posted a request to RI service for updating the tenant info for organization Id {0} with deployment type {1}.`
- `0x85e6b`: `TimeTakenForUpdateTenantInfoRequest`

## pseudocode

```c

```

## disassembly

```asm
0x85ca0  ldarg.0
0x85ca1  call     instance bool Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::IsCrmOnline()
0x85ca6  brtrue.s loc_85CBD
0x85ca8  ldc.i4   0x80044276
0x85cad  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x85cb2  ldc.i4   0x80044276
0x85cb7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x85cbc  throw
0x85cbd  ldarg.0
0x85cbe  ldarg.s  4
0x85cc0  call     instance bool Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::IsSystemUserOrAdministrator(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x85cc5  brtrue.s loc_85D01
0x85cc7  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x85ccc  ldarg.s  4
0x85cce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85cd3  ldstr    aUpdatetenantin// "UpdateTenantInfo"
0x85cd8  ldc.i4   0x80044270
0x85cdd  ldc.i4   0x80044270
0x85ce2  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x85ce7  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogError(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int32 CrmErrorCode, string ErrorDetails)
0x85cec  ldc.i4   0x80044270
0x85cf1  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x85cf6  ldc.i4   0x80044270
0x85cfb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x85d00  throw
0x85d01  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x85d06  stloc.0
0x85d07  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85d0c  stloc.1
0x85d0d  ldloc.1
0x85d0e  ldstr    aHubname// "HubName"
0x85d13  ldarg.1
0x85d14  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85d19  ldloc.1
0x85d1a  ldstr    aPrimarykey// "PrimaryKey"
0x85d1f  ldarg.2
0x85d20  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85d25  call     int32 [Microsoft.Crm]Microsoft.Crm.EndpointUtility::GetEndpointType()
0x85d2a  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::GetExternalEndpointProvider(int32)
0x85d2f  ldarg.s  4
0x85d31  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85d36  callvirt instance class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::GetWebApplicationUrl(valuetype [mscorlib]System.Guid)
0x85d3b  stloc.2
0x85d3c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x85d41  ldarg.s  4
0x85d43  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85d48  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationName(valuetype [mscorlib]System.Guid)
0x85d4d  stloc.3
0x85d4e  ldarg.3
0x85d4f  ldc.i4.s 0x10
0x85d51  beq.s    loc_85D56
0x85d53  ldc.i4.2
0x85d54  br.s     loc_85D57
0x85d56  ldc.i4.1
0x85d57  stloc.s  4
0x85d59  ldarg.s  4
0x85d5b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85d60  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x85d65  ldloc.s  4
0x85d67  ldloc.3
0x85d68  ldloc.2
0x85d69  ldloc.1
0x85d6a  newobj   instance void Microsoft.Crm.ObjectModel.RiOrganizationRequest::.ctor(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid requestId, valuetype Microsoft.Crm.ObjectModel.RelationshipIntelligenceFeatureType featureType, string organizationUniqueName, class [System]System.Uri organizationUrl, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> requestData)
0x85d6f  stloc.s  5
0x85d71  ldarg.s  4
0x85d73  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85d78  ldc.i4.s 0x14
0x85d7a  ldstr    aStartingPostin_0// "Starting posting a request to RI servic"...
0x85d7f  ldc.i4.2
0x85d80  newarr   [mscorlib]System.Object
0x85d85  dup
0x85d86  ldc.i4.0
0x85d87  ldarg.s  4
0x85d89  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85d8e  box      [mscorlib]System.Guid
0x85d93  stelem.ref
0x85d94  dup
0x85d95  ldc.i4.1
0x85d96  ldarg.3
0x85d97  box      AzureApplicationType
0x85d9c  stelem.ref
0x85d9d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x85da2  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x85da7  ldarg.s  4
0x85da9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85dae  ldstr    aRelationshipin// "RelationshipIntelligenceInformational"
0x85db3  ldstr    aUpdatetenantin// "UpdateTenantInfo"
0x85db8  ldstr    aStartingPostin_0// "Starting posting a request to RI servic"...
0x85dbd  ldarg.s  4
0x85dbf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85dc4  box      [mscorlib]System.Guid
0x85dc9  ldarg.3
0x85dca  box      AzureApplicationType
0x85dcf  call     string [mscorlib]System.String::Format(string, object, object)
0x85dd4  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogInformation(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string EventDetails)
0x85dd9  newobj   instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceOdataWrapper::.ctor()
0x85dde  ldarg.0
0x85ddf  ldc.i4.5
0x85de0  ldarg.s  4
0x85de2  ldarg.3
0x85de3  call     instance string Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::GetRelationshipInsightsUrl(valuetype RequestType requestType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] valuetype AzureApplicationType type)
0x85de8  ldloc.s  5
0x85dea  ldarg.s  4
0x85dec  call     instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceOdataWrapper::PostDataToRelationshipIntelligence(string requestUrl, class Microsoft.Crm.ObjectModel.RiOrganizationRequest organizationRequest, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x85df1  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x85df6  ldarg.s  4
0x85df8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85dfd  ldstr    aRelationshipin// "RelationshipIntelligenceInformational"
0x85e02  ldstr    aUpdatetenantin// "UpdateTenantInfo"
0x85e07  ldstr    aSuccessfullyPo_2// "Successfully posted a request to RI ser"...
0x85e0c  ldarg.s  4
0x85e0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85e13  box      [mscorlib]System.Guid
0x85e18  ldarg.3
0x85e19  box      AzureApplicationType
0x85e1e  call     string [mscorlib]System.String::Format(string, object, object)
0x85e23  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogInformation(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string EventDetails)
0x85e28  ldloc.0
0x85e29  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x85e2e  ldarg.s  4
0x85e30  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85e35  ldc.i4.s 0x14
0x85e37  ldstr    aSuccessfullyPo_2// "Successfully posted a request to RI ser"...
0x85e3c  ldc.i4.2
0x85e3d  newarr   [mscorlib]System.Object
0x85e42  dup
0x85e43  ldc.i4.0
0x85e44  ldarg.s  4
0x85e46  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85e4b  box      [mscorlib]System.Guid
0x85e50  stelem.ref
0x85e51  dup
0x85e52  ldc.i4.1
0x85e53  ldarg.3
0x85e54  box      AzureApplicationType
0x85e59  stelem.ref
0x85e5a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x85e5f  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x85e64  ldarg.s  4
0x85e66  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85e6b  ldstr    aTimetakenforup_1// "TimeTakenForUpdateTenantInfoRequest"
0x85e70  ldstr    aUpdatetenantin// "UpdateTenantInfo"
0x85e75  ldloc.0
0x85e76  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x85e7b  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogTimeTakenInformation(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, int64 TimeTaken)
0x85e80  ret
```
