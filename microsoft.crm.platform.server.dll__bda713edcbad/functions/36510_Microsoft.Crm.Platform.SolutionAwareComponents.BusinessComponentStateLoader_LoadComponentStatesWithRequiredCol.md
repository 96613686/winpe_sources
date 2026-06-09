# Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateLoader::LoadComponentStatesWithRequiredColumns

- ea: `0x36510`
- end: `0x36691`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateLoader::LoadComponentStatesWithRequiredColumns`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x36430`

## callees

- `0x13b50`
- `0x13eb0`
- `0x184b0`
- `0x18520`
- `0x18540`
- `0x18560`
- `0x1af20`
- `0x1cfc0`
- `0x35b70`
- `0x35b90`
- `0x35bd0`
- `0x35bf0`
- `0x35f10`
- `0x36340`
- `0x36510`
- `0x366a0`
- `0x66ae0`

## string_xrefs

- `0x365d1`: `componentstate`
- `0x365de`: `componentstate`
- `0x36665`: `componentstate`
- `0x36544`: `OverwriteTime`
- `0x36593`: `overwritetime`
- `0x36641`: `overwritetime`
- `0x36650`: `overwritetime`
- `0x36555`: `ComponentState`

## pseudocode

```c

```

## disassembly

```asm
0x36510  ldarg.2
0x36511  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x36516  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x3651b  ldarg.2
0x3651c  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x36521  ldc.i4.2
0x36522  ldstr    aSolutionid_1// "SolutionId"
0x36527  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType mapping, string attributeName)
0x3652c  ldarg.2
0x3652d  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x36532  ldc.i4.2
0x36533  ldstr    aSupportingsolu_1// "SupportingSolutionId"
0x36538  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType mapping, string attributeName)
0x3653d  ldarg.2
0x3653e  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x36543  ldc.i4.2
0x36544  ldstr    aOverwritetime// "OverwriteTime"
0x36549  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType mapping, string attributeName)
0x3654e  ldarg.2
0x3654f  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x36554  ldc.i4.2
0x36555  ldstr    aComponentstate_3// "ComponentState"
0x3655a  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType mapping, string attributeName)
0x3655f  ldarg.2
0x36560  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x36565  ldc.i4.2
0x36566  ldarg.2
0x36567  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x3656c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_UniqueIdAttribute()
0x36571  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x36576  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType mapping, string attributeName)
0x3657b  ldarg.2
0x3657c  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x36581  ldarg.1
0x36582  box      [mscorlib]System.Guid
0x36587  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddPrimaryKeyCondition(object primaryKeyValue)
0x3658c  pop
0x3658d  ldarg.2
0x3658e  callvirt instance class Microsoft.Crm.Query.OrderExpression Microsoft.Crm.Query.EntityExpression::get_Order()
0x36593  ldstr    aOverwritetime_0// "overwritetime"
0x36598  ldc.i4.0
0x36599  callvirt instance void Microsoft.Crm.Query.OrderExpression::AddOrder(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType orderType)
0x3659e  ldarg.0
0x3659f  ldarg.2
0x365a0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x365a5  ldarg.2
0x365a6  ldarg.3
0x365a7  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity[] Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentStateLoader::ReadRawComponentRows(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, class Microsoft.Crm.Query.EntityExpression expression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x365ac  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::.ctor()
0x365b1  stloc.0
0x365b2  stloc.1
0x365b3  ldc.i4.0
0x365b4  stloc.2
0x365b5  br       loc_36686
0x365ba  ldloc.1
0x365bb  ldloc.2
0x365bc  ldelem.ref
0x365bd  stloc.3
0x365be  ldloc.3
0x365bf  ldstr    aSolutionid_0// "solutionid"
0x365c4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x365c9  unbox.any [mscorlib]System.Guid
0x365ce  stloc.s  4
0x365d0  ldloc.3
0x365d1  ldstr    aComponentstate// "componentstate"
0x365d6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x365db  brtrue.s loc_365EF
0x365dd  ldloc.3
0x365de  ldstr    aComponentstate// "componentstate"
0x365e3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x365e8  unbox.any [mscorlib]System.Int32
0x365ed  br.s     loc_365F0
0x365ef  ldc.i4.0
0x365f0  stloc.s  5
0x365f2  ldloc.3
0x365f3  ldarg.0
0x365f4  ldloc.s  4
0x365f6  ldloc.s  5
0x365f8  ldloc.3
0x365f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x365fe  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsPublishable()
0x36603  ldarg.3
0x36604  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x36609  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::GetComponentRowState(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState componentState, bool isPublishable, class [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext context)
0x3660e  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType)
0x36613  stloc.s  6
0x36615  ldloc.s  6
0x36617  ldloc.s  4
0x36619  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_SolutionId(valuetype [mscorlib]System.Guid value)
0x3661e  ldloc.s  6
0x36620  ldloc.3
0x36621  ldloc.3
0x36622  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x36627  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_UniqueIdAttribute()
0x3662c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x36631  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x36636  unbox.any [mscorlib]System.Guid
0x3663b  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_RowGuidId(valuetype [mscorlib]System.Guid value)
0x36640  ldloc.3
0x36641  ldstr    aOverwritetime_0// "overwritetime"
0x36646  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x3664b  brtrue.s loc_36664
0x3664d  ldloc.s  6
0x3664f  ldloc.3
0x36650  ldstr    aOverwritetime_0// "overwritetime"
0x36655  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3665a  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3665f  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_OverwriteTime(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime value)
0x36664  ldloc.3
0x36665  ldstr    aComponentstate// "componentstate"
0x3666a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x3666f  brtrue.s loc_3667A
0x36671  ldloc.s  6
0x36673  ldloc.s  5
0x36675  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_ComponentState(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState value)
0x3667a  ldloc.0
0x3667b  ldloc.s  6
0x3667d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x36682  ldloc.2
0x36683  ldc.i4.1
0x36684  add
0x36685  stloc.2
0x36686  ldloc.2
0x36687  ldloc.1
0x36688  ldlen
0x36689  conv.i4
0x3668a  blt      loc_365BA
0x3668f  ldloc.0
0x36690  ret
```
