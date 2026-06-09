# Microsoft.Crm.Service.ObjectModel.CasePreCreatePlugin::Execute

- ea: `0x10830`
- end: `0x108dc`
- name: `Microsoft.Crm.Service.ObjectModel.CasePreCreatePlugin::Execute`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x10830`
- `0x115d0`
- `0x117b0`
- `0x11890`
- `0x119d0`
- `0x11df0`
- `0x13840`

## pseudocode

```c

```

## disassembly

```asm
0x10830  ldarg.1
0x10831  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x10836  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1083b  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x10840  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x10845  stloc.0
0x10846  ldloc.0
0x10847  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x1084c  stloc.1
0x1084d  ldloc.0
0x1084e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x10853  ldstr    aTarget// "Target"
0x10858  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1085d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x10862  stloc.2
0x10863  ldloc.2
0x10864  ldc.i4.1
0x10865  ldloc.1
0x10866  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x1086b  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CheckCanSetManualSLA(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, bool isCreate, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10870  ldloc.1
0x10871  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x10876  call     bool Microsoft.Crm.Service.ObjectModel.CasePluginHelper::AutoApplyDefaultOnCaseCreate(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1087b  brfalse.s loc_108BB
0x1087d  ldloc.2
0x1087e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10883  ldstr    aEntitlementid// "entitlementid"
0x10888  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1088d  brfalse.s loc_108B3
0x1088f  ldloc.2
0x10890  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10895  ldstr    aEntitlementid// "entitlementid"
0x1089a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1089f  brfalse.s loc_108BB
0x108a1  ldloc.2
0x108a2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x108a7  ldstr    aEntitlementid// "entitlementid"
0x108ac  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x108b1  brtrue.s loc_108BB
0x108b3  ldloc.2
0x108b4  ldc.i4.0
0x108b5  ldloc.0
0x108b6  call     void Microsoft.Crm.Service.ObjectModel.CasePluginHelper::SetDefaultEntitlement(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, bool isUpdate, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext executionContext)
0x108bb  ldloc.0
0x108bc  ldc.i4.1
0x108bd  ldc.i4.0
0x108be  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlement(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isRestrictCheckrequired, bool isUpdate)
0x108c3  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement
0x108c8  ldloc.0
0x108c9  ldc.i4.0
0x108ca  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlementChannel(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isUpadte)
0x108cf  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel
0x108d4  stloc.3
0x108d5  ldloc.3
0x108d6  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::CheckEntitlementAndChannelTermValidity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entitlementEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity channelEntity)
0x108db  ret
```
