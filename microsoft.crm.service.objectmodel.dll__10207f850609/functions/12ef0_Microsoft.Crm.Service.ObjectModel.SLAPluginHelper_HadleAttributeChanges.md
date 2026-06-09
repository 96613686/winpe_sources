# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HadleAttributeChanges

- ea: `0x12ef0`
- end: `0x12f94`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HadleAttributeChanges`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x12ca0`

## callees

- `0x12350`
- `0x12ef0`
- `0x12fa0`

## pseudocode

```c

```

## disassembly

```asm
0x12ef0  ldnull
0x12ef1  stloc.0
0x12ef2  ldarg.0
0x12ef3  ldstr    aApplicablefrom// "applicablefrom"
0x12ef8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12efd  brfalse.s loc_12F15
0x12eff  ldarg.0
0x12f00  ldstr    aApplicablefrom// "applicablefrom"
0x12f05  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12f0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12f0f  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x12f14  stloc.0
0x12f15  ldloc.0
0x12f16  brfalse.s loc_12F2E
0x12f18  ldarg.1
0x12f19  ldloc.0
0x12f1a  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x12f1f  brfalse.s loc_12F2E
0x12f21  ldloc.0
0x12f22  ldstr    aModifiedon// "modifiedon"
0x12f27  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x12f2c  brtrue.s loc_12F5B
0x12f2e  ldarga.s 4
0x12f30  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12f35  brfalse.s loc_12F6D
0x12f37  ldarga.s 4
0x12f39  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x12f3f  callvirt instance string [mscorlib]System.Object::ToString()
0x12f44  ldarg.0
0x12f45  ldstr    aSlaid// "slaid"
0x12f4a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12f4f  callvirt instance string [mscorlib]System.Object::ToString()
0x12f54  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x12f59  brfalse.s loc_12F6D
0x12f5b  ldarg.s  7
0x12f5d  ldarg.s  8
0x12f5f  ldarg.0
0x12f60  ldarg.2
0x12f61  ldarg.3
0x12f62  ldarg.s  5
0x12f64  ldarg.s  6
0x12f66  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelOldAndExecuteNewWorkFlows(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, valuetype [mscorlib]System.Guid incidentId, valuetype [mscorlib]System.Guid slaInvokedId, int32 slaKpiStatus, int32 caseOnHoldTime)
0x12f6b  ldc.i4.1
0x12f6c  ret
0x12f6d  ldarg.0
0x12f6e  ldstr    aChangedattribu// "changedattributelist"
0x12f73  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12f78  ldarg.1
0x12f79  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::IsAttributeChanged(object changedAttributeList, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity)
0x12f7e  brfalse.s loc_12F92
0x12f80  ldarg.s  7
0x12f82  ldarg.s  8
0x12f84  ldarg.0
0x12f85  ldarg.2
0x12f86  ldarg.3
0x12f87  ldarg.s  5
0x12f89  ldarg.s  6
0x12f8b  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelOldAndExecuteNewWorkFlows(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, valuetype [mscorlib]System.Guid incidentId, valuetype [mscorlib]System.Guid slaInvokedId, int32 slaKpiStatus, int32 caseOnHoldTime)
0x12f90  ldc.i4.1
0x12f91  ret
0x12f92  ldc.i4.0
0x12f93  ret
```
