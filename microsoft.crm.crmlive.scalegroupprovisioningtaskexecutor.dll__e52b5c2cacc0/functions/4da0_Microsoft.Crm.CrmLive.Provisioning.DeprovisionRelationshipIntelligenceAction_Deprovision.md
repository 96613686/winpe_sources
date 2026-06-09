# Microsoft.Crm.CrmLive.Provisioning.DeprovisionRelationshipIntelligenceAction::Deprovision

- ea: `0x4da0`
- end: `0x4e5b`
- name: `Microsoft.Crm.CrmLive.Provisioning.DeprovisionRelationshipIntelligenceAction::Deprovision`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x4da0`
- `0x64b0`
- `0x91b0`
- `0x2f020`
- `0x2f030`
- `0x2f060`

## string_xrefs

- `0x4de7`: `Deprovisioning Relationship Insights service in DeprovisionRelationshipIntelligenceAction started for organization Id {0}.`
- `0x4e1a`: `Deprovisioning Relationship Insights service in DeprovisionRelationshipIntelligenceAction failed for organization Id {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x4da0  ldarg.0
0x4da1  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4da6  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x4dab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x4db0  stloc.0
0x4db1  ldloc.0
0x4db2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4db7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4dbc  brfalse.s loc_4E07
0x4dbe  ldc.i4.2
0x4dbf  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x4dc4  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x4dc9  bne.un.s loc_4E07
0x4dcb  ldloc.0
0x4dcc  ldc.i4.0
0x4dcd  ldc.i4.0
0x4dce  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x4dd3  stloc.1
0x4dd4  ldloc.1
0x4dd5  brfalse.s loc_4E07
0x4dd7  call     class Microsoft.Crm.CrmLive.Provisioning.RelationshipIntelligenceEventSource Microsoft.Crm.CrmLive.Provisioning.RelationshipIntelligenceEventSource::get_Instance()
0x4ddc  ldloc.0
0x4ddd  ldstr    aRideprovisioni// "RIDeprovisioningStarted"
0x4de2  ldstr    aDeprovision// "Deprovision"
0x4de7  ldstr    aDeprovisioning// "Deprovisioning Relationship Insights se"...
0x4dec  ldloc.0
0x4ded  box      [mscorlib]System.Guid
0x4df2  call     string [mscorlib]System.String::Format(string, object)
0x4df7  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.RelationshipIntelligenceEventSource::RIDeprovisioningStarted(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string Message)
0x4dfc  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::.ctor()
0x4e01  ldloc.1
0x4e02  call     instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RelationshipIntelligenceService::DeprovisionRelationshipInsights(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4e07  leave.s  loc_4E5A
0x4e09  stloc.2
0x4e0a  call     class Microsoft.Crm.CrmLive.Provisioning.RelationshipIntelligenceEventSource Microsoft.Crm.CrmLive.Provisioning.RelationshipIntelligenceEventSource::get_Instance()
0x4e0f  ldloc.0
0x4e10  ldstr    aRideprovisioni_0// "RIDeprovisioningFailed"
0x4e15  ldstr    aDeprovision// "Deprovision"
0x4e1a  ldstr    aDeprovisioning_0// "Deprovisioning Relationship Insights se"...
0x4e1f  ldloc.0
0x4e20  box      [mscorlib]System.Guid
0x4e25  call     string [mscorlib]System.String::Format(string, object)
0x4e2a  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.RelationshipIntelligenceEventSource::RIDeprovisioningFailed(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string Message)
0x4e2f  ldloc.2
0x4e30  ldloc.0
0x4e31  ldc.i4.s 0xA
0x4e33  ldstr    aDeprovisioning_1// "Deprovisioning organization for Relatio"...
0x4e38  ldc.i4.0
0x4e39  newarr   [mscorlib]System.Object
0x4e3e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e43  ldstr    aDeprovisioning_2// "Deprovisioning organization for Relatio"...
0x4e48  ldloc.2
0x4e49  callvirt instance string [mscorlib]System.Object::ToString()
0x4e4e  call     string [mscorlib]System.String::Concat(string, string)
0x4e53  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x4e58  leave.s  loc_4E5A
0x4e5a  ret
```
