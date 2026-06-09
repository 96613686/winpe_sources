# Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::InitializeProfileHandlers

- ea: `0x77230`
- end: `0x773b0`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::InitializeProfileHandlers`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x75ef0`

## callees

- `0x72380`
- `0x764c0`
- `0x77230`
- `0x97590`

## string_xrefs

- `0x77242`: `FieldSecurityProfile`
- `0x77261`: `fieldsecurityprofileid`
- `0x77291`: `fieldsecurityprofileid`
- `0x772a3`: `fieldsecurityprofileid`
- `0x772f9`: `fieldsecurityprofileid`

## pseudocode

```c

```

## disassembly

```asm
0x77230  ldarg.1
0x77231  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x77236  ldc.i4.0
0x77237  ble      loc_773AF
0x7723c  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FieldSecurityProfileService::.ctor()
0x77241  stloc.0
0x77242  ldstr    aFieldsecurityp// "FieldSecurityProfile"
0x77247  ldarg.0
0x77248  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x7724d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x77252  stloc.1
0x77253  ldloc.1
0x77254  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x77259  ldc.i4.4
0x7725a  newarr   [mscorlib]System.String
0x7725f  dup
0x77260  ldc.i4.0
0x77261  ldstr    aFieldsecurityp_0// "fieldsecurityprofileid"
0x77266  stelem.ref
0x77267  dup
0x77268  ldc.i4.1
0x77269  ldstr    aName// "name"
0x7726e  stelem.ref
0x7726f  dup
0x77270  ldc.i4.2
0x77271  ldstr    aDescription// "description"
0x77276  stelem.ref
0x77277  dup
0x77278  ldc.i4.3
0x77279  ldstr    aSolutionid// "solutionid"
0x7727e  stelem.ref
0x7727f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x77284  ldloc.1
0x77285  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x7728a  ldc.i4.0
0x7728b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x77290  dup
0x77291  ldstr    aFieldsecurityp_0// "fieldsecurityprofileid"
0x77296  ldc.i4.8
0x77297  ldarg.1
0x77298  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x7729d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x772a2  pop
0x772a3  ldstr    aFieldsecurityp_0// "fieldsecurityprofileid"
0x772a8  ldc.i4.1
0x772a9  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.FieldLevelSecurityConstants::AdminProfileGuid
0x772ae  box      [mscorlib]System.Guid
0x772b3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x772b8  pop
0x772b9  ldloc.0
0x772ba  ldloc.1
0x772bb  ldarg.0
0x772bc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x772c1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x772c6  stloc.2
0x772c7  ldloc.2
0x772c8  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x772cd  ldc.i4.0
0x772ce  ble      loc_773AF
0x772d3  ldloc.2
0x772d4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x772d9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Item>::.ctor(int32)
0x772de  stloc.3
0x772df  ldloc.2
0x772e0  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x772e5  stloc.s  4
0x772e7  br.s     loc_7732E
0x772e9  ldloc.s  4
0x772eb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x772f0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x772f5  stloc.s  5
0x772f7  ldloc.s  5
0x772f9  ldstr    aFieldsecurityp_0// "fieldsecurityprofileid"
0x772fe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x77303  unbox.any [mscorlib]System.Guid
0x77308  stloc.s  6
0x7730a  ldloc.s  5
0x7730c  ldstr    aName// "name"
0x77311  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x77316  castclass [mscorlib]System.String
0x7731b  stloc.s  7
0x7731d  ldloc.3
0x7731e  ldloc.s  7
0x77320  ldloc.s  6
0x77322  ldloc.s  5
0x77324  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Item::.ctor(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x77329  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Item>::Add(var<u1>)
0x7732e  ldloc.s  4
0x77330  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x77335  brtrue.s loc_772E9
0x77337  leave.s  loc_7734E
0x77339  ldloc.s  4
0x7733b  isinst   [mscorlib]System.IDisposable
0x77340  stloc.s  8
0x77342  ldloc.s  8
0x77344  brfalse.s loc_7734D
0x77346  ldloc.s  8
0x77348  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7734d  endfinally
0x7734e  ldloc.3
0x7734f  newobj   instance void ListComparer::.ctor()
0x77354  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Item>::Sort(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x77359  ldloc.3
0x7735a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Item>::GetEnumerator()
0x7735f  stloc.s  9
0x77361  br.s     loc_77396
0x77363  ldloca.s 9
0x77365  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Item>::get_Current()
0x7736a  stloc.s  0xA
0x7736c  ldarg.0
0x7736d  ldloc.s  0xA
0x7736f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Item::get_Entity()
0x77374  ldarg.0
0x77375  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::cache
0x7737a  ldarg.0
0x7737b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::context
0x77380  ldarg.0
0x77381  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::tracer
0x77386  ldarg.0
0x77387  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::_exportDeltaOverride
0x7738c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity profile, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, bool exportDeltaOverride)
0x77391  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::AddHandler(class Microsoft.Crm.Tools.ImportExportPublish.ExportHandler handler)
0x77396  ldloca.s 9
0x77398  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Item>::MoveNext()
0x7739d  brtrue.s loc_77363
0x7739f  leave.s  loc_773AF
0x773a1  ldloca.s 9
0x773a3  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Item>
0x773a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x773ae  endfinally
0x773af  ret
```
