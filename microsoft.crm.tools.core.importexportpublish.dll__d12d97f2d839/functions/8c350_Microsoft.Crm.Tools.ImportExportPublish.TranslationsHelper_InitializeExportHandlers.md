# Microsoft.Crm.Tools.ImportExportPublish.TranslationsHelper::InitializeExportHandlers

- ea: `0x8c350`
- end: `0x8c6f2`
- name: `Microsoft.Crm.Tools.ImportExportPublish.TranslationsHelper::InitializeExportHandlers`
- size: `930`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x825d0`
- `0x827f0`

## callees

- `0x180f0`
- `0x27500`
- `0x2a480`
- `0x2cae0`
- `0x2e940`
- `0x3a890`
- `0x3ae80`
- `0x70170`
- `0x74b20`
- `0x77480`
- `0x87810`
- `0x88bc0`
- `0x89360`
- `0x8c350`
- `0x8c700`
- `0x8d340`

## string_xrefs

- `0x8c3df`: `componenttype`
- `0x8c403`: `componenttype`
- `0x8c443`: `componenttype`
- `0x8c3b0`: `SolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x8c350  ldc.i4.7
0x8c351  newarr   [mscorlib]System.Int32
0x8c356  dup
0x8c357  ldtoken  valuetype __StaticArrayInitTypeSize=28 <PrivateImplementationDetails>::'4EEB5D964BBDE7F4887CC20D82E79C3A00D8E6B0'
0x8c35c  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x8c361  stloc.0
0x8c362  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x8c367  stloc.1
0x8c368  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x8c36d  stloc.2
0x8c36e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x8c373  stloc.3
0x8c374  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x8c379  stloc.s  4
0x8c37b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x8c380  stloc.s  5
0x8c382  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x8c387  stloc.s  6
0x8c389  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x8c38e  stloc.s  7
0x8c390  ldarg.0
0x8c391  ldarg.s  4
0x8c393  call     class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Solution Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::GetSolution(string solutionName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8c398  ldstr    aSolutionid// "solutionid"
0x8c39d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8c3a2  unbox.any [mscorlib]System.Guid
0x8c3a7  stloc.s  8
0x8c3a9  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x8c3ae  stloc.s  9
0x8c3b0  ldstr    aSolutioncompon// "SolutionComponent"
0x8c3b5  ldarg.s  4
0x8c3b7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x8c3bc  stloc.s  0xA
0x8c3be  ldloc.s  0xA
0x8c3c0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x8c3c5  ldstr    aSolutionid// "solutionid"
0x8c3ca  ldc.i4.0
0x8c3cb  ldloc.s  8
0x8c3cd  box      [mscorlib]System.Guid
0x8c3d2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x8c3d7  pop
0x8c3d8  ldloc.s  0xA
0x8c3da  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x8c3df  ldstr    aComponenttype// "componenttype"
0x8c3e4  ldc.i4.8
0x8c3e5  ldloc.0
0x8c3e6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x8c3eb  pop
0x8c3ec  ldloc.s  0xA
0x8c3ee  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8c3f3  ldc.i4.2
0x8c3f4  newarr   [mscorlib]System.String
0x8c3f9  dup
0x8c3fa  ldc.i4.0
0x8c3fb  ldstr    aObjectid// "objectid"
0x8c400  stelem.ref
0x8c401  dup
0x8c402  ldc.i4.1
0x8c403  ldstr    aComponenttype// "componenttype"
0x8c408  stelem.ref
0x8c409  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x8c40e  ldloc.s  9
0x8c410  ldloc.s  0xA
0x8c412  ldarg.s  4
0x8c414  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8c419  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x8c41e  stloc.s  0xD
0x8c420  br       loc_8C4E2
0x8c425  ldloc.s  0xD
0x8c427  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8c42c  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent
0x8c431  dup
0x8c432  ldstr    aObjectid// "objectid"
0x8c437  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8c43c  unbox.any [mscorlib]System.Guid
0x8c441  stloc.s  0xE
0x8c443  ldstr    aComponenttype// "componenttype"
0x8c448  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8c44d  unbox.any [mscorlib]System.Int32
0x8c452  stloc.s  0xF
0x8c454  ldloc.s  0xF
0x8c456  ldc.i4.s 0x1D
0x8c458  bgt.s    loc_8C46D
0x8c45a  ldloc.s  0xF
0x8c45c  ldc.i4.1
0x8c45d  beq.s    loc_8C48F
0x8c45f  ldloc.s  0xF
0x8c461  ldc.i4.s 9
0x8c463  beq.s    loc_8C4A4
0x8c465  ldloc.s  0xF
0x8c467  ldc.i4.s 0x1D
0x8c469  beq.s    loc_8C4C3
0x8c46b  br.s     loc_8C4E2
0x8c46d  ldloc.s  0xF
0x8c46f  ldc.i4.s 0x3C
0x8c471  bgt.s    loc_8C481
0x8c473  ldloc.s  0xF
0x8c475  ldc.i4.s 0x32
0x8c477  beq.s    loc_8C4B8
0x8c479  ldloc.s  0xF
0x8c47b  ldc.i4.s 0x3C
0x8c47d  beq.s    loc_8C4AE
0x8c47f  br.s     loc_8C4E2
0x8c481  ldloc.s  0xF
0x8c483  ldc.i4.s 0x3E
0x8c485  beq.s    loc_8C4D9
0x8c487  ldloc.s  0xF
0x8c489  ldc.i4.s 0x50
0x8c48b  beq.s    loc_8C4CE
0x8c48d  br.s     loc_8C4E2
0x8c48f  ldloc.1
0x8c490  ldloc.s  0xE
0x8c492  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x8c497  ldloc.s  0xE
0x8c499  ldloc.s  5
0x8c49b  ldarg.s  4
0x8c49d  call     void Microsoft.Crm.Tools.ImportExportPublish.TranslationsHelper::AddBusinessRulesToComponentList(valuetype [mscorlib]System.Guid entityId, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> solutionComponentWorkflowList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8c4a2  br.s     loc_8C4E2
0x8c4a4  ldloc.2
0x8c4a5  ldloc.s  0xE
0x8c4a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x8c4ac  br.s     loc_8C4E2
0x8c4ae  ldloc.3
0x8c4af  ldloc.s  0xE
0x8c4b1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x8c4b6  br.s     loc_8C4E2
0x8c4b8  ldloc.s  4
0x8c4ba  ldloc.s  0xE
0x8c4bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x8c4c1  br.s     loc_8C4E2
0x8c4c3  ldloc.s  5
0x8c4c5  ldloc.s  0xE
0x8c4c7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x8c4cc  br.s     loc_8C4E2
0x8c4ce  ldloc.s  6
0x8c4d0  ldloc.s  0xE
0x8c4d2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x8c4d7  br.s     loc_8C4E2
0x8c4d9  ldloc.s  7
0x8c4db  ldloc.s  0xE
0x8c4dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x8c4e2  ldloc.s  0xD
0x8c4e4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8c4e9  brtrue   loc_8C425
0x8c4ee  leave.s  loc_8C505
0x8c4f0  ldloc.s  0xD
0x8c4f2  isinst   [mscorlib]System.IDisposable
0x8c4f7  stloc.s  0x10
0x8c4f9  ldloc.s  0x10
0x8c4fb  brfalse.s loc_8C504
0x8c4fd  ldloc.s  0x10
0x8c4ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c504  endfinally
0x8c505  ldarg.s  4
0x8c507  ldarg.2
0x8c508  ldarg.3
0x8c509  ldarg.0
0x8c50a  ldc.i4.0
0x8c50b  ldc.i4.0
0x8c50c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dmc, string solutionName, bool managed, bool exportDeltaOverride)
0x8c511  stloc.s  0xB
0x8c513  ldarg.1
0x8c514  ldloc.s  0xB
0x8c516  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8c51b  pop
0x8c51c  ldarg.3
0x8c51d  call     class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::GetCustomizableEntityList(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x8c522  ldarg.s  4
0x8c524  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8c529  stloc.s  0xC
0x8c52b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<int32>::GetEnumerator()
0x8c530  stloc.s  0x11
0x8c532  br       loc_8C617
0x8c537  ldloca.s 0x11
0x8c539  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::get_Current()
0x8c53e  stloc.s  0x12
0x8c540  ldarg.3
0x8c541  ldloc.s  0x12
0x8c543  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x8c548  stloc.s  0x13
0x8c54a  ldloc.1
0x8c54b  ldloc.s  0x13
0x8c54d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x8c552  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x8c557  brfalse  loc_8C617
0x8c55c  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RibbonCustomizationService::.ctor()
0x8c561  ldstr    aRibboncustomiz// "RibbonCustomization"
0x8c566  ldarg.s  4
0x8c568  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x8c56d  stloc.s  0x14
0x8c56f  ldloc.s  0x14
0x8c571  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x8c576  ldstr    aEntity// "entity"
0x8c57b  ldc.i4.0
0x8c57c  ldloc.s  0x13
0x8c57e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x8c583  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x8c588  pop
0x8c589  ldloc.s  0x14
0x8c58b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8c590  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x8c595  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x8c59a  ldloc.s  0x14
0x8c59c  ldarg.s  4
0x8c59e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8c5a3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x8c5a8  stloc.s  0x15
0x8c5aa  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x8c5af  stloc.s  0xD
0x8c5b1  br.s     loc_8C5D9
0x8c5b3  ldloc.s  0xD
0x8c5b5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8c5ba  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x8c5bf  stloc.s  0x16
0x8c5c1  ldloc.s  0x15
0x8c5c3  ldloc.s  0x16
0x8c5c5  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x8c5ca  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8c5cf  unbox.any [mscorlib]System.Guid
0x8c5d4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x8c5d9  ldloc.s  0xD
0x8c5db  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8c5e0  brtrue.s loc_8C5B3
0x8c5e2  leave.s  loc_8C5F9
0x8c5e4  ldloc.s  0xD
0x8c5e6  isinst   [mscorlib]System.IDisposable
0x8c5eb  stloc.s  0x10
0x8c5ed  ldloc.s  0x10
0x8c5ef  brfalse.s loc_8C5F8
0x8c5f1  ldloc.s  0x10
0x8c5f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c5f8  endfinally
0x8c5f9  ldloc.s  0xC
0x8c5fb  ldarg.1
0x8c5fc  ldloc.s  0x13
0x8c5fe  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x8c603  ldloc.s  0x12
0x8c605  ldarg.3
0x8c606  ldarg.s  4
0x8c608  ldarg.2
0x8c609  ldloc.s  0x15
0x8c60b  ldloc.s  8
0x8c60d  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.EntityHandler::.ctor(string entityName, int32 objectTypeCode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dmc, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext ec, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> relatedRibbonCustomizations, valuetype [mscorlib]System.Guid solutionId)
0x8c612  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::AddHandler(class [mscorlib]System.Collections.ArrayList handlers, class Microsoft.Crm.Tools.ImportExportPublish.ExportHandler handler)
0x8c617  ldloca.s 0x11
0x8c619  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::MoveNext()
0x8c61e  brtrue   loc_8C537
0x8c623  leave.s  loc_8C633
0x8c625  ldloca.s 0x11
0x8c627  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>
0x8c62d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c632  endfinally
0x8c633  ldloc.s  0xC
0x8c635  ldarg.1
0x8c636  ldarg.2
0x8c637  ldarg.3
0x8c638  ldloc.2
0x8c639  ldarg.s  4
0x8c63b  ldc.i4.0
0x8c63c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.OptionSetsHandler::.ctor(class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dmc, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> solutionComponentOptionSetSet, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool exportDeltaOverride)
0x8c641  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::AddHandler(class [mscorlib]System.Collections.ArrayList handlers, class Microsoft.Crm.Tools.ImportExportPublish.ExportHandler handler)
0x8c646  ldloc.s  0xC
0x8c648  ldarg.1
0x8c649  ldarg.s  4
0x8c64b  ldarg.2
0x8c64c  ldloc.3
0x8c64d  ldc.i4.0
0x8c64e  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> solutionComponentDashboardSet, bool exportDeltaOverride)
0x8c653  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::AddHandler(class [mscorlib]System.Collections.ArrayList handlers, class Microsoft.Crm.Tools.ImportExportPublish.ExportHandler handler)
0x8c658  ldloc.s  0xC
0x8c65a  ldarg.1
0x8c65b  ldarg.s  4
0x8c65d  ldarg.2
0x8c65e  ldloc.3
0x8c65f  ldc.i4.0
0x8c660  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> solutionComponentDialogSet, bool exportDeltaOverride)
0x8c665  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::AddHandler(class [mscorlib]System.Collections.ArrayList handlers, class Microsoft.Crm.Tools.ImportExportPublish.ExportHandler handler)
0x8c66a  ldloc.s  0xC
0x8c66c  ldarg.1
0x8c66d  ldarg.s  4
0x8c66f  ldarg.2
0x8c670  ldloc.s  4
0x8c672  ldc.i4.0
0x8c673  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonsHandler::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> relatedRibbonCustomizations, bool exportDeltaOverride)
0x8c678  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::AddHandler(class [mscorlib]System.Collections.ArrayList handlers, class Microsoft.Crm.Tools.ImportExportPublish.ExportHandler handler)
0x8c67d  ldloc.s  0xC
0x8c67f  ldarg.1
0x8c680  ldarg.2
0x8c681  ldarg.3
0x8c682  ldloc.s  5
0x8c684  ldarg.s  4
0x8c686  ldc.i4.0
0x8c687  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::.ctor(class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> solutionComponentWorkflowList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool exportDeltaOverride)
0x8c68c  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::AddHandler(class [mscorlib]System.Collections.ArrayList handlers, class Microsoft.Crm.Tools.ImportExportPublish.ExportHandler handler)
0x8c691  ldloc.s  0xC
0x8c693  ldarg.1
0x8c694  ldarg.s  4
0x8c696  ldarg.2
0x8c697  ldarg.3
0x8c698  ldloc.s  7
  ... truncated ...
```
