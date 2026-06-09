# Microsoft.Crm.Service.ObjectModel.SLAKPIInstanceService::CollectTelemetry

- ea: `0x94d0`
- end: `0x96cf`
- name: `Microsoft.Crm.Service.ObjectModel.SLAKPIInstanceService::CollectTelemetry`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x94d0`

## string_xrefs

- `0x94fc`: `Create`
- `0x9509`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x94d0  ldc.i4.0
0x94d1  stloc.0
0x94d2  ldarg.1
0x94d3  brfalse  loc_96CD
0x94d8  ldarg.2
0x94d9  brfalse  loc_96CD
0x94de  ldarg.3
0x94df  brfalse  loc_96CD
0x94e4  ldarg.3
0x94e5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x94ea  brfalse  loc_96CD
0x94ef  ldarg.3
0x94f0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x94f5  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x94fa  stloc.1
0x94fb  ldloc.1
0x94fc  ldstr    aCreate_0// "Create"
0x9501  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9506  brtrue.s loc_9518
0x9508  ldloc.1
0x9509  ldstr    aUpdate// "Update"
0x950e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9513  brfalse  loc_96CD
0x9518  ldarg.1
0x9519  ldc.i4.0
0x951a  callvirt instance object [mscorlib]System.Collections.IList::get_Item(int32)
0x951f  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity
0x9524  stloc.2
0x9525  ldloc.2
0x9526  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::FailureTime
0x952b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x9530  brtrue.s loc_955F
0x9532  ldarg.2
0x9533  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::FailureTime
0x9538  ldloc.2
0x9539  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::FailureTime
0x953e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9543  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x9548  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTimeWithMilliseconds()
0x954d  stloc.3
0x954e  ldloca.s 3
0x9550  ldstr    aYyyyMmDdthhMmS// "yyyy-MM-ddTHH:mm:ss.fff-00:00"
0x9555  call     instance string [mscorlib]System.DateTime::ToString(string)
0x955a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x955f  ldloc.2
0x9560  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::ComputedFailureTime
0x9565  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x956a  brtrue.s loc_9599
0x956c  ldarg.2
0x956d  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::ComputedFailureTime
0x9572  ldloc.2
0x9573  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::ComputedFailureTime
0x9578  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x957d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x9582  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTimeWithMilliseconds()
0x9587  stloc.3
0x9588  ldloca.s 3
0x958a  ldstr    aYyyyMmDdthhMmS// "yyyy-MM-ddTHH:mm:ss.fff-00:00"
0x958f  call     instance string [mscorlib]System.DateTime::ToString(string)
0x9594  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x9599  ldloc.2
0x959a  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::WarningTime
0x959f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x95a4  brtrue.s loc_95D3
0x95a6  ldarg.2
0x95a7  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::WarningTime
0x95ac  ldloc.2
0x95ad  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::WarningTime
0x95b2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x95b7  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x95bc  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTimeWithMilliseconds()
0x95c1  stloc.3
0x95c2  ldloca.s 3
0x95c4  ldstr    aYyyyMmDdthhMmS// "yyyy-MM-ddTHH:mm:ss.fff-00:00"
0x95c9  call     instance string [mscorlib]System.DateTime::ToString(string)
0x95ce  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x95d3  ldloc.2
0x95d4  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::ComputedWarningTime
0x95d9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x95de  brtrue.s loc_960D
0x95e0  ldarg.2
0x95e1  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::ComputedWarningTime
0x95e6  ldloc.2
0x95e7  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::ComputedWarningTime
0x95ec  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x95f1  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x95f6  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTimeWithMilliseconds()
0x95fb  stloc.3
0x95fc  ldloca.s 3
0x95fe  ldstr    aYyyyMmDdthhMmS// "yyyy-MM-ddTHH:mm:ss.fff-00:00"
0x9603  call     instance string [mscorlib]System.DateTime::ToString(string)
0x9608  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x960d  ldloc.2
0x960e  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Status
0x9613  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x9618  brtrue.s loc_9635
0x961a  ldarg.2
0x961b  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Status
0x9620  ldloc.2
0x9621  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Status
0x9626  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x962b  callvirt instance string [mscorlib]System.Object::ToString()
0x9630  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x9635  ldloc.2
0x9636  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Regarding
0x963b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x9640  brtrue.s loc_965D
0x9642  ldarg.2
0x9643  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Regarding
0x9648  ldloc.2
0x9649  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Regarding
0x964e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9653  callvirt instance string [mscorlib]System.Object::ToString()
0x9658  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x965d  ldloc.2
0x965e  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::RegardingObjectTypeCode
0x9663  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x9668  brtrue.s loc_96A3
0x966a  ldarg.3
0x966b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9670  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9675  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x967a  ldloc.2
0x967b  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::RegardingObjectTypeCode
0x9680  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x9685  unbox.any [mscorlib]System.Int32
0x968a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x968f  stloc.s  4
0x9691  ldarg.2
0x9692  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::RegardingObjectName
0x9697  ldloc.s  4
0x9699  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x969e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x96a3  ldloc.2
0x96a4  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::WarningTimeReached
0x96a9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x96ae  brtrue.s loc_96CB
0x96b0  ldarg.2
0x96b1  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::WarningTimeReached
0x96b6  ldloc.2
0x96b7  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::WarningTimeReached
0x96bc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x96c1  callvirt instance string [mscorlib]System.Object::ToString()
0x96c6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x96cb  ldc.i4.1
0x96cc  stloc.0
0x96cd  ldloc.0
0x96ce  ret
```
