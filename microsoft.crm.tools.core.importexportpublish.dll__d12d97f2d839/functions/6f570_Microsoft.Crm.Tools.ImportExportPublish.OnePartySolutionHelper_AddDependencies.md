# Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::AddDependencies

- ea: `0x6f570`
- end: `0x6f713`
- name: `Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::AddDependencies`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x75980`

## callees

- `0x2bec0`
- `0x2c3d0`
- `0x6f570`
- `0x72790`
- `0x72c30`

## string_xrefs

- `0x6f5d3`: `componenttype`
- `0x6f608`: `componenttype`
- `0x6f657`: `componenttype`
- `0x6f59f`: `SolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x6f570  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x6f575  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x6f57a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x6f57f  ldarg.0
0x6f580  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_context
0x6f585  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6f58a  brtrue.s loc_6F58D
0x6f58c  ret
0x6f58d  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x6f592  stloc.0
0x6f593  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x6f598  stloc.1
0x6f599  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x6f59e  stloc.2
0x6f59f  ldstr    aSolutioncompon// "SolutionComponent"
0x6f5a4  ldarg.0
0x6f5a5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_context
0x6f5aa  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6f5af  stloc.3
0x6f5b0  ldloc.3
0x6f5b1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x6f5b6  ldstr    aSolutionid// "solutionid"
0x6f5bb  ldc.i4.0
0x6f5bc  ldarg.0
0x6f5bd  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_solutionId
0x6f5c2  box      [mscorlib]System.Guid
0x6f5c7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6f5cc  pop
0x6f5cd  ldloc.3
0x6f5ce  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x6f5d3  ldstr    aComponenttype// "componenttype"
0x6f5d8  ldc.i4.8
0x6f5d9  ldc.i4.1
0x6f5da  newarr   [mscorlib]System.Object
0x6f5df  dup
0x6f5e0  ldc.i4.0
0x6f5e1  ldc.i4   0xA9
0x6f5e6  box      [mscorlib]System.Int32
0x6f5eb  stelem.ref
0x6f5ec  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x6f5f1  pop
0x6f5f2  ldloc.3
0x6f5f3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x6f5f8  ldc.i4.4
0x6f5f9  newarr   [mscorlib]System.String
0x6f5fe  dup
0x6f5ff  ldc.i4.0
0x6f600  ldstr    aObjectid// "objectid"
0x6f605  stelem.ref
0x6f606  dup
0x6f607  ldc.i4.1
0x6f608  ldstr    aComponenttype// "componenttype"
0x6f60d  stelem.ref
0x6f60e  dup
0x6f60f  ldc.i4.2
0x6f610  ldstr    aSolutionid// "solutionid"
0x6f615  stelem.ref
0x6f616  dup
0x6f617  ldc.i4.3
0x6f618  ldstr    aIsmetadata// "ismetadata"
0x6f61d  stelem.ref
0x6f61e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x6f623  ldloc.0
0x6f624  ldloc.3
0x6f625  ldarg.0
0x6f626  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_context
0x6f62b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6f630  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6f635  stloc.s  4
0x6f637  br.s     loc_6F68E
0x6f639  ldloc.s  4
0x6f63b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6f640  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent
0x6f645  dup
0x6f646  ldstr    aObjectid// "objectid"
0x6f64b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6f650  unbox.any [mscorlib]System.Guid
0x6f655  stloc.s  5
0x6f657  ldstr    aComponenttype// "componenttype"
0x6f65c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6f661  unbox.any [mscorlib]System.Int32
0x6f666  stloc.s  6
0x6f668  ldloc.s  6
0x6f66a  ldc.i4   0xA9
0x6f66f  beq.s    loc_6F67C
0x6f671  ldloc.s  6
0x6f673  ldc.i4   0xAC
0x6f678  beq.s    loc_6F686
0x6f67a  br.s     loc_6F68E
0x6f67c  ldloc.1
0x6f67d  ldloc.s  5
0x6f67f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x6f684  br.s     loc_6F68E
0x6f686  ldloc.2
0x6f687  ldloc.s  5
0x6f689  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x6f68e  ldloc.s  4
0x6f690  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6f695  brtrue.s loc_6F639
0x6f697  leave.s  loc_6F6AE
0x6f699  ldloc.s  4
0x6f69b  isinst   [mscorlib]System.IDisposable
0x6f6a0  stloc.s  7
0x6f6a2  ldloc.s  7
0x6f6a4  brfalse.s loc_6F6AD
0x6f6a6  ldloc.s  7
0x6f6a8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6f6ad  endfinally
0x6f6ae  ldloc.1
0x6f6af  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x6f6b4  ldc.i4.0
0x6f6b5  ble.s    loc_6F6E6
0x6f6b7  ldloc.1
0x6f6b8  ldarg.0
0x6f6b9  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_solutionName
0x6f6be  ldarg.0
0x6f6bf  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_context
0x6f6c4  ldarg.0
0x6f6c5  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_tracer
0x6f6ca  ldarg.0
0x6f6cb  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_cache
0x6f6d0  ldarg.0
0x6f6d1  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_exportDeltaOverride
0x6f6d6  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::.ctor(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> profileRules, string solutionName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, bool exportDeltaOverride)
0x6f6db  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::AddProfileRuleDependencies()
0x6f6e0  ldloc.1
0x6f6e1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0x6f6e6  ldloc.2
0x6f6e7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x6f6ec  ldc.i4.0
0x6f6ed  ble.s    loc_6F712
0x6f6ef  ldloc.2
0x6f6f0  ldarg.0
0x6f6f1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_context
0x6f6f6  ldarg.0
0x6f6f7  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_tracer
0x6f6fc  ldarg.0
0x6f6fd  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.OnePartySolutionHelper::_exportDeltaOverride
0x6f702  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::.ctor(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> channelAccessProfiles, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, bool exportDeltaOverride)
0x6f707  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::AddChannelAccessProfileDependencies()
0x6f70c  ldloc.2
0x6f70d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0x6f712  ret
```
