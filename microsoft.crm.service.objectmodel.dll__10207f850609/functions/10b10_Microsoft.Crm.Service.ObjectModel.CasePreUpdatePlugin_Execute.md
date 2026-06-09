# Microsoft.Crm.Service.ObjectModel.CasePreUpdatePlugin::Execute

- ea: `0x10b10`
- end: `0x10b9a`
- name: `Microsoft.Crm.Service.ObjectModel.CasePreUpdatePlugin::Execute`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x10b10`
- `0x117d0`
- `0x11890`
- `0x119d0`
- `0x11df0`
- `0x11f70`

## pseudocode

```c

```

## disassembly

```asm
0x10b10  ldarg.1
0x10b11  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x10b16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b1b  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x10b20  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x10b25  stloc.0
0x10b26  ldloc.0
0x10b27  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x10b2c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x10b31  stloc.1
0x10b32  ldloc.0
0x10b33  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x10b38  ldstr    aTarget// "Target"
0x10b3d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10b42  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x10b47  stloc.2
0x10b48  ldloc.2
0x10b49  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10b4e  ldstr    aEntitlementid// "entitlementid"
0x10b53  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10b58  brfalse.s loc_10B8B
0x10b5a  ldloc.2
0x10b5b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10b60  ldstr    aEntitlementid// "entitlementid"
0x10b65  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10b6a  brfalse.s loc_10B8B
0x10b6c  ldloc.0
0x10b6d  ldc.i4.1
0x10b6e  ldc.i4.1
0x10b6f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlement(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isRestrictCheckrequired, bool isUpdate)
0x10b74  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement
0x10b79  ldloc.0
0x10b7a  ldc.i4.1
0x10b7b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlementChannel(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isUpadte)
0x10b80  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel
0x10b85  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::CheckEntitlementAndChannelTermValidity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entitlementEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity channelEntity)
0x10b8a  ret
0x10b8b  ldloc.1
0x10b8c  call     bool Microsoft.Crm.Service.ObjectModel.CasePluginHelper::AutoApplyDefaultOnCaseUpdate(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10b91  brfalse.s loc_10B99
0x10b93  ldloc.0
0x10b94  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::SetDefaultEntitlementOnCaseUpdate(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context)
0x10b99  ret
```
