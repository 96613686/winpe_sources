# Microsoft.Crm.Service.ObjectModel.CasePostCreatePlugin::Execute

- ea: `0x10900`
- end: `0x10aa1`
- name: `Microsoft.Crm.Service.ObjectModel.CasePostCreatePlugin::Execute`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x10900`
- `0x10ab0`
- `0x11820`
- `0x11890`
- `0x119d0`
- `0x121a0`
- `0x126d0`
- `0x12990`
- `0x13660`

## pseudocode

```c

```

## disassembly

```asm
0x10900  ldarg.1
0x10901  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x10906  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1090b  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x10910  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x10915  stloc.0
0x10916  ldarg.1
0x10917  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0x1091c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10921  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x10926  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0x1092b  stloc.1
0x1092c  ldloc.0
0x1092d  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x10932  stloc.2
0x10933  ldloc.0
0x10934  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x10939  ldstr    aTarget// "Target"
0x1093e  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10943  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x10948  stloc.3
0x10949  ldloc.0
0x1094a  ldc.i4.0
0x1094b  ldc.i4.0
0x1094c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlement(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isRestrictCheckrequired, bool isUpdate)
0x10951  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement
0x10956  stloc.s  4
0x10958  ldloca.s 5
0x1095a  ldloc.3
0x1095b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10960  ldstr    aIncidentid// "incidentid"
0x10965  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1096a  callvirt instance string [mscorlib]System.Object::ToString()
0x1096f  call     instance void [mscorlib]System.Guid::.ctor(string)
0x10974  ldarg.0
0x10975  ldloc.3
0x10976  ldstr    aSlaid// "slaid"
0x1097b  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Service.ObjectModel.CasePostCreatePlugin::GetEntityReferenceId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeName)
0x10980  stloc.s  6
0x10982  ldc.i4.0
0x10983  stloc.s  7
0x10985  ldloc.s  4
0x10987  ldloc.s  6
0x10989  ldloca.s 0xD
0x1098b  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x10991  ldloc.s  0xD
0x10993  ldloca.s 7
0x10995  ldloc.2
0x10996  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x1099b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::SlaForCase(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement entitlement, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> manualSLAId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> previousSLAId, bool& isAutoSLA, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x109a0  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0x109a5  stloc.s  8
0x109a7  ldloc.1
0x109a8  ldloc.s  8
0x109aa  ldloc.2
0x109ab  ldc.i4.0
0x109ac  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ImpersonateUserForSLAWorkflows(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext, bool toCancelWorkflow)
0x109b1  stloc.s  9
0x109b3  ldc.i4.0
0x109b4  stloc.s  0xA
0x109b6  ldc.i4.0
0x109b7  stloc.s  0xB
0x109b9  ldloc.3
0x109ba  ldnull
0x109bb  ldloc.2
0x109bc  ldloc.s  5
0x109be  ldnull
0x109bf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x109c4  ldloca.s 0xA
0x109c6  ldloca.s 0xB
0x109c8  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HandlePauseResume(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext, valuetype [mscorlib]System.Guid primaryEntityId, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident incident, valuetype [mscorlib]System.Guid calenderId, [out] int32& slaKpiStatus, [out] int32& caseOnHoldTime)
0x109cd  pop
0x109ce  ldloc.s  8
0x109d0  ldloc.s  5
0x109d2  ldloc.s  9
0x109d4  ldloc.2
0x109d5  ldloc.s  0xB
0x109d7  ldloc.s  0xA
0x109d9  ldc.i4.1
0x109da  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ExecuteWorkflow(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, valuetype [mscorlib]System.Guid incidentId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService organizationService, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext context, int32 onHoldTime, int32 slaKpiStatus, int32 invokeChildWFs)
0x109df  ldloc.s  4
0x109e1  brfalse.s loc_109F6
0x109e3  ldloc.s  4
0x109e5  ldstr    aDecreaseremain// "decreaseremainingon"
0x109ea  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x109ef  unbox.any [mscorlib]System.Int32
0x109f4  brtrue.s loc_109F7
0x109f6  ret
0x109f7  ldloc.s  4
0x109f9  ldstr    aAllocationtype// "allocationtypecode"
0x109fe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x10a03  unbox.any [mscorlib]System.Int32
0x10a08  brfalse.s loc_10A0B
0x10a0a  ret
0x10a0b  ldloc.3
0x10a0c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10a11  ldstr    aDecremententit// "decremententitlementterm"
0x10a16  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10a1b  brfalse.s loc_10A4C
0x10a1d  ldloc.3
0x10a1e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10a23  ldstr    aDecremententit// "decremententitlementterm"
0x10a28  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10a2d  unbox.any [mscorlib]System.Boolean
0x10a32  brfalse.s loc_10A4C
0x10a34  ldloc.s  4
0x10a36  ldc.i4.0
0x10a37  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::One
0x10a3c  ldstr    aRemainingterms// "remainingterms"
0x10a41  ldloc.2
0x10a42  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x10a47  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::DecreaseOrIncreaseTerms(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, string terms, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10a4c  ldloc.0
0x10a4d  ldc.i4.0
0x10a4e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlementChannel(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isUpadte)
0x10a53  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel
0x10a58  stloc.s  0xC
0x10a5a  ldloc.s  0xC
0x10a5c  brtrue.s loc_10A5F
0x10a5e  ret
0x10a5f  ldloc.3
0x10a60  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10a65  ldstr    aDecremententit// "decremententitlementterm"
0x10a6a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10a6f  brfalse.s loc_10AA0
0x10a71  ldloc.3
0x10a72  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10a77  ldstr    aDecremententit// "decremententitlementterm"
0x10a7c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10a81  unbox.any [mscorlib]System.Boolean
0x10a86  brfalse.s loc_10AA0
0x10a88  ldloc.s  0xC
0x10a8a  ldc.i4.0
0x10a8b  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::One
0x10a90  ldstr    aRemainingterms// "remainingterms"
0x10a95  ldloc.2
0x10a96  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x10a9b  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::DecreaseOrIncreaseTerms(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, string terms, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10aa0  ret
```
