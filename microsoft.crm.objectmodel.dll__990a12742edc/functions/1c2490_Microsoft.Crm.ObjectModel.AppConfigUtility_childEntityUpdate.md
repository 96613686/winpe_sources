# Microsoft.Crm.ObjectModel.AppConfigUtility::childEntityUpdate

- ea: `0x1c2490`
- end: `0x1c28d7`
- name: `Microsoft.Crm.ObjectModel.AppConfigUtility::childEntityUpdate`
- size: `1095`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x192c0`
- `0x192e0`
- `0x18d0b0`
- `0x18d110`
- `0x1c2490`
- `0x1c4040`
- `0x1c4160`
- `0x1c4380`
- `0x1c4430`

## string_xrefs

- `0x1c273a`: `appconfigid`
- `0x1c2712`: `appconfigmasterid`
- `0x1c2719`: `appconfigmasterid`
- `0x1c27be`: `appconfiginstanceid`
- `0x1c27cb`: `appconfiginstanceid`
- `0x1c27e6`: `appconfiginstanceid`
- `0x1c2788`: `componentstate`
- `0x1c26ec`: `AppConfigInstance`

## pseudocode

```c

```

## disassembly

```asm
0x1c2490  ldarga.s 1
0x1c2492  constrained. mvar<u1>
0x1c2498  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c249d  ldtoken  Microsoft.Crm.AppConfig.AppConfigInstanceDefinition
0x1c24a2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c24a7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c24ac  brfalse.s loc_1C24DB
0x1c24ae  ldarg.2
0x1c24af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c24b4  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfigInstance::.ctor(valuetype [mscorlib]System.Guid)
0x1c24b9  stloc.0
0x1c24ba  ldarg.0
0x1c24bb  ldfld    class Microsoft.Crm.ObjectModel.AppConfigInstanceService Microsoft.Crm.ObjectModel.AppConfigUtility::_appConfigInstanceService
0x1c24c0  stloc.1
0x1c24c1  ldarg.0
0x1c24c2  ldloc.0
0x1c24c3  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfigInstance
0x1c24c8  ldarg.1
0x1c24c9  box      mvar<u1>
0x1c24ce  isinst   Microsoft.Crm.AppConfig.AppConfigInstanceDefinition
0x1c24d3  ldarg.3
0x1c24d4  call     instance void Microsoft.Crm.ObjectModel.AppConfigUtility::PopulateAppConfigInstanceEntity(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfigInstance appConfigInstanceEntity, class Microsoft.Crm.AppConfig.AppConfigInstanceDefinition appConfigInstanceDefinition, valuetype [mscorlib]System.Guid appConfigId)
0x1c24d9  br.s     loc_1C255A
0x1c24db  ldarga.s 1
0x1c24dd  constrained. mvar<u1>
0x1c24e3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c24e8  ldtoken  Microsoft.Crm.AppConfig.NavigationSettingDefinition
0x1c24ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c24f2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c24f7  brfalse.s loc_1C2559
0x1c24f9  ldarg.2
0x1c24fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c24ff  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.NavigationSetting::.ctor(valuetype [mscorlib]System.Guid)
0x1c2504  stloc.0
0x1c2505  ldarg.0
0x1c2506  ldfld    class Microsoft.Crm.ObjectModel.NavigationSettingService Microsoft.Crm.ObjectModel.AppConfigUtility::_navSettingService
0x1c250b  stloc.1
0x1c250c  ldarg.1
0x1c250d  box      mvar<u1>
0x1c2512  isinst   Microsoft.Crm.AppConfig.NavigationSettingDefinition
0x1c2517  stloc.2
0x1c2518  ldarg.s  4
0x1c251a  brfalse.s loc_1C2549
0x1c251c  ldarg.s  4
0x1c251e  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x1c2523  brfalse.s loc_1C2549
0x1c2525  ldloc.2
0x1c2526  ldarg.s  4
0x1c2528  ldstr    aName// "name"
0x1c252d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1c2532  callvirt instance void Microsoft.Crm.AppConfig.NavigationSettingDefinition::set_Name(string value)
0x1c2537  ldloc.2
0x1c2538  ldarg.s  4
0x1c253a  ldstr    aDescription// "description"
0x1c253f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1c2544  callvirt instance void Microsoft.Crm.AppConfig.NavigationSettingDefinition::set_Description(string value)
0x1c2549  ldarg.0
0x1c254a  ldloc.0
0x1c254b  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.NavigationSetting
0x1c2550  ldloc.2
0x1c2551  ldarg.3
0x1c2552  call     instance void Microsoft.Crm.ObjectModel.AppConfigUtility::PopulateNavSettingEntity(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.NavigationSetting navigationSettingEntity, class Microsoft.Crm.AppConfig.NavigationSettingDefinition navigationSettingDefinition, valuetype [mscorlib]System.Guid appConfigId)
0x1c2557  br.s     loc_1C255A
0x1c2559  ret
0x1c255a  ldarga.s 1
0x1c255c  constrained. mvar<u1>
0x1c2562  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c2567  ldstr    aSolutionaction_5// "SolutionAction"
0x1c256c  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x1c2571  ldnull
0x1c2572  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Inequality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x1c2577  brfalse  loc_1C28D6
0x1c257c  ldarga.s 1
0x1c257e  constrained. mvar<u1>
0x1c2584  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c2589  ldstr    aSolutionaction_5// "SolutionAction"
0x1c258e  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x1c2593  ldarg.1
0x1c2594  box      mvar<u1>
0x1c2599  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x1c259e  castclass [mscorlib]System.String
0x1c25a3  stloc.3
0x1c25a4  ldnull
0x1c25a5  stloc.s  4
0x1c25a7  ldloc.3
0x1c25a8  ldstr    aUnmodified// "UnModified"
0x1c25ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c25b2  brtrue.s loc_1C25D6
0x1c25b4  ldloc.3
0x1c25b5  ldstr    aAdded// "Added"
0x1c25ba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c25bf  brtrue.s loc_1C2613
0x1c25c1  ldloc.3
0x1c25c2  ldstr    aModified_0// "Modified"
0x1c25c7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c25cc  brtrue   loc_1C289F
0x1c25d1  br       loc_1C28C5
0x1c25d6  ldloc.0
0x1c25d7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x1c25dc  unbox.any [mscorlib]System.Guid
0x1c25e1  ldloc.0
0x1c25e2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x1c25e7  ldarg.2
0x1c25e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c25ed  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x1c25f2  stloc.s  4
0x1c25f4  ldarg.s  5
0x1c25f6  brfalse.s loc_1C2605
0x1c25f8  ldloc.1
0x1c25f9  ldloc.0
0x1c25fa  ldarg.2
0x1c25fb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1c2600  br       loc_1C28C5
0x1c2605  ldloc.1
0x1c2606  ldloc.s  4
0x1c2608  ldarg.2
0x1c2609  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1c260e  br       loc_1C28C5
0x1c2613  ldarga.s 1
0x1c2615  constrained. mvar<u1>
0x1c261b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c2620  ldtoken  Microsoft.Crm.AppConfig.NavigationSettingDefinition
0x1c2625  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c262a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c262f  brfalse  loc_1C26EC
0x1c2634  ldarg.0
0x1c2635  ldloc.0
0x1c2636  ldstr    aNavigationsett// "navigationsettingid"
0x1c263b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c2640  unbox.any [mscorlib]System.Guid
0x1c2645  ldc.i4   0xFA
0x1c264a  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState Microsoft.Crm.ObjectModel.AppConfigUtility::RetrieveEntityStates(valuetype [mscorlib]System.Guid Id, int32 componentType)
0x1c264f  dup
0x1c2650  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetLastManagedEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState states)
0x1c2655  stloc.s  5
0x1c2657  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetPublishedCustomizationEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState states)
0x1c265c  stloc.s  6
0x1c265e  ldloc.s  5
0x1c2660  brfalse.s loc_1C268D
0x1c2662  ldloc.1
0x1c2663  ldloc.0
0x1c2664  ldarg.2
0x1c2665  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1c266a  ldloc.0
0x1c266b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x1c2670  unbox.any [mscorlib]System.Guid
0x1c2675  ldloc.0
0x1c2676  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x1c267b  ldarg.2
0x1c267c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c2681  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x1c2686  stloc.s  4
0x1c2688  br       loc_1C28C5
0x1c268d  ldloc.s  6
0x1c268f  brfalse  loc_1C2893
0x1c2694  ldloc.s  6
0x1c2696  ldstr    aIsmanaged// "ismanaged"
0x1c269b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c26a0  unbox.any [mscorlib]System.Boolean
0x1c26a5  brtrue   loc_1C2893
0x1c26aa  ldarg.2
0x1c26ab  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_ConvertToManaged()
0x1c26b0  stloc.s  7
0x1c26b2  ldarg.2
0x1c26b3  ldc.i4.1
0x1c26b4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::set_ConvertToManaged(bool)
0x1c26b9  ldloc.1
0x1c26ba  ldloc.0
0x1c26bb  ldarg.2
0x1c26bc  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1c26c1  ldloc.0
0x1c26c2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x1c26c7  unbox.any [mscorlib]System.Guid
0x1c26cc  ldloc.0
0x1c26cd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x1c26d2  ldarg.2
0x1c26d3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c26d8  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x1c26dd  stloc.s  4
0x1c26df  ldarg.2
0x1c26e0  ldloc.s  7
0x1c26e2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::set_ConvertToManaged(bool)
0x1c26e7  br       loc_1C28C5
0x1c26ec  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x1c26f1  ldarg.0
0x1c26f2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigUtility::_context
0x1c26f7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1c26fc  stloc.s  8
0x1c26fe  ldloc.s  8
0x1c2700  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c2705  ldc.i4.0
0x1c2706  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1c270b  ldloc.s  8
0x1c270d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c2712  ldstr    aAppconfigmaste// "appconfigmasterid"
0x1c2717  ldc.i4.0
0x1c2718  ldloc.0
0x1c2719  ldstr    aAppconfigmaste// "appconfigmasterid"
0x1c271e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c2723  unbox.any [mscorlib]System.Guid
0x1c2728  box      [mscorlib]System.Guid
0x1c272d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c2732  pop
0x1c2733  ldloc.s  8
0x1c2735  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c273a  ldstr    aAppconfigid// "appconfigid"
0x1c273f  ldc.i4.0
0x1c2740  ldarg.3
0x1c2741  box      [mscorlib]System.Guid
0x1c2746  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c274b  pop
0x1c274c  ldloc.0
0x1c274d  ldstr    aObjectid// "objectid"
0x1c2752  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c2757  brfalse.s loc_1C2781
0x1c2759  ldloc.s  8
0x1c275b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c2760  ldstr    aObjectid// "objectid"
0x1c2765  ldc.i4.0
0x1c2766  ldloc.0
0x1c2767  ldstr    aObjectid// "objectid"
0x1c276c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c2771  unbox.any [mscorlib]System.Guid
0x1c2776  box      [mscorlib]System.Guid
0x1c277b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c2780  pop
0x1c2781  ldloc.s  8
0x1c2783  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1c2788  ldstr    aComponentstate_0// "componentstate"
0x1c278d  ldc.i4.0
0x1c278e  ldc.i4.0
0x1c278f  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x1c2794  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1c2799  pop
0x1c279a  ldloc.s  8
0x1c279c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1c27a1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x1c27a6  ldarg.0
0x1c27a7  ldloc.s  8
0x1c27a9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.AppConfigUtility::RetrieveRawEntityRows(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression expression)
0x1c27ae  stloc.s  9
0x1c27b0  ldloc.s  9
0x1c27b2  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1c27b7  ldc.i4.0
0x1c27b8  ble      loc_1C2893
0x1c27bd  ldloc.0
0x1c27be  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x1c27c3  ldloc.s  9
0x1c27c5  ldc.i4.0
0x1c27c6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1c27cb  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x1c27d0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c27d5  unbox.any [mscorlib]System.Guid
0x1c27da  box      [mscorlib]System.Guid
0x1c27df  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1c27e4  ldarg.0
0x1c27e5  ldloc.0
0x1c27e6  ldstr    aAppconfiginsta// "appconfiginstanceid"
0x1c27eb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c27f0  unbox.any [mscorlib]System.Guid
0x1c27f5  ldc.i4   0xC0
0x1c27fa  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState Microsoft.Crm.ObjectModel.AppConfigUtility::RetrieveEntityStates(valuetype [mscorlib]System.Guid Id, int32 componentType)
0x1c27ff  dup
0x1c2800  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetLastManagedEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState states)
0x1c2805  stloc.s  0xA
0x1c2807  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetPublishedCustomizationEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState states)
0x1c280c  stloc.s  0xB
0x1c280e  ldloc.s  0xA
0x1c2810  brfalse.s loc_1C283D
0x1c2812  ldloc.1
0x1c2813  ldloc.0
0x1c2814  ldarg.2
0x1c2815  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1c281a  ldloc.0
0x1c281b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x1c2820  unbox.any [mscorlib]System.Guid
0x1c2825  ldloc.0
0x1c2826  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x1c282b  ldarg.2
0x1c282c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c2831  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x1c2836  stloc.s  4
0x1c2838  br       loc_1C28C5
0x1c283d  ldloc.s  0xB
0x1c283f  brfalse.s loc_1C2893
0x1c2841  ldloc.s  0xB
0x1c2843  ldstr    aIsmanaged// "ismanaged"
0x1c2848  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c284d  unbox.any [mscorlib]System.Boolean
0x1c2852  brtrue.s loc_1C2893
0x1c2854  ldarg.2
0x1c2855  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_ConvertToManaged()
0x1c285a  stloc.s  0xC
0x1c285c  ldarg.2
0x1c285d  ldc.i4.1
0x1c285e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::set_ConvertToManaged(bool)
0x1c2863  ldloc.1
0x1c2864  ldloc.0
0x1c2865  ldarg.2
0x1c2866  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
  ... truncated ...
```
