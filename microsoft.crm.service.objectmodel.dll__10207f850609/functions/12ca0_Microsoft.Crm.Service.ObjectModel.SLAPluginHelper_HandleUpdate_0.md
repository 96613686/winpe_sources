# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HandleUpdate_0

- ea: `0x12ca0`
- end: `0x12eef`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HandleUpdate_0`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x12b30`

## callees

- `0x11470`
- `0x121a0`
- `0x12350`
- `0x12c60`
- `0x12ca0`
- `0x12ef0`
- `0x12fe0`
- `0x13030`
- `0x13290`
- `0x13660`

## string_xrefs

- `0x12cf5`: `businesshoursid`
- `0x12d02`: `businesshoursid`

## pseudocode

```c

```

## disassembly

```asm
0x12ca0  ldc.i4.0
0x12ca1  stloc.0
0x12ca2  ldc.i4.0
0x12ca3  stloc.1
0x12ca4  ldc.i4.0
0x12ca5  stloc.2
0x12ca6  ldarg.1
0x12ca7  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x12cac  stloc.3
0x12cad  ldc.i4.0
0x12cae  stloc.s  4
0x12cb0  ldarg.s  4
0x12cb2  ldstr    aSlaid// "slaid"
0x12cb7  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetEntityReferenceId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeName)
0x12cbc  stloc.s  5
0x12cbe  ldarg.s  5
0x12cc0  ldstr    aSlaid// "slaid"
0x12cc5  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetEntityReferenceId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeName)
0x12cca  stloc.s  6
0x12ccc  ldarg.3
0x12ccd  dup
0x12cce  brtrue.s loc_12CE8
0x12cd0  pop
0x12cd1  ldarg.2
0x12cd2  ldloc.s  5
0x12cd4  ldloc.s  6
0x12cd6  ldloca.s 4
0x12cd8  ldloc.3
0x12cd9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x12cde  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::SlaForCase(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement entitlement, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> manualSLAId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> previousSLAId, bool& isAutoSLA, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x12ce3  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0x12ce8  starg.s  3
0x12cea  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12cef  stloc.s  7
0x12cf1  ldarg.3
0x12cf2  brfalse.s loc_12D13
0x12cf4  ldarg.3
0x12cf5  ldstr    aBusinesshoursi// "businesshoursid"
0x12cfa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12cff  brfalse.s loc_12D13
0x12d01  ldarg.3
0x12d02  ldstr    aBusinesshoursi// "businesshoursid"
0x12d07  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12d0c  unbox.any [mscorlib]System.Guid
0x12d11  stloc.s  7
0x12d13  ldloca.s 8
0x12d15  ldarg.s  4
0x12d17  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12d1c  ldstr    aIncidentid// "incidentid"
0x12d21  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12d26  callvirt instance string [mscorlib]System.Object::ToString()
0x12d2b  call     instance void [mscorlib]System.Guid::.ctor(string)
0x12d30  ldloc.s  4
0x12d32  brfalse.s loc_12D44
0x12d34  ldarg.3
0x12d35  brfalse.s loc_12D44
0x12d37  ldloc.3
0x12d38  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x12d3d  ldloc.s  8
0x12d3f  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ClearManualSLA(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid incidentId)
0x12d44  ldloc.s  8
0x12d46  ldstr    aIncident// "Incident"
0x12d4b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x12d50  ldc.i4.4
0x12d51  newarr   [mscorlib]System.String
0x12d56  dup
0x12d57  ldc.i4.0
0x12d58  ldstr    aSlainvokedid// "slainvokedid"
0x12d5d  stelem.ref
0x12d5e  dup
0x12d5f  ldc.i4.1
0x12d60  ldstr    aLastonholdtime// "lastonholdtime"
0x12d65  stelem.ref
0x12d66  dup
0x12d67  ldc.i4.2
0x12d68  ldstr    aOnholdtime// "onholdtime"
0x12d6d  stelem.ref
0x12d6e  dup
0x12d6f  ldc.i4.3
0x12d70  ldstr    aStatuscode// "statuscode"
0x12d75  stelem.ref
0x12d76  ldloc.3
0x12d77  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x12d7c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(valuetype [mscorlib]System.Guid id, string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x12d81  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident
0x12d86  stloc.s  9
0x12d88  ldarg.s  4
0x12d8a  ldarg.s  5
0x12d8c  ldloc.3
0x12d8d  ldarg.1
0x12d8e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityId()
0x12d93  ldloc.s  9
0x12d95  ldloc.s  7
0x12d97  ldloca.s 1
0x12d99  ldloca.s 2
0x12d9b  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HandlePauseResume(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext, valuetype [mscorlib]System.Guid primaryEntityId, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident incident, valuetype [mscorlib]System.Guid calenderId, [out] int32& slaKpiStatus, [out] int32& caseOnHoldTime)
0x12da0  stloc.0
0x12da1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12da6  stloc.s  0xA
0x12da8  ldloc.s  9
0x12daa  ldstr    aSlainvokedid// "slainvokedid"
0x12daf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12db4  brfalse.s loc_12DC9
0x12db6  ldloc.s  9
0x12db8  ldstr    aSlainvokedid// "slainvokedid"
0x12dbd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12dc2  unbox.any [mscorlib]System.Guid
0x12dc7  stloc.s  0xA
0x12dc9  ldloca.s 5
0x12dcb  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12dd0  brfalse.s loc_12E14
0x12dd2  ldloc.s  5
0x12dd4  stloc.s  0xB
0x12dd6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12ddb  stloc.s  0xC
0x12ddd  ldloca.s 0xB
0x12ddf  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12de4  brtrue.s loc_12DE9
0x12de6  ldc.i4.0
0x12de7  br.s     loc_12E03
0x12de9  ldloca.s 0xB
0x12deb  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12df0  brtrue.s loc_12DF5
0x12df2  ldc.i4.1
0x12df3  br.s     loc_12E03
0x12df5  ldloca.s 0xB
0x12df7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x12dfc  ldloc.s  0xC
0x12dfe  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12e03  brfalse.s loc_12E14
0x12e05  ldarg.3
0x12e06  brtrue.s loc_12E14
0x12e08  ldloc.s  0xA
0x12e0a  ldloc.s  8
0x12e0c  ldarg.0
0x12e0d  ldloc.3
0x12e0e  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelWorkFlows(valuetype [mscorlib]System.Guid slainvokedid, valuetype [mscorlib]System.Guid incidentId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x12e13  ret
0x12e14  ldarg.3
0x12e15  brfalse  loc_12EEE
0x12e1a  ldarg.s  4
0x12e1c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12e21  ldstr    aEntitlementid// "entitlementid"
0x12e26  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12e2b  brfalse.s loc_12E51
0x12e2d  ldarg.3
0x12e2e  ldstr    aSlaid// "slaid"
0x12e33  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12e38  callvirt instance string [mscorlib]System.Object::ToString()
0x12e3d  ldloca.s 0xA
0x12e3f  constrained. [mscorlib]System.Guid
0x12e45  callvirt instance string [mscorlib]System.Object::ToString()
0x12e4a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x12e4f  brtrue.s loc_12E96
0x12e51  ldloca.s 5
0x12e53  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x12e59  callvirt instance string [mscorlib]System.Object::ToString()
0x12e5e  ldarg.3
0x12e5f  ldstr    aSlaid// "slaid"
0x12e64  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12e69  callvirt instance string [mscorlib]System.Object::ToString()
0x12e6e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12e73  brfalse.s loc_12EA5
0x12e75  ldloca.s 0xA
0x12e77  constrained. [mscorlib]System.Guid
0x12e7d  callvirt instance string [mscorlib]System.Object::ToString()
0x12e82  ldloca.s 5
0x12e84  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x12e8a  callvirt instance string [mscorlib]System.Object::ToString()
0x12e8f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x12e94  brfalse.s loc_12EA5
0x12e96  ldarg.0
0x12e97  ldloc.3
0x12e98  ldarg.3
0x12e99  ldloc.s  8
0x12e9b  ldloc.s  0xA
0x12e9d  ldloc.1
0x12e9e  ldloc.2
0x12e9f  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelOldAndExecuteNewWorkFlows(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, valuetype [mscorlib]System.Guid incidentId, valuetype [mscorlib]System.Guid slaInvokedId, int32 slaKpiStatus, int32 caseOnHoldTime)
0x12ea4  ret
0x12ea5  ldarg.3
0x12ea6  ldarg.s  4
0x12ea8  ldloc.s  8
0x12eaa  ldloc.s  0xA
0x12eac  ldloc.s  5
0x12eae  ldloc.1
0x12eaf  ldloc.2
0x12eb0  ldarg.0
0x12eb1  ldloc.3
0x12eb2  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HadleAttributeChanges(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, valuetype [mscorlib]System.Guid incidentId, valuetype [mscorlib]System.Guid slainvokedid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> manualSLAId, int32 slaKpiStatus, int32 caseOnHoldTime, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x12eb7  brfalse.s loc_12EBA
0x12eb9  ret
0x12eba  ldloc.0
0x12ebb  brfalse.s loc_12EEE
0x12ebd  ldarg.3
0x12ebe  ldstr    aAllowpauseresu// "allowpauseresume"
0x12ec3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12ec8  brfalse.s loc_12EEE
0x12eca  ldarg.3
0x12ecb  ldstr    aAllowpauseresu// "allowpauseresume"
0x12ed0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12ed5  unbox.any [mscorlib]System.Boolean
0x12eda  brfalse.s loc_12EEE
0x12edc  ldarg.0
0x12edd  ldloc.3
0x12ede  ldarg.1
0x12edf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityId()
0x12ee4  ldarg.3
0x12ee5  ldc.i4.0
0x12ee6  ldloc.1
0x12ee7  ldloc.2
0x12ee8  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ExecuteParentWorkFlow(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext context, valuetype [mscorlib]System.Guid incidentId, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, int32 invokeChildWFs, int32 slaKpiStatus, int32 caseOnHoldTime)
0x12eed  ret
0x12eee  ret
```
