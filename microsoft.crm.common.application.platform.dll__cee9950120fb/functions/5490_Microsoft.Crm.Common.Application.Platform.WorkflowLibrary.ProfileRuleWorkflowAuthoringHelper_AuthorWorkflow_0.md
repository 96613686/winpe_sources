# Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AuthorWorkflow_0

- ea: `0x5490`
- end: `0x57e5`
- name: `Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AuthorWorkflow_0`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x51d0`

## callees

- `0x51f0`
- `0x52f0`
- `0x53d0`
- `0x5490`

## string_xrefs

- `0x558f`: `channelaccessprofilerule`
- `0x561b`: `channelaccessprofilerule`
- `0x55e8`: `associatedchannelaccessprofile`
- `0x5718`: `associatedchannelaccessprofile`
- `0x5726`: `associatedchannelaccessprofile`
- `0x5594`: `channelaccessprofileruleid`
- `0x5599`: `channelaccessprofileruleid`
- `0x55aa`: `channelaccessprofileruleid`
- `0x55d8`: `conditionxml`
- `0x56ad`: `conditionxml`
- `0x56bb`: `conditionxml`
- `0x56f1`: `conditionxml`

## pseudocode

```c

```

## disassembly

```asm
0x5490  ldc.i4.3
0x5491  newarr   [mscorlib]System.String
0x5496  dup
0x5497  ldc.i4.0
0x5498  ldstr    aName// "name"
0x549d  stelem.ref
0x549e  dup
0x549f  ldc.i4.1
0x54a0  ldstr    aWorkflowid// "workflowid"
0x54a5  stelem.ref
0x54a6  dup
0x54a7  ldc.i4.2
0x54a8  ldstr    aOwnerid// "ownerid"
0x54ad  stelem.ref
0x54ae  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x54b3  stloc.0
0x54b4  ldarg.0
0x54b5  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x54ba  ldarg.3
0x54bb  ldarg.1
0x54bc  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x54c1  ldloc.0
0x54c2  ldc.i4.0
0x54c3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x54c8  stloc.1
0x54c9  ldloc.1
0x54ca  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x54cf  ldstr    aWorkflowid// "workflowid"
0x54d4  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x54d9  brfalse.s loc_5540
0x54db  ldloc.1
0x54dc  ldstr    aWorkflowid// "workflowid"
0x54e1  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x54e6  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x54eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x54f0  stloc.s  6
0x54f2  ldloc.1
0x54f3  ldstr    aWorkflowid// "workflowid"
0x54f8  ldnull
0x54f9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x54fe  ldarg.0
0x54ff  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x5504  ldloc.1
0x5505  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x550a  ldloc.s  6
0x550c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5511  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5516  brfalse.s loc_5540
0x5518  ldarg.0
0x5519  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x551e  ldstr    aWorkflow// "workflow"
0x5523  ldloc.s  6
0x5525  ldloc.0
0x5526  ldc.i4.0
0x5527  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x552c  brfalse.s loc_5540
0x552e  ldarg.0
0x552f  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x5534  ldstr    aWorkflow// "workflow"
0x5539  ldloc.s  6
0x553b  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Delete(string, valuetype [mscorlib]System.Guid)
0x5540  ldarg.0
0x5541  ldloc.1
0x5542  ldstr    aName// "name"
0x5547  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x554c  callvirt instance string [mscorlib]System.Object::ToString()
0x5551  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowName(string)
0x5556  ldarg.0
0x5557  ldarg.2
0x5558  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_PrimaryEntityName(string)
0x555d  ldarg.0
0x555e  ldc.i4.0
0x555f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_IsSyncWorkflow(bool)
0x5564  ldarg.0
0x5565  ldc.i4.0
0x5566  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowCategory(int32)
0x556b  ldarg.0
0x556c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_WorkflowAdapter()
0x5571  ldloc.1
0x5572  ldstr    aOwnerid// "ownerid"
0x5577  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x557c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x5581  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::set_OverriddenOwnerId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x5586  ldarg.s  4
0x5588  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x558d  stloc.2
0x558e  ldloc.2
0x558f  ldstr    aChannelaccessp// "channelaccessprofilerule"
0x5594  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x5599  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x559e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddLink(string, string, string)
0x55a3  pop
0x55a4  ldloc.2
0x55a5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x55aa  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x55af  ldc.i4.0
0x55b0  ldarg.1
0x55b1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x55b6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0x55bb  ldloc.2
0x55bc  ldstr    aSequencenumber// "sequencenumber"
0x55c1  ldc.i4.0
0x55c2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x55c7  ldloc.2
0x55c8  ldc.i4.4
0x55c9  newarr   [mscorlib]System.String
0x55ce  dup
0x55cf  ldc.i4.0
0x55d0  ldstr    aSequencenumber// "sequencenumber"
0x55d5  stelem.ref
0x55d6  dup
0x55d7  ldc.i4.1
0x55d8  ldstr    aConditionxml// "conditionxml"
0x55dd  stelem.ref
0x55de  dup
0x55df  ldc.i4.2
0x55e0  ldstr    aName// "name"
0x55e5  stelem.ref
0x55e6  dup
0x55e7  ldc.i4.3
0x55e8  ldstr    aAssociatedchan// "associatedchannelaccessprofile"
0x55ed  stelem.ref
0x55ee  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x55f3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x55f8  ldarg.0
0x55f9  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x55fe  ldloc.2
0x55ff  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression)
0x5604  stloc.3
0x5605  ldarg.0
0x5606  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::CreateWorkflow()
0x560b  stloc.s  4
0x560d  ldarg.0
0x560e  ldc.i4.4
0x560f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowTriggerType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x5614  ldloc.s  4
0x5616  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x561b  ldstr    aChannelaccessp// "channelaccessprofilerule"
0x5620  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_WorkflowRendererObjectTypeCode(string)
0x5625  ldloc.3
0x5626  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x562b  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x5630  brtrue.s loc_5682
0x5632  ldarg.0
0x5633  ldloc.s  4
0x5635  ldarg.s  5
0x5637  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0x563c  pop
0x563d  ldloc.1
0x563e  ldstr    aWorkflowid// "workflowid"
0x5643  ldstr    aWorkflow// "workflow"
0x5648  ldloc.s  4
0x564a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x564f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x5654  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x5659  ldarg.0
0x565a  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x565f  ldloc.1
0x5660  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x5665  ldloc.s  4
0x5667  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x566c  stloc.s  7
0x566e  ldloca.s 7
0x5670  constrained. [mscorlib]System.Guid
0x5676  callvirt instance string [mscorlib]System.Object::ToString()
0x567b  stloc.s  8
0x567d  leave    loc_57E2
0x5682  ldc.i4.0
0x5683  stloc.s  5
0x5685  ldloc.3
0x5686  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x568b  call     T0x2B000002
0x5690  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x5695  stloc.s  9
0x5697  br       loc_5748
0x569c  ldloc.s  9
0x569e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x56a3  stloc.s  0xA
0x56a5  ldc.i4.0
0x56a6  stloc.s  0xB
0x56a8  ldnull
0x56a9  stloc.s  0xC
0x56ab  ldloc.s  0xA
0x56ad  ldstr    aConditionxml// "conditionxml"
0x56b2  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x56b7  brfalse.s loc_5712
0x56b9  ldloc.s  0xA
0x56bb  ldstr    aConditionxml// "conditionxml"
0x56c0  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x56c5  callvirt instance string [mscorlib]System.Object::ToString()
0x56ca  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x56cf  brtrue.s loc_5712
0x56d1  ldarg.0
0x56d2  ldloc.s  0xA
0x56d4  ldstr    aSequencenumber// "sequencenumber"
0x56d9  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x56de  callvirt instance string [mscorlib]System.Object::ToString()
0x56e3  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x56e8  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x56ed  ldloc.s  4
0x56ef  ldloc.s  0xA
0x56f1  ldstr    aConditionxml// "conditionxml"
0x56f6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x56fb  callvirt instance string [mscorlib]System.Object::ToString()
0x5700  ldstr    asc_882E// ""
0x5705  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddConditionWorkflowStep(int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x570a  stloc.s  0xC
0x570c  ldc.i4.1
0x570d  stloc.s  0xB
0x570f  ldc.i4.1
0x5710  stloc.s  5
0x5712  ldloc.s  0xB
0x5714  brfalse.s loc_5748
0x5716  ldloc.s  0xA
0x5718  ldstr    aAssociatedchan// "associatedchannelaccessprofile"
0x571d  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x5722  brfalse.s loc_5748
0x5724  ldloc.s  0xA
0x5726  ldstr    aAssociatedchan// "associatedchannelaccessprofile"
0x572b  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x5730  callvirt instance string [mscorlib]System.Object::ToString()
0x5735  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x573a  brtrue.s loc_5748
0x573c  ldarg.0
0x573d  ldloc.s  4
0x573f  ldloc.s  0xC
0x5741  ldloc.s  0xA
0x5743  call     instance void Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AddUpdatePrimaryEntityChannelAccessProfileStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase conditionWorkflowStep, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity ruleChildEntity)
0x5748  ldloc.s  9
0x574a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x574f  brtrue   loc_569C
0x5754  leave.s  loc_5762
0x5756  ldloc.s  9
0x5758  brfalse.s loc_5761
0x575a  ldloc.s  9
0x575c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5761  endfinally
0x5762  ldloc.s  5
0x5764  brfalse.s loc_5783
0x5766  ldarg.0
0x5767  ldloc.s  4
0x5769  ldstr    asc_882E// ""
0x576e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AddElseStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5773  stloc.s  0xD
0x5775  ldloc.s  0xD
0x5777  brfalse.s loc_5783
0x5779  ldarg.0
0x577a  ldloc.s  4
0x577c  ldloc.s  0xD
0x577e  call     instance void Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AddUpdateWithDefaultChannelAccessProfileStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase elseStep)
0x5783  ldarg.0
0x5784  ldloc.s  4
0x5786  ldarg.s  5
0x5788  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0x578d  pop
0x578e  ldloc.1
0x578f  ldstr    aWorkflowid// "workflowid"
0x5794  ldstr    aWorkflow// "workflow"
0x5799  ldloc.s  4
0x579b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x57a0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x57a5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x57aa  ldarg.0
0x57ab  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x57b0  ldloc.1
0x57b1  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x57b6  ldloc.s  4
0x57b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x57bd  stloc.s  7
0x57bf  ldloca.s 7
0x57c1  constrained. [mscorlib]System.Guid
0x57c7  callvirt instance string [mscorlib]System.Object::ToString()
0x57cc  stloc.s  8
0x57ce  leave.s  loc_57E2
0x57d0  pop
0x57d1  ldc.i4   0x80061101
0x57d6  ldc.i4.0
0x57d7  newarr   [mscorlib]System.Object
0x57dc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x57e1  throw
0x57e2  ldloc.s  8
0x57e4  ret
```
