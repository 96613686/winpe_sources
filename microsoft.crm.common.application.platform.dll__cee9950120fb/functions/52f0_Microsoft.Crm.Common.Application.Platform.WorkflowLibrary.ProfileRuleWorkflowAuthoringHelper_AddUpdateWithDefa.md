# Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AddUpdateWithDefaultChannelAccessProfileStep

- ea: `0x52f0`
- end: `0x53c2`
- name: `Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AddUpdateWithDefaultChannelAccessProfileStep`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5490`

## callees

- `0x52f0`
- `0x5420`

## string_xrefs

- `0x5370`: `Update ChannelAccessProfile`
- `0x5308`: `channelaccessprofileid`
- `0x53a0`: `channelaccessprofileid`
- `0x5318`: `channelaccessprofile`

## pseudocode

```c

```

## disassembly

```asm
0x52f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x52f5  stloc.0
0x52f6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x52fb  stloc.1
0x52fc  ldarg.0
0x52fd  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::GetDefaultChannelAccessProfile()
0x5302  stloc.2
0x5303  ldloc.2
0x5304  brtrue.s loc_5307
0x5306  ret
0x5307  ldloc.2
0x5308  ldstr    aChannelaccessp_1// "channelaccessprofileid"
0x530d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x5312  callvirt instance string [mscorlib]System.Object::ToString()
0x5317  stloc.3
0x5318  ldstr    aChannelaccessp_2// "channelaccessprofile"
0x531d  stloc.s  4
0x531f  ldloc.2
0x5320  ldstr    aName// "name"
0x5325  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x532a  callvirt instance string [mscorlib]System.Object::ToString()
0x532f  stloc.s  5
0x5331  ldarg.1
0x5332  ldarg.1
0x5333  ldloc.3
0x5334  ldc.i4.s 0xF
0x5336  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x533b  ldc.i4.6
0x533c  ldloc.s  4
0x533e  ldloc.s  5
0x5340  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x5345  stloc.s  6
0x5347  ldloc.0
0x5348  ldloc.s  6
0x534a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>)
0x534f  ldarg.1
0x5350  ldc.i4.0
0x5351  ldloc.0
0x5352  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::ToArray()
0x5357  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x535c  stloc.s  7
0x535e  ldloc.1
0x535f  ldloc.s  7
0x5361  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>)
0x5366  ldarg.1
0x5367  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x536c  stloc.s  8
0x536e  ldloc.s  8
0x5370  ldstr    aUpdateChannela// "Update ChannelAccessProfile"
0x5375  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x537a  ldloc.s  8
0x537c  ldarg.1
0x537d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x5382  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x5387  ldloc.s  8
0x5389  ldarg.1
0x538a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x538f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x5394  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_EntitySpec(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x5399  ldloc.s  8
0x539b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_EntitySpec()
0x53a0  ldstr    aChannelaccessp_1// "channelaccessprofileid"
0x53a5  ldloc.1
0x53a6  ldc.i4.0
0x53a7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Item(!!T0)
0x53ac  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x53b1  ldarg.2
0x53b2  ldloc.s  8
0x53b4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x53b9  ldarg.0
0x53ba  ldarg.1
0x53bb  ldarg.2
0x53bc  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::StopWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase)
0x53c1  ret
```
