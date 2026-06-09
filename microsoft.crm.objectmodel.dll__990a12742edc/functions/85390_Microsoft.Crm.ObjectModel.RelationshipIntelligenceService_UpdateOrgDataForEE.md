# Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::UpdateOrgDataForEE

- ea: `0x85390`
- end: `0x854dc`
- name: `Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::UpdateOrgDataForEE`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x84430`

## callees

- `0x82a40`
- `0x834c0`
- `0x85170`
- `0x85310`
- `0x85370`
- `0x85390`
- `0x862d0`
- `0x862e0`
- `0x86340`
- `0x86380`

## string_xrefs

- `0x853c1`: `UpdateOrgDataForEE`
- `0x8542b`: `UpdateOrgDataForEE`
- `0x85496`: `UpdateOrgDataForEE`
- `0x854cb`: `UpdateOrgDataForEE`
- `0x853fd`: `PostData To RelationshipIntelligence Service started for Updating Org Data for organization Id {0} with UseThirdPartyAuth = true.`
- `0x85430`: `PostData To RelationshipIntelligence Service for updating org data started for organization Id {0} with UseThirdPartyAuth = true.`
- `0x85468`: `PostData To RelationshipIntelligence Service completed for Updating Org Data for organization Id {0} with UseThirdPartyAuth = true`
- `0x8549b`: `PostData To RelationshipIntelligence Service completed for Updating Org Data for organization Id {0} with UseThirdPartyAuth = true.`
- `0x854c6`: `TimeTakenForUpdateOrgDataForEERequest`

## pseudocode

```c

```

## disassembly

```asm
0x85390  ldarg.0
0x85391  call     instance bool Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::IsCrmOnline()
0x85396  brtrue.s loc_853AD
0x85398  ldc.i4   0x80044276
0x8539d  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x853a2  ldc.i4   0x80044276
0x853a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x853ac  throw
0x853ad  ldarg.0
0x853ae  ldarg.2
0x853af  call     instance bool Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::IsSystemUserOrAdministrator(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x853b4  brtrue.s loc_853EF
0x853b6  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x853bb  ldarg.2
0x853bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x853c1  ldstr    aUpdateorgdataf// "UpdateOrgDataForEE"
0x853c6  ldc.i4   0x80044270
0x853cb  ldc.i4   0x80044270
0x853d0  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x853d5  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogError(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int32 CrmErrorCode, string ErrorDetails)
0x853da  ldc.i4   0x80044270
0x853df  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x853e4  ldc.i4   0x80044270
0x853e9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x853ee  throw
0x853ef  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x853f4  stloc.0
0x853f5  ldarg.2
0x853f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x853fb  ldc.i4.s 0x14
0x853fd  ldstr    aPostdataToRela// "PostData To RelationshipIntelligence Se"...
0x85402  ldc.i4.1
0x85403  newarr   [mscorlib]System.Object
0x85408  dup
0x85409  ldc.i4.0
0x8540a  ldarg.2
0x8540b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85410  box      [mscorlib]System.Guid
0x85415  stelem.ref
0x85416  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8541b  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x85420  ldarg.2
0x85421  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85426  ldstr    aRelationshipin// "RelationshipIntelligenceInformational"
0x8542b  ldstr    aUpdateorgdataf// "UpdateOrgDataForEE"
0x85430  ldstr    aPostdataToRela_0// "PostData To RelationshipIntelligence Se"...
0x85435  ldarg.2
0x85436  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8543b  box      [mscorlib]System.Guid
0x85440  call     string [mscorlib]System.String::Format(string, object)
0x85445  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogInformation(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string EventDetails)
0x8544a  newobj   instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceOdataWrapper::.ctor()
0x8544f  ldarg.0
0x85450  ldc.i4.7
0x85451  ldarg.2
0x85452  ldc.i4.s 0xE
0x85454  call     instance string Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::GetRelationshipInsightsUrl(valuetype RequestType requestType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] valuetype AzureApplicationType type)
0x85459  ldarg.1
0x8545a  ldarg.2
0x8545b  call     instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceOdataWrapper::PostDataToRelationshipIntelligence(string requestUrl, string requestData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x85460  ldarg.2
0x85461  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85466  ldc.i4.s 0x14
0x85468  ldstr    aPostdataToRela_1// "PostData To RelationshipIntelligence Se"...
0x8546d  ldc.i4.1
0x8546e  newarr   [mscorlib]System.Object
0x85473  dup
0x85474  ldc.i4.0
0x85475  ldarg.2
0x85476  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8547b  box      [mscorlib]System.Guid
0x85480  stelem.ref
0x85481  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x85486  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x8548b  ldarg.2
0x8548c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x85491  ldstr    aRelationshipin// "RelationshipIntelligenceInformational"
0x85496  ldstr    aUpdateorgdataf// "UpdateOrgDataForEE"
0x8549b  ldstr    aPostdataToRela_2// "PostData To RelationshipIntelligence Se"...
0x854a0  ldarg.2
0x854a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x854a6  box      [mscorlib]System.Guid
0x854ab  call     string [mscorlib]System.String::Format(string, object)
0x854b0  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogInformation(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string EventDetails)
0x854b5  ldloc.0
0x854b6  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x854bb  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x854c0  ldarg.2
0x854c1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x854c6  ldstr    aTimetakenforup_0// "TimeTakenForUpdateOrgDataForEERequest"
0x854cb  ldstr    aUpdateorgdataf// "UpdateOrgDataForEE"
0x854d0  ldloc.0
0x854d1  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x854d6  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogTimeTakenInformation(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, int64 TimeTaken)
0x854db  ret
```
