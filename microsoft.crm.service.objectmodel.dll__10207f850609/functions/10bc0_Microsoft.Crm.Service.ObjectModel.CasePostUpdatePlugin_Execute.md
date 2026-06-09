# Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::Execute

- ea: `0x10bc0`
- end: `0x111c2`
- name: `Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::Execute`
- size: `1538`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x10bc0`
- `0x111d0`
- `0x11310`
- `0x11350`
- `0x11370`
- `0x11470`
- `0x11820`
- `0x11890`
- `0x11e20`
- `0x11e80`
- `0x12b30`

## pseudocode

```c

```

## disassembly

```asm
0x10bc0  ldarg.1
0x10bc1  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x10bc6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10bcb  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x10bd0  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x10bd5  stloc.0
0x10bd6  ldarg.1
0x10bd7  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0x10bdc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10be1  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x10be6  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0x10beb  stloc.1
0x10bec  ldloc.0
0x10bed  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x10bf2  stloc.2
0x10bf3  ldloc.0
0x10bf4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x10bf9  ldstr    aTarget// "Target"
0x10bfe  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10c03  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x10c08  stloc.3
0x10c09  ldloc.3
0x10c0a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10c0f  ldstr    aEntitlementid// "entitlementid"
0x10c14  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10c19  brtrue.s loc_10C52
0x10c1b  ldloc.3
0x10c1c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10c21  ldstr    aSlainvokedid// "slainvokedid"
0x10c26  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10c2b  brtrue.s loc_10C51
0x10c2d  ldloc.3
0x10c2e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10c33  ldstr    aResponseby// "responseby"
0x10c38  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10c3d  brtrue.s loc_10C51
0x10c3f  ldloc.3
0x10c40  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10c45  ldstr    aResolveby// "resolveby"
0x10c4a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10c4f  brfalse.s loc_10C52
0x10c51  ret
0x10c52  ldloc.0
0x10c53  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PreEntityImages()
0x10c58  ldstr    aPrebusinessent// "PreBusinessEntity"
0x10c5d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0x10c62  stloc.s  4
0x10c64  ldloc.0
0x10c65  ldc.i4.0
0x10c66  ldc.i4.1
0x10c67  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlement(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, bool isRestrictCheckrequired, bool isUpdate)
0x10c6c  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement
0x10c71  stloc.s  5
0x10c73  ldloc.1
0x10c74  ldloc.0
0x10c75  ldloc.s  5
0x10c77  ldloc.3
0x10c78  ldloc.s  4
0x10c7a  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HandleUpdate(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement newEntitlement, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity)
0x10c7f  ldloc.3
0x10c80  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10c85  ldstr    aDecremententit// "decremententitlementterm"
0x10c8a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10c8f  brfalse.s loc_10CA8
0x10c91  ldloc.3
0x10c92  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10c97  ldstr    aDecremententit// "decremententitlementterm"
0x10c9c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10ca1  unbox.any [mscorlib]System.Boolean
0x10ca6  brtrue.s loc_10CEE
0x10ca8  ldloc.3
0x10ca9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10cae  ldstr    aDecremententit// "decremententitlementterm"
0x10cb3  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10cb8  brtrue   loc_11164
0x10cbd  ldloc.s  4
0x10cbf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10cc4  ldstr    aDecremententit// "decremententitlementterm"
0x10cc9  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10cce  brfalse  loc_11164
0x10cd3  ldloc.s  4
0x10cd5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10cda  ldstr    aDecremententit// "decremententitlementterm"
0x10cdf  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10ce4  unbox.any [mscorlib]System.Boolean
0x10ce9  brfalse  loc_11164
0x10cee  ldloc.3
0x10cef  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10cf4  ldstr    aEntitlementid// "entitlementid"
0x10cf9  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10cfe  brfalse.s loc_10D66
0x10d00  ldloc.s  5
0x10d02  brfalse.s loc_10D5D
0x10d04  ldarg.0
0x10d05  ldloc.s  5
0x10d07  ldc.i4.0
0x10d08  ldloc.2
0x10d09  call     instance void Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::ValidateAndDecreaseOrIncreaseTerms(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement entitlement, bool isIncrease, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x10d0e  ldloc.3
0x10d0f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10d14  ldstr    aCaseorigincode// "caseorigincode"
0x10d19  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10d1e  brtrue.s loc_10D33
0x10d20  ldloc.s  4
0x10d22  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10d27  ldstr    aCaseorigincode// "caseorigincode"
0x10d2c  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10d31  brfalse.s loc_10D5D
0x10d33  ldloc.3
0x10d34  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10d39  ldstr    aCaseorigincode// "caseorigincode"
0x10d3e  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10d43  brtrue.s loc_10D49
0x10d45  ldloc.s  4
0x10d47  br.s     loc_10D4A
0x10d49  ldloc.3
0x10d4a  stloc.s  7
0x10d4c  ldarg.0
0x10d4d  ldloc.s  7
0x10d4f  ldloc.s  5
0x10d51  ldc.i4.0
0x10d52  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::One
0x10d57  ldloc.2
0x10d58  call     instance void Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::DecreaseOrIncreaseChannelTerms(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement entitlement, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x10d5d  ldarg.0
0x10d5e  ldloc.s  4
0x10d60  ldloc.2
0x10d61  call     instance void Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::UpdateOldEntitlementTerms(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x10d66  ldloc.s  4
0x10d68  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10d6d  ldstr    aEntitlementid// "entitlementid"
0x10d72  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10d77  brfalse.s loc_10D87
0x10d79  ldloc.s  4
0x10d7b  ldstr    aEntitlementid// "entitlementid"
0x10d80  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x10d85  brtrue.s loc_10D88
0x10d87  ret
0x10d88  ldloc.s  4
0x10d8a  ldstr    aEntitlementid// "entitlementid"
0x10d8f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x10d94  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x10d99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x10d9e  ldstr    aEntitlement// "Entitlement"
0x10da3  ldnull
0x10da4  ldc.i4.5
0x10da5  newarr   [mscorlib]System.String
0x10daa  dup
0x10dab  ldc.i4.0
0x10dac  ldstr    aDecreaseremain// "decreaseremainingon"
0x10db1  stelem.ref
0x10db2  dup
0x10db3  ldc.i4.1
0x10db4  ldstr    aAllocationtype// "allocationtypecode"
0x10db9  stelem.ref
0x10dba  dup
0x10dbb  ldc.i4.2
0x10dbc  ldstr    aRemainingterms// "remainingterms"
0x10dc1  stelem.ref
0x10dc2  dup
0x10dc3  ldc.i4.3
0x10dc4  ldstr    aTotalterms// "totalterms"
0x10dc9  stelem.ref
0x10dca  dup
0x10dcb  ldc.i4.4
0x10dcc  ldstr    aOwnerid// "ownerid"
0x10dd1  stelem.ref
0x10dd2  ldloc.2
0x10dd3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x10dd8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(valuetype [mscorlib]System.Guid id, string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x10ddd  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement
0x10de2  stloc.s  6
0x10de4  ldloc.s  6
0x10de6  brtrue.s loc_10DE9
0x10de8  ret
0x10de9  ldloc.3
0x10dea  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10def  ldstr    aStatecode// "statecode"
0x10df4  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10df9  brfalse  loc_11097
0x10dfe  ldloc.s  4
0x10e00  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10e05  ldstr    aStatecode// "statecode"
0x10e0a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10e0f  brfalse.s loc_10E4B
0x10e11  ldloc.s  4
0x10e13  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10e18  ldstr    aStatecode// "statecode"
0x10e1d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10e22  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x10e27  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x10e2c  ldloc.3
0x10e2d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10e32  ldstr    aStatecode// "statecode"
0x10e37  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10e3c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x10e41  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x10e46  beq      loc_11097
0x10e4b  ldloc.3
0x10e4c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10e51  ldstr    aStatecode// "statecode"
0x10e56  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10e5b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x10e60  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x10e65  brtrue   loc_10F42
0x10e6a  ldloc.s  4
0x10e6c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10e71  ldstr    aStatecode// "statecode"
0x10e76  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10e7b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x10e80  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x10e85  ldc.i4.2
0x10e86  bne.un.s loc_10EA8
0x10e88  ldarg.0
0x10e89  ldloc.s  6
0x10e8b  ldc.i4.0
0x10e8c  ldloc.2
0x10e8d  call     instance void Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::ValidateAndDecreaseOrIncreaseTerms(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement entitlement, bool isIncrease, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x10e92  ldarg.0
0x10e93  ldloc.s  4
0x10e95  ldloc.s  6
0x10e97  ldc.i4.0
0x10e98  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::One
0x10e9d  ldloc.2
0x10e9e  call     instance void Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::DecreaseOrIncreaseChannelTerms(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement entitlement, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x10ea3  br       loc_11097
0x10ea8  ldloc.s  6
0x10eaa  ldstr    aDecreaseremain// "decreaseremainingon"
0x10eaf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x10eb4  unbox.any [mscorlib]System.Int32
0x10eb9  brtrue   loc_11097
0x10ebe  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::One
0x10ec3  stloc.s  8
0x10ec5  ldloc.s  6
0x10ec7  ldstr    aAllocationtype// "allocationtypecode"
0x10ecc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x10ed1  unbox.any [mscorlib]System.Int32
0x10ed6  ldc.i4.1
0x10ed7  bne.un.s loc_10F0B
0x10ed9  ldloc.3
0x10eda  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10edf  ldstr    aIncidentid// "incidentid"
0x10ee4  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10ee9  unbox.any [mscorlib]System.Guid
0x10eee  ldloc.2
0x10eef  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x10ef4  call     int32 Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::TimeSpentOnIncident(valuetype [mscorlib]System.Guid incidentId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x10ef9  conv.r8
0x10efa  ldc.r8   60.0
0x10f03  div
0x10f04  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Explicit(float64)
0x10f09  stloc.s  8
0x10f0b  ldloc.s  6
0x10f0d  ldc.i4.1
0x10f0e  ldloc.s  8
0x10f10  ldstr    aRemainingterms// "remainingterms"
0x10f15  ldloc.2
0x10f16  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x10f1b  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::DecreaseOrIncreaseTerms(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, string terms, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10f20  ldloc.s  4
0x10f22  ldloc.s  4
0x10f24  ldloc.2
0x10f25  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetEntitlementChannel(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entitlementContainer, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity caseOriginContainer, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x10f2a  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel
0x10f2f  stloc.s  9
0x10f31  ldarg.0
0x10f32  ldloc.s  9
0x10f34  ldc.i4.1
0x10f35  ldloc.s  8
0x10f37  ldloc.2
0x10f38  call     instance void Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::ValidateAndDecreaseOrIncreaseChannelTerms(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel channel, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x10f3d  br       loc_11097
0x10f42  ldloc.3
0x10f43  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x10f48  ldstr    aStatecode// "statecode"
0x10f4d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10f52  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x10f57  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x10f5c  ldc.i4.1
0x10f5d  bne.un   loc_1102E
0x10f62  ldloc.s  6
0x10f64  ldstr    aAllocationtype// "allocationtypecode"
0x10f69  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x10f6e  unbox.any [mscorlib]System.Int32
0x10f73  brtrue.s loc_10FC8
0x10f75  ldloc.s  6
0x10f77  ldstr    aDecreaseremain// "decreaseremainingon"
0x10f7c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x10f81  unbox.any [mscorlib]System.Int32
0x10f86  brtrue   loc_11097
0x10f8b  ldloc.s  6
0x10f8d  ldc.i4.0
0x10f8e  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::One
0x10f93  ldstr    aRemainingterms// "remainingterms"
0x10f98  ldloc.2
0x10f99  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x10f9e  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::DecreaseOrIncreaseTerms(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, string terms, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10fa3  ldloc.s  4
0x10fa5  ldloc.s  4
0x10fa7  ldloc.2
  ... truncated ...
```
