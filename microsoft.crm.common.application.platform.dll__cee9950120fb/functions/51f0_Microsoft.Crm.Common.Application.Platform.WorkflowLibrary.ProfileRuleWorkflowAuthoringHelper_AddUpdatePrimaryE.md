# Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AddUpdatePrimaryEntityChannelAccessProfileStep

- ea: `0x51f0`
- end: `0x52ea`
- name: `Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AddUpdatePrimaryEntityChannelAccessProfileStep`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5490`

## callees

- `0x51f0`

## string_xrefs

- `0x51fd`: `associatedchannelaccessprofile`
- `0x526f`: `Update ChannelAccessProfile`
- `0x529f`: `channelaccessprofileid`

## pseudocode

```c

```

## disassembly

```asm
0x51f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x51f5  stloc.0
0x51f6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x51fb  stloc.1
0x51fc  ldarg.3
0x51fd  ldstr    aAssociatedchan// "associatedchannelaccessprofile"
0x5202  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x5207  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x520c  dup
0x520d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x5212  stloc.2
0x5213  ldloca.s 2
0x5215  constrained. [mscorlib]System.Guid
0x521b  callvirt instance string [mscorlib]System.Object::ToString()
0x5220  stloc.3
0x5221  dup
0x5222  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x5227  stloc.s  4
0x5229  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x522e  stloc.s  5
0x5230  ldarg.1
0x5231  ldarg.1
0x5232  ldloc.3
0x5233  ldc.i4.s 0xF
0x5235  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x523a  ldc.i4.6
0x523b  ldloc.s  4
0x523d  ldloc.s  5
0x523f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x5244  stloc.s  6
0x5246  ldloc.0
0x5247  ldloc.s  6
0x5249  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>)
0x524e  ldarg.1
0x524f  ldc.i4.0
0x5250  ldloc.0
0x5251  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::ToArray()
0x5256  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x525b  stloc.s  7
0x525d  ldloc.1
0x525e  ldloc.s  7
0x5260  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>)
0x5265  ldarg.1
0x5266  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x526b  stloc.s  8
0x526d  ldloc.s  8
0x526f  ldstr    aUpdateChannela// "Update ChannelAccessProfile"
0x5274  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x5279  ldloc.s  8
0x527b  ldarg.1
0x527c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x5281  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x5286  ldloc.s  8
0x5288  ldarg.1
0x5289  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x528e  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x5293  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_EntitySpec(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x5298  ldloc.s  8
0x529a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x529f  ldstr    aChannelaccessp_1// "channelaccessprofileid"
0x52a4  ldloc.1
0x52a5  ldc.i4.0
0x52a6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Item(!!T0)
0x52ab  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x52b0  ldnull
0x52b1  stloc.s  9
0x52b3  ldarg.2
0x52b4  brfalse.s loc_52C5
0x52b6  ldarg.2
0x52b7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x52bc  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x52c1  stloc.s  9
0x52c3  br.s     loc_52D7
0x52c5  ldarg.1
0x52c6  ldstr    asc_882E// ""
0x52cb  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x52d0  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x52d5  stloc.s  9
0x52d7  ldloc.s  9
0x52d9  ldloc.s  8
0x52db  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x52e0  ldarg.0
0x52e1  ldarg.1
0x52e2  ldloc.s  9
0x52e4  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::StopWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase)
0x52e9  ret
```
