# Microsoft.Crm.Service.ObjectModel.RoutingWorkflowAuthoringHelper::AuthorWorkflow_1

- ea: `0x1a120`
- end: `0x1a619`
- name: `Microsoft.Crm.Service.ObjectModel.RoutingWorkflowAuthoringHelper::AuthorWorkflow_1`
- size: `1273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1a100`

## callees

- `0x7df0`
- `0x1a120`
- `0x1a620`

## string_xrefs

- `0x1a436`: `conditionxml`
- `0x1a444`: `conditionxml`
- `0x1a47a`: `conditionxml`

## pseudocode

```c

```

## disassembly

```asm
0x1a120  ldc.i4.3
0x1a121  newarr   [mscorlib]System.String
0x1a126  dup
0x1a127  ldc.i4.0
0x1a128  ldstr    aName// "name"
0x1a12d  stelem.ref
0x1a12e  dup
0x1a12f  ldc.i4.1
0x1a130  ldstr    aOwnerid// "ownerid"
0x1a135  stelem.ref
0x1a136  dup
0x1a137  ldc.i4.2
0x1a138  ldstr    aWorkflowid// "workflowid"
0x1a13d  stelem.ref
0x1a13e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1a143  stloc.0
0x1a144  ldarg.0
0x1a145  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x1a14a  ldarg.3
0x1a14b  ldarg.1
0x1a14c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a151  ldloc.0
0x1a152  ldc.i4.0
0x1a153  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x1a158  stloc.1
0x1a159  newobj   instance void Microsoft.Crm.Service.ObjectModel.RoutingRuleService::.ctor()
0x1a15e  stloc.2
0x1a15f  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::.ctor()
0x1a164  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityToBusinessEntityConverter::.ctor()
0x1a169  stloc.3
0x1a16a  ldarg.s  6
0x1a16c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::CreateInstance(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a171  stloc.s  4
0x1a173  ldloc.1
0x1a174  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1a179  ldstr    aWorkflowid// "workflowid"
0x1a17e  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1a183  brfalse.s loc_1A1F3
0x1a185  ldloc.1
0x1a186  ldstr    aWorkflowid// "workflowid"
0x1a18b  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1a190  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1a195  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1a19a  stloc.s  0xC
0x1a19c  ldloc.1
0x1a19d  ldstr    aWorkflowid// "workflowid"
0x1a1a2  ldnull
0x1a1a3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1a1a8  ldloc.3
0x1a1a9  ldloc.s  4
0x1a1ab  ldloc.1
0x1a1ac  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityToBusinessEntityConverter::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x1a1b1  stloc.s  5
0x1a1b3  ldloc.2
0x1a1b4  ldloc.s  5
0x1a1b6  ldarg.s  6
0x1a1b8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a1bd  ldloc.s  0xC
0x1a1bf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a1c4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a1c9  brfalse.s loc_1A1F3
0x1a1cb  ldarg.0
0x1a1cc  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x1a1d1  ldstr    aWorkflow_0// "workflow"
0x1a1d6  ldloc.s  0xC
0x1a1d8  ldloc.0
0x1a1d9  ldc.i4.0
0x1a1da  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x1a1df  brfalse.s loc_1A1F3
0x1a1e1  ldarg.0
0x1a1e2  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x1a1e7  ldstr    aWorkflow_0// "workflow"
0x1a1ec  ldloc.s  0xC
0x1a1ee  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Delete(string, valuetype [mscorlib]System.Guid)
0x1a1f3  ldarg.0
0x1a1f4  ldloc.1
0x1a1f5  ldstr    aName// "name"
0x1a1fa  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1a1ff  callvirt instance string [mscorlib]System.Object::ToString()
0x1a204  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowName(string)
0x1a209  ldarg.0
0x1a20a  ldarg.2
0x1a20b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_PrimaryEntityName(string)
0x1a210  ldarg.0
0x1a211  ldc.i4.0
0x1a212  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_IsSyncWorkflow(bool)
0x1a217  ldarg.0
0x1a218  ldc.i4.0
0x1a219  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowCategory(int32)
0x1a21e  ldarg.0
0x1a21f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_WorkflowAdapter()
0x1a224  ldloc.1
0x1a225  ldstr    aOwnerid// "ownerid"
0x1a22a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1a22f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1a234  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::set_OverriddenOwnerId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x1a239  ldarg.s  4
0x1a23b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x1a240  stloc.s  6
0x1a242  ldloc.s  6
0x1a244  ldstr    aRoutingrule_0// "routingrule"
0x1a249  ldstr    aRoutingruleid_0// "routingruleid"
0x1a24e  ldstr    aRoutingruleid_0// "routingruleid"
0x1a253  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddLink(string, string, string)
0x1a258  pop
0x1a259  ldloc.s  6
0x1a25b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1a260  ldstr    aRoutingruleid_0// "routingruleid"
0x1a265  ldc.i4.0
0x1a266  ldarg.1
0x1a267  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1a26c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0x1a271  ldloc.s  6
0x1a273  ldstr    aSequencenumber// "sequencenumber"
0x1a278  ldc.i4.0
0x1a279  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x1a27e  ldloc.s  6
0x1a280  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x1a285  ldc.i4.1
0x1a286  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::set_AllColumns(bool)
0x1a28b  ldarg.0
0x1a28c  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x1a291  ldloc.s  6
0x1a293  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression)
0x1a298  stloc.s  7
0x1a29a  ldarg.0
0x1a29b  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::CreateWorkflow()
0x1a2a0  stloc.s  8
0x1a2a2  ldarg.0
0x1a2a3  ldc.i4.4
0x1a2a4  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowTriggerType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x1a2a9  ldloc.s  8
0x1a2ab  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x1a2b0  ldstr    aRoutingrule_0// "routingrule"
0x1a2b5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_WorkflowRendererObjectTypeCode(string)
0x1a2ba  ldloc.s  7
0x1a2bc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1a2c1  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1a2c6  brtrue.s loc_1A321
0x1a2c8  ldarg.0
0x1a2c9  ldloc.s  8
0x1a2cb  ldarg.s  5
0x1a2cd  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0x1a2d2  pop
0x1a2d3  ldloc.1
0x1a2d4  ldstr    aWorkflowid// "workflowid"
0x1a2d9  ldstr    aWorkflow_0// "workflow"
0x1a2de  ldloc.s  8
0x1a2e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x1a2e5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1a2ea  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1a2ef  ldloc.3
0x1a2f0  ldloc.s  4
0x1a2f2  ldloc.1
0x1a2f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityToBusinessEntityConverter::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x1a2f8  stloc.s  5
0x1a2fa  ldloc.2
0x1a2fb  ldloc.s  5
0x1a2fd  ldarg.s  6
0x1a2ff  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a304  ldloc.s  8
0x1a306  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x1a30b  stloc.s  0xD
0x1a30d  ldloca.s 0xD
0x1a30f  constrained. [mscorlib]System.Guid
0x1a315  callvirt instance string [mscorlib]System.Object::ToString()
0x1a31a  stloc.s  0xE
0x1a31c  leave    loc_1A616
0x1a321  ldstr    aIsmanualrun// "IsManualRun"
0x1a326  ldtoken  [mscorlib]System.Int32
0x1a32b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a330  ldc.i4.1
0x1a331  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, class [mscorlib]System.Type, bool)
0x1a336  stloc.s  9
0x1a338  ldloc.s  8
0x1a33a  ldloc.s  9
0x1a33c  ldtoken  [mscorlib]System.Int32
0x1a341  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a346  ldc.i4.0
0x1a347  box      [mscorlib]System.Int32
0x1a34c  ldc.i4.1
0x1a34d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(string, class [mscorlib]System.Type, object, bool)
0x1a352  ldstr    aAndConditionCo_2// "<and><condition><column id=\"colEntity"...
0x1a357  stloc.s  0xA
0x1a359  ldc.i4.s 0xC
0x1a35b  newarr   [mscorlib]System.String
0x1a360  dup
0x1a361  ldc.i4.0
0x1a362  ldloc.s  0xA
0x1a364  stelem.ref
0x1a365  dup
0x1a366  ldc.i4.1
0x1a367  ldstr    aConditionColum// "<condition><column id=\"colEntity\" val"...
0x1a36c  stelem.ref
0x1a36d  dup
0x1a36e  ldc.i4.2
0x1a36f  ldloc.s  8
0x1a371  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x1a376  stloc.s  0xD
0x1a378  ldloca.s 0xD
0x1a37a  constrained. [mscorlib]System.Guid
0x1a380  callvirt instance string [mscorlib]System.Object::ToString()
0x1a385  stelem.ref
0x1a386  dup
0x1a387  ldc.i4.3
0x1a388  ldstr    a12535// "&#125;&#35;"
0x1a38d  stelem.ref
0x1a38e  dup
0x1a38f  ldc.i4.4
0x1a390  ldloc.s  8
0x1a392  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x1a397  stelem.ref
0x1a398  dup
0x1a399  ldc.i4.5
0x1a39a  ldstr    aColumnIdColatt// "\" /><column id=\"colAttribute\" value="...
0x1a39f  stelem.ref
0x1a3a0  dup
0x1a3a1  ldc.i4.6
0x1a3a2  ldloc.s  9
0x1a3a4  stelem.ref
0x1a3a5  dup
0x1a3a6  ldc.i4.7
0x1a3a7  ldstr    a35Uiscript3512// "&#35;UIScript&#35;&#123;"
0x1a3ac  stelem.ref
0x1a3ad  dup
0x1a3ae  ldc.i4.8
0x1a3af  ldloc.s  8
0x1a3b1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x1a3b6  stloc.s  0xD
0x1a3b8  ldloca.s 0xD
0x1a3ba  constrained. [mscorlib]System.Guid
0x1a3c0  callvirt instance string [mscorlib]System.Object::ToString()
0x1a3c5  stelem.ref
0x1a3c6  dup
0x1a3c7  ldc.i4.s 9
0x1a3c9  ldstr    a12535// "&#125;&#35;"
0x1a3ce  stelem.ref
0x1a3cf  dup
0x1a3d0  ldc.i4.s 0xA
0x1a3d2  ldloc.s  8
0x1a3d4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x1a3d9  stelem.ref
0x1a3da  dup
0x1a3db  ldc.i4.s 0xB
0x1a3dd  ldstr    a35Int355Column// "&#35;int&#35;5\"/><column id=\"colOpera"...
0x1a3e2  stelem.ref
0x1a3e3  call     string [mscorlib]System.String::Concat(string[])
0x1a3e8  stloc.s  0xA
0x1a3ea  ldarg.0
0x1a3eb  ldc.i4.0
0x1a3ec  ldloc.s  8
0x1a3ee  ldloc.s  0xA
0x1a3f0  ldstr    asc_1EEAE// ""
0x1a3f5  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddConditionWorkflowStep(int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1a3fa  stloc.s  0xB
0x1a3fc  ldarg.0
0x1a3fd  ldloc.s  8
0x1a3ff  ldloc.s  0xB
0x1a401  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x1a406  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x1a40b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::StopWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase)
0x1a410  ldloc.s  7
0x1a412  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1a417  call     T0x2B00000D
0x1a41c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x1a421  stloc.s  0xF
0x1a423  br       loc_1A5A3
0x1a428  ldloc.s  0xF
0x1a42a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x1a42f  stloc.s  0x10
0x1a431  ldnull
0x1a432  stloc.s  0x11
0x1a434  ldloc.s  0x10
0x1a436  ldstr    aConditionxml// "conditionxml"
0x1a43b  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1a440  brfalse.s loc_1A495
0x1a442  ldloc.s  0x10
0x1a444  ldstr    aConditionxml// "conditionxml"
0x1a449  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1a44e  callvirt instance string [mscorlib]System.Object::ToString()
0x1a453  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a458  brtrue.s loc_1A495
0x1a45a  ldarg.0
0x1a45b  ldloc.s  0x10
0x1a45d  ldstr    aSequencenumber// "sequencenumber"
0x1a462  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1a467  callvirt instance string [mscorlib]System.Object::ToString()
0x1a46c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1a471  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x1a476  ldloc.s  8
0x1a478  ldloc.s  0x10
0x1a47a  ldstr    aConditionxml// "conditionxml"
0x1a47f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1a484  callvirt instance string [mscorlib]System.Object::ToString()
0x1a489  ldstr    asc_1EEAE// ""
0x1a48e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddConditionWorkflowStep(int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1a493  stloc.s  0x11
0x1a495  ldloc.s  0x10
0x1a497  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1a49c  ldstr    aRoutedqueueid// "routedqueueid"
  ... truncated ...
```
