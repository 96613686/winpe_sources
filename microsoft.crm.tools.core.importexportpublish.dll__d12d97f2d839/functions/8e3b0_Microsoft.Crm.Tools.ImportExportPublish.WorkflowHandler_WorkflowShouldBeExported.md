# Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::WorkflowShouldBeExported

- ea: `0x8e3b0`
- end: `0x8e692`
- name: `Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::WorkflowShouldBeExported`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x8d3d0`

## callees

- `0x39460`
- `0x3a470`
- `0x3a520`
- `0x3aa70`
- `0x3af00`
- `0x76c00`
- `0x76cb0`
- `0x8d120`
- `0x8e3b0`
- `0x8e6a0`
- `0x8e710`
- `0x8e760`

## string_xrefs

- `0x8e43d`: `Workflow.TaskBasedFlow.ExportAs.TaskFlow.FilteredMessage`
- `0x8e4eb`: `Workflow.TaskBasedFlow.ExportAs.BusinessRule.FilteredMessage`
- `0x8e640`: `solutioncomponentid`
- `0x8e679`: `solutioncomponentid`

## pseudocode

```c

```

## disassembly

```asm
0x8e3b0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x8e3b5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x8e3ba  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_BpfActionSupportPUV2GA()
0x8e3bf  ldarg.0
0x8e3c0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::context
0x8e3c5  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8e3ca  stloc.0
0x8e3cb  ldarg.0
0x8e3cc  ldarg.1
0x8e3cd  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::VerifyIfBpfHasActionStep(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflowEntity)
0x8e3d2  brtrue.s loc_8E3DD
0x8e3d4  ldarg.0
0x8e3d5  ldarg.1
0x8e3d6  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::CheckIfOnDemandPA(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflow)
0x8e3db  br.s     loc_8E3DE
0x8e3dd  ldc.i4.1
0x8e3de  brfalse.s loc_8E3F8
0x8e3e0  ldloc.0
0x8e3e1  brtrue.s loc_8E3F8
0x8e3e3  ldc.i4   0x80060382
0x8e3e8  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x8e3ed  ldc.i4   0x80060382
0x8e3f2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x8e3f7  throw
0x8e3f8  ldarg.0
0x8e3f9  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::get_ExportToTargetVersionContext()
0x8e3fe  brfalse  loc_8E48F
0x8e403  ldarg.1
0x8e404  ldstr    aWorkflowid_0// "workflowid"
0x8e409  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e40e  unbox.any [mscorlib]System.Guid
0x8e413  ldc.i4.s 0x1D
0x8e415  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0)
0x8e41a  stloc.s  4
0x8e41c  ldc.i4.1
0x8e41d  ldarg.0
0x8e41e  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::get_ExportToTargetVersionContext()
0x8e423  ldloc.s  4
0x8e425  callvirt instance valuetype Microsoft.Crm.Tools.ImportExportPublish.ComponentAction Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::ActionToBeTakenOnComponent(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32> dependentComponent)
0x8e42a  bne.un.s loc_8E42E
0x8e42c  ldc.i4.0
0x8e42d  ret
0x8e42e  ldarg.1
0x8e42f  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.BusinessEntityExtension::IsTaskBasedFlow(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x8e434  brfalse.s loc_8E48F
0x8e436  ldsfld   bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ApplicationXmlDiffCalculatorBase::IsTargetVersionSupportsTaskBasedFlow
0x8e43b  brtrue.s loc_8E48F
0x8e43d  ldstr    aWorkflowTaskba_0// "Workflow.TaskBasedFlow.ExportAs.TaskFlo"...
0x8e442  ldarg.0
0x8e443  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::context
0x8e448  ldc.i4.1
0x8e449  newarr   [mscorlib]System.Object
0x8e44e  dup
0x8e44f  ldc.i4.0
0x8e450  ldarg.1
0x8e451  ldstr    aName// "name"
0x8e456  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e45b  stelem.ref
0x8e45c  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x8e461  stloc.s  5
0x8e463  ldarg.1
0x8e464  ldstr    aWorkflowid_0// "workflowid"
0x8e469  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e46e  unbox.any [mscorlib]System.Guid
0x8e473  ldc.i4.s 0x1D
0x8e475  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0)
0x8e47a  stloc.s  6
0x8e47c  ldarg.0
0x8e47d  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::get_ExportToTargetVersionContext()
0x8e482  ldloc.s  6
0x8e484  ldc.i4.1
0x8e485  ldloc.s  5
0x8e487  ldc.i4.0
0x8e488  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::AddFilteredComponentAndComment(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32> dependentComponent, valuetype Microsoft.Crm.Tools.ImportExportPublish.FilteredComponentAction action, string comment, bool addToExistingComments)
0x8e48d  ldc.i4.0
0x8e48e  ret
0x8e48f  ldarg.1
0x8e490  ldstr    aCategory// "category"
0x8e495  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e49a  unbox.any [mscorlib]System.Int32
0x8e49f  ldc.i4.0
0x8e4a0  stloc.1
0x8e4a1  ldc.i4.2
0x8e4a2  beq.s    loc_8E4A6
0x8e4a4  ldc.i4.1
0x8e4a5  ret
0x8e4a6  ldloca.s 2
0x8e4a8  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x8e4ae  ldarg.1
0x8e4af  ldarg.0
0x8e4b0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::context
0x8e4b5  ldloca.s 2
0x8e4b7  call     bool Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::IsTaskBaseFlowRelatedPortableBusinessLogic(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflow, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>& taskBasedFlowFormId)
0x8e4bc  stloc.3
0x8e4bd  ldloc.3
0x8e4be  brfalse.s loc_8E53D
0x8e4c0  ldarg.0
0x8e4c1  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::get_ExportToTargetVersionContext()
0x8e4c6  brfalse.s loc_8E53D
0x8e4c8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x8e4cd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x8e4d2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_TaskBasedFlowSolutionAware()
0x8e4d7  ldarg.0
0x8e4d8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::context
0x8e4dd  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8e4e2  brfalse.s loc_8E4EB
0x8e4e4  ldsfld   bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ApplicationXmlDiffCalculatorBase::IsTargetVersionSupportsTaskBasedFlow
0x8e4e9  brtrue.s loc_8E53D
0x8e4eb  ldstr    aWorkflowTaskba_1// "Workflow.TaskBasedFlow.ExportAs.Busines"...
0x8e4f0  ldarg.0
0x8e4f1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::context
0x8e4f6  ldc.i4.1
0x8e4f7  newarr   [mscorlib]System.Object
0x8e4fc  dup
0x8e4fd  ldc.i4.0
0x8e4fe  ldarg.1
0x8e4ff  ldstr    aName// "name"
0x8e504  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e509  stelem.ref
0x8e50a  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x8e50f  stloc.s  7
0x8e511  ldarg.1
0x8e512  ldstr    aWorkflowid_0// "workflowid"
0x8e517  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e51c  unbox.any [mscorlib]System.Guid
0x8e521  ldc.i4.s 0x1D
0x8e523  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0)
0x8e528  stloc.s  8
0x8e52a  ldarg.0
0x8e52b  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::get_ExportToTargetVersionContext()
0x8e530  ldloc.s  8
0x8e532  ldc.i4.1
0x8e533  ldloc.s  7
0x8e535  ldc.i4.0
0x8e536  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::AddFilteredComponentAndComment(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32> dependentComponent, valuetype Microsoft.Crm.Tools.ImportExportPublish.FilteredComponentAction action, string comment, bool addToExistingComments)
0x8e53b  ldc.i4.0
0x8e53c  ret
0x8e53d  ldarg.1
0x8e53e  ldstr    aSolutionid// "solutionid"
0x8e543  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e548  unbox.any [mscorlib]System.Guid
0x8e54d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x8e552  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8e557  brfalse.s loc_8E55D
0x8e559  ldc.i4.1
0x8e55a  stloc.1
0x8e55b  br.s     loc_8E5CC
0x8e55d  ldarg.1
0x8e55e  ldstr    aWorkflowid_0// "workflowid"
0x8e563  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e568  unbox.any [mscorlib]System.Guid
0x8e56d  ldarg.0
0x8e56e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::context
0x8e573  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::GetTriggersForBusinessRule(valuetype [mscorlib]System.Guid workflowId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8e578  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x8e57d  stloc.s  9
0x8e57f  br.s     loc_8E5AC
0x8e581  ldloc.s  9
0x8e583  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8e588  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ProcessTrigger
0x8e58d  ldstr    aSolutionid// "solutionid"
0x8e592  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e597  unbox.any [mscorlib]System.Guid
0x8e59c  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x8e5a1  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8e5a6  brfalse.s loc_8E5AC
0x8e5a8  ldc.i4.1
0x8e5a9  stloc.1
0x8e5aa  leave.s  loc_8E5CC
0x8e5ac  ldloc.s  9
0x8e5ae  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e5b3  brtrue.s loc_8E581
0x8e5b5  leave.s  loc_8E5CC
0x8e5b7  ldloc.s  9
0x8e5b9  isinst   [mscorlib]System.IDisposable
0x8e5be  stloc.s  0xA
0x8e5c0  ldloc.s  0xA
0x8e5c2  brfalse.s loc_8E5CB
0x8e5c4  ldloc.s  0xA
0x8e5c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e5cb  endfinally
0x8e5cc  ldloc.1
0x8e5cd  brtrue.s loc_8E5DA
0x8e5cf  ldarg.2
0x8e5d0  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::IsSolutionUnmanaged(class [System.Xml]System.Xml.XmlDocument importDocument)
0x8e5d5  brfalse  loc_8E690
0x8e5da  ldarg.0
0x8e5db  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::context
0x8e5e0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8e5e5  ldarg.1
0x8e5e6  ldstr    aPrimaryentity_0// "primaryentity"
0x8e5eb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e5f0  unbox.any [mscorlib]System.Int32
0x8e5f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x8e5fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x8e5ff  stloc.s  0xB
0x8e601  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x8e606  stloc.s  0xC
0x8e608  ldnull
0x8e609  stloc.s  0xD
0x8e60b  ldloc.1
0x8e60c  brfalse.s loc_8E620
0x8e60e  ldarg.0
0x8e60f  ldloc.s  0xB
0x8e611  ldarg.0
0x8e612  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::context
0x8e617  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::IsIncludeSelfAndAllSubcomponentsInComponentTable(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x8e61c  brfalse.s loc_8E620
0x8e61e  ldc.i4.1
0x8e61f  ret
0x8e620  ldloc.3
0x8e621  brfalse.s loc_8E657
0x8e623  ldarg.0
0x8e624  ldloc.2
0x8e625  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::GetTaskBaseFlowByFormId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> formID)
0x8e62a  stloc.s  0xE
0x8e62c  ldloc.s  0xC
0x8e62e  ldloc.s  0xE
0x8e630  ldc.i4.s 0x1D
0x8e632  ldarg.0
0x8e633  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::get_SolutionId()
0x8e638  ldc.i4.1
0x8e639  newarr   [mscorlib]System.String
0x8e63e  dup
0x8e63f  ldc.i4.0
0x8e640  ldstr    aSolutioncompon_12// "solutioncomponentid"
0x8e645  stelem.ref
0x8e646  ldloca.s 0xD
0x8e648  ldarg.0
0x8e649  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::context
0x8e64e  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::TryRetrieveSolutionComponent(valuetype [mscorlib]System.Guid, int32, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity&, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8e653  brfalse.s loc_8E690
0x8e655  ldc.i4.1
0x8e656  ret
0x8e657  ldloc.s  0xC
0x8e659  ldarg.1
0x8e65a  ldstr    aWorkflowid_0// "workflowid"
0x8e65f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e664  unbox.any [mscorlib]System.Guid
0x8e669  ldc.i4.s 0x1D
0x8e66b  ldarg.0
0x8e66c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::get_SolutionId()
0x8e671  ldc.i4.1
0x8e672  newarr   [mscorlib]System.String
0x8e677  dup
0x8e678  ldc.i4.0
0x8e679  ldstr    aSolutioncompon_12// "solutioncomponentid"
0x8e67e  stelem.ref
0x8e67f  ldloca.s 0xD
0x8e681  ldarg.0
0x8e682  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::context
0x8e687  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::TryRetrieveSolutionComponent(valuetype [mscorlib]System.Guid, int32, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity&, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8e68c  brfalse.s loc_8E690
0x8e68e  ldc.i4.1
0x8e68f  ret
0x8e690  ldc.i4.0
0x8e691  ret
```
