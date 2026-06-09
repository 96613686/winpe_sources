# Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::GetRelationshipInsightsUrl

- ea: `0x85170`
- end: `0x85308`
- name: `Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::GetRelationshipInsightsUrl`
- size: `408`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x83bc0`
- `0x83e60`
- `0x85390`
- `0x854e0`
- `0x85770`
- `0x85a50`
- `0x85ca0`

## callees

- `0x84b90`
- `0x85170`
- `0x862d0`
- `0x862e0`
- `0x86560`
- `0x86590`

## string_xrefs

- `0x85209`: `api/ProvisioningService/ProvisionRelationshipIntelligence`
- `0x85211`: `api/ProvisioningService/DeprovisionRelationshipIntelligence`
- `0x85219`: `api/ProvisioningService/EnableRelationshipIntelligenceFeature`
- `0x85221`: `api/ProvisioningService/DisableRelationshipIntelligenceFeature`
- `0x85229`: `api/ProvisioningService/UpdateRelationshipIntelligenceTenantInfo`
- `0x85231`: `api/ProvisioningService/UpdateOrganization`
- `0x85239`: `api/ProvisioningService/UpdateOrgData`
- `0x85254`: `Fetching RITenantInfo completed for organization Id {0} with deployment type {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x85170  ldarg.2
0x85171  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85176  ldc.i4.s 0x14
0x85178  ldstr    aFetchingRitena// "Fetching RITenantInfo started for organ"...
0x8517d  ldc.i4.2
0x8517e  newarr   [mscorlib]System.Object
0x85183  dup
0x85184  ldc.i4.0
0x85185  ldarg.2
0x85186  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8518b  box      [mscorlib]System.Guid
0x85190  stelem.ref
0x85191  dup
0x85192  ldc.i4.1
0x85193  ldarg.3
0x85194  box      AzureApplicationType
0x85199  stelem.ref
0x8519a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8519f  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x851a4  ldarg.2
0x851a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x851aa  ldstr    aGetritenantinf// "GetRITenantInfoStarted"
0x851af  ldstr    aGetrelationshi_0// "GetRelationshipInsightsUrl"
0x851b4  ldstr    aFetchingRitena_0// "Fetching RITenantInfo Started for organ"...
0x851b9  ldarg.2
0x851ba  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x851bf  box      [mscorlib]System.Guid
0x851c4  ldarg.3
0x851c5  box      AzureApplicationType
0x851ca  call     string [mscorlib]System.String::Format(string, object, object)
0x851cf  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::GetRITenantInfoStarted(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string Message)
0x851d4  ldarg.0
0x851d5  ldarg.2
0x851d6  ldarg.3
0x851d7  call     instance string Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::GetRelationshipInsightsBaseUrl(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] valuetype AzureApplicationType type)
0x851dc  stloc.0
0x851dd  ldsfld   string [mscorlib]System.String::Empty
0x851e2  stloc.1
0x851e3  ldarg.1
0x851e4  ldc.i4.1
0x851e5  sub
0x851e6  switch   loc_85209, loc_85211, loc_85219, loc_85221, loc_85229, loc_85231, loc_85239
0x85207  br.s     loc_8523F
0x85209  ldstr    aApiProvisionin// "api/ProvisioningService/ProvisionRelati"...
0x8520e  stloc.1
0x8520f  br.s     loc_8523F
0x85211  ldstr    aApiProvisionin_0// "api/ProvisioningService/DeprovisionRela"...
0x85216  stloc.1
0x85217  br.s     loc_8523F
0x85219  ldstr    aApiProvisionin_1// "api/ProvisioningService/EnableRelations"...
0x8521e  stloc.1
0x8521f  br.s     loc_8523F
0x85221  ldstr    aApiProvisionin_2// "api/ProvisioningService/DisableRelation"...
0x85226  stloc.1
0x85227  br.s     loc_8523F
0x85229  ldstr    aApiProvisionin_3// "api/ProvisioningService/UpdateRelations"...
0x8522e  stloc.1
0x8522f  br.s     loc_8523F
0x85231  ldstr    aApiProvisionin_4// "api/ProvisioningService/UpdateOrganizat"...
0x85236  stloc.1
0x85237  br.s     loc_8523F
0x85239  ldstr    aApiProvisionin_5// "api/ProvisioningService/UpdateOrgData"
0x8523e  stloc.1
0x8523f  ldstr    a01_11// "{0}/{1}"
0x85244  ldloc.0
0x85245  ldloc.1
0x85246  call     string [mscorlib]System.String::Format(string, object, object)
0x8524b  stloc.2
0x8524c  ldarg.2
0x8524d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85252  ldc.i4.s 0x14
0x85254  ldstr    aFetchingRitena_1// "Fetching RITenantInfo completed for org"...
0x85259  ldc.i4.2
0x8525a  newarr   [mscorlib]System.Object
0x8525f  dup
0x85260  ldc.i4.0
0x85261  ldarg.2
0x85262  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85267  box      [mscorlib]System.Guid
0x8526c  stelem.ref
0x8526d  dup
0x8526e  ldc.i4.1
0x8526f  ldarg.3
0x85270  box      AzureApplicationType
0x85275  stelem.ref
0x85276  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8527b  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x85280  ldarg.2
0x85281  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85286  ldstr    aRelationshipin_5// "RelationshipInsightsUrl"
0x8528b  ldstr    aGetrelationshi_0// "GetRelationshipInsightsUrl"
0x85290  ldloc.2
0x85291  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogInformation(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string EventDetails)
0x85296  ldloc.2
0x85297  stloc.3
0x85298  leave.s  loc_85306
0x8529a  ldarg.2
0x8529b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x852a0  ldc.i4.s 0x14
0x852a2  ldstr    aFetchingRitena_2// "Fetching RITenantInfo Failed for organi"...
0x852a7  ldc.i4.2
0x852a8  newarr   [mscorlib]System.Object
0x852ad  dup
0x852ae  ldc.i4.0
0x852af  ldarg.2
0x852b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x852b5  box      [mscorlib]System.Guid
0x852ba  stelem.ref
0x852bb  dup
0x852bc  ldc.i4.1
0x852bd  ldarg.3
0x852be  box      AzureApplicationType
0x852c3  stelem.ref
0x852c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x852c9  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x852ce  ldarg.2
0x852cf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x852d4  ldstr    aGetritenantinf_0// "GetRITenantInfoFailed"
0x852d9  ldstr    aGetrelationshi_0// "GetRelationshipInsightsUrl"
0x852de  ldstr    aFetchingRitena_2// "Fetching RITenantInfo Failed for organi"...
0x852e3  ldarg.2
0x852e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x852e9  box      [mscorlib]System.Guid
0x852ee  ldarg.3
0x852ef  box      AzureApplicationType
0x852f4  call     string [mscorlib]System.String::Format(string, object, object)
0x852f9  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::GetRITenantInfoFailed(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string Message)
0x852fe  ldstr    asc_24F76C// ""
0x85303  stloc.3
0x85304  leave.s  loc_85306
0x85306  ldloc.3
0x85307  ret
```
