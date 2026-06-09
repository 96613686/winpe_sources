# Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::SetDefaultEntitlementOnCaseUpdate

- ea: `0x11f70`
- end: `0x120e7`
- name: `Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::SetDefaultEntitlementOnCaseUpdate`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10b10`

## callees

- `0x11470`
- `0x115d0`
- `0x11890`
- `0x119d0`
- `0x11df0`
- `0x11f70`

## pseudocode

```c

```

## disassembly

```asm
0x11f70  ldarg.0
0x11f71  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x11f76  stloc.0
0x11f77  ldarg.0
0x11f78  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x11f7d  ldstr    aTarget// "Target"
0x11f82  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11f87  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x11f8c  stloc.1
0x11f8d  ldloc.1
0x11f8e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11f93  ldstr    aIncidentid// "incidentid"
0x11f98  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11f9d  unbox.any [mscorlib]System.Guid
0x11fa2  ldstr    aIncident// "Incident"
0x11fa7  ldnull
0x11fa8  ldc.i4.1
0x11fa9  newarr   [mscorlib]System.String
0x11fae  dup
0x11faf  ldc.i4.0
0x11fb0  ldstr    aEntitlementid// "entitlementid"
0x11fb5  stelem.ref
0x11fb6  ldloc.0
0x11fb7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x11fbc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(valuetype [mscorlib]System.Guid id, string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x11fc1  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident
0x11fc6  stloc.2
0x11fc7  ldloc.1
0x11fc8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11fcd  ldstr    aEntitlementid// "entitlementid"
0x11fd2  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11fd7  brfalse  loc_1207D
0x11fdc  ldloc.1
0x11fdd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11fe2  ldstr    aEntitlementid// "entitlementid"
0x11fe7  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11fec  brtrue   loc_1207D
0x11ff1  ldloc.1
0x11ff2  ldc.i4.1
0x11ff3  ldarg.0
0x11ff4  call     void Microsoft.Crm.Service.ObjectModel.CasePluginHelper::SetDefaultEntitlement(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, bool isUpdate, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext executionContext)
0x11ff9  ldloc.1
0x11ffa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11fff  ldstr    aEntitlementid// "entitlementid"
0x12004  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12009  brfalse  loc_120E6
0x1200e  ldloc.2
0x1200f  ldstr    aEntitlementid// "entitlementid"
0x12014  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12019  brfalse.s loc_1205E
0x1201b  ldloc.1
0x1201c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12021  ldstr    aEntitlementid// "entitlementid"
0x12026  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1202b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x12030  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x12035  ldloc.2
0x12036  ldstr    aEntitlementid// "entitlementid"
0x1203b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12040  unbox.any [mscorlib]System.Guid
0x12045  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1204a  brfalse.s loc_1205E
0x1204c  ldloc.1
0x1204d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12052  ldstr    aEntitlementid// "entitlementid"
0x12057  ldnull
0x12058  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x1205d  ret
0x1205e  ldarg.0
0x1205f  ldc.i4.1
0x12060  ldc.i4.1
0x12061  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlement(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isRestrictCheckrequired, bool isUpdate)
0x12066  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement
0x1206b  ldarg.0
0x1206c  ldc.i4.1
0x1206d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlementChannel(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isUpadte)
0x12072  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel
0x12077  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::CheckEntitlementAndChannelTermValidity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entitlementEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity channelEntity)
0x1207c  ret
0x1207d  ldloc.1
0x1207e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12083  ldstr    aEntitlementid// "entitlementid"
0x12088  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1208d  brtrue.s loc_120E6
0x1208f  ldloc.2
0x12090  ldstr    aEntitlementid// "entitlementid"
0x12095  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1209a  brtrue.s loc_120E6
0x1209c  ldloc.1
0x1209d  ldc.i4.1
0x1209e  ldarg.0
0x1209f  call     void Microsoft.Crm.Service.ObjectModel.CasePluginHelper::SetDefaultEntitlement(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, bool isUpdate, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext executionContext)
0x120a4  ldloc.1
0x120a5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x120aa  ldstr    aEntitlementid// "entitlementid"
0x120af  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x120b4  brfalse.s loc_120E6
0x120b6  ldloc.1
0x120b7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x120bc  ldstr    aEntitlementid// "entitlementid"
0x120c1  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x120c6  brfalse.s loc_120E6
0x120c8  ldarg.0
0x120c9  ldc.i4.1
0x120ca  ldc.i4.1
0x120cb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlement(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isRestrictCheckrequired, bool isUpdate)
0x120d0  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement
0x120d5  ldarg.0
0x120d6  ldc.i4.1
0x120d7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlementChannel(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isUpadte)
0x120dc  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel
0x120e1  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::CheckEntitlementAndChannelTermValidity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entitlementEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity channelEntity)
0x120e6  ret
```
