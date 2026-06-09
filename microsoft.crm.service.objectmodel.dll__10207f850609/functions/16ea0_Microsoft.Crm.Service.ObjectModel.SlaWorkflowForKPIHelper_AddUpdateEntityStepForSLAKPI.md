# Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddUpdateEntityStepForSLAKPI

- ea: `0x16ea0`
- end: `0x16fa4`
- name: `Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddUpdateEntityStepForSLAKPI`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x16ea0`
- `0x17400`
- `0x17410`
- `0x17860`
- `0x178e0`
- `0x17a80`
- `0x17aa0`

## pseudocode

```c

```

## disassembly

```asm
0x16ea0  ldarg.0
0x16ea1  ldarg.s  4
0x16ea3  ldarg.2
0x16ea4  ldarg.s  6
0x16ea6  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::SetRelatedKPIForSLAKPI(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string applicableFrom, int32 failureAfter)
0x16eab  stloc.0
0x16eac  ldarg.0
0x16ead  ldarg.s  4
0x16eaf  ldarg.2
0x16eb0  ldarg.s  7
0x16eb2  ldarg.s  6
0x16eb4  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::SetRelatedKPIForSLAKPI(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string applicableFrom, int32 actionAfter, int32 failureAfter)
0x16eb9  stloc.1
0x16eba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16ebf  ldstr    aAndConditionCo_1// "<and><condition><column id=\"colEntity"...
0x16ec4  ldarg.3
0x16ec5  ldstr    aColumnIdColope// "\"/><column id=\"colOperator\" value=\""...
0x16eca  call     string [mscorlib]System.String::Concat(string, string, string)
0x16ecf  ldc.i4.1
0x16ed0  newarr   [mscorlib]System.Object
0x16ed5  dup
0x16ed6  ldc.i4.0
0x16ed7  ldarg.0
0x16ed8  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_PrimaryEntityName()
0x16edd  stelem.ref
0x16ede  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16ee3  stloc.2
0x16ee4  ldarg.0
0x16ee5  ldarg.1
0x16ee6  ldarg.s  4
0x16ee8  ldloc.2
0x16ee9  ldstr    asc_1EEAE// ""
0x16eee  ldstr    asc_1EEAE// ""
0x16ef3  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddCheckStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x16ef8  stloc.3
0x16ef9  ldloc.3
0x16efa  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x16eff  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x16f04  stloc.s  4
0x16f06  ldarg.s  6
0x16f08  brtrue.s loc_16F4A
0x16f0a  ldarg.0
0x16f0b  ldloc.s  4
0x16f0d  ldarg.s  4
0x16f0f  ldloc.0
0x16f10  ldloc.1
0x16f11  ldarg.3
0x16f12  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddStepIfKPItobeCreatedNoPause(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase IfKPICreatedConditionStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionFailAfter, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionWarnAfter, string relatedKPI)
0x16f17  stloc.0
0x16f18  ldarg.0
0x16f19  ldloc.3
0x16f1a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x16f1f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x16f24  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x16f29  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x16f2e  ldarg.s  4
0x16f30  ldstr    asc_1EEAE// ""
0x16f35  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x16f3a  ldarg.0
0x16f3b  ldarg.s  4
0x16f3d  ldloc.0
0x16f3e  ldloc.1
0x16f3f  ldarg.3
0x16f40  ldarg.s  5
0x16f42  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddStepIfKPICreatedNoPause(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionFailAfter, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionWarnAfter, string relatedKPI, string stepDescription)
0x16f47  stloc.0
0x16f48  br.s     loc_16FA2
0x16f4a  ldarg.0
0x16f4b  ldloc.s  4
0x16f4d  ldarg.s  4
0x16f4f  ldloc.0
0x16f50  ldloc.1
0x16f51  ldarg.3
0x16f52  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddStepIfKPItobeCreatedPausable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase IfKPICreatedConditionStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionFailAfter, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionWarnAfter, string relatedKPI)
0x16f57  stloc.0
0x16f58  ldarg.0
0x16f59  ldloc.3
0x16f5a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x16f5f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x16f64  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x16f69  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x16f6e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x16f73  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x16f78  ldarg.s  4
0x16f7a  ldstr    asc_1EEAE// ""
0x16f7f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x16f84  ldarg.s  4
0x16f86  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x16f8b  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x16f90  stloc.s  5
0x16f92  ldarg.0
0x16f93  ldloc.s  5
0x16f95  ldarg.s  4
0x16f97  ldloc.0
0x16f98  ldloc.1
0x16f99  ldarg.3
0x16f9a  ldarg.s  5
0x16f9c  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddStepIfKPICreatedPausable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase KPIExistsStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionFailAfter, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionWarnAfter, string relatedKPI, string stepDescription)
0x16fa1  stloc.0
0x16fa2  ldloc.0
0x16fa3  ret
```
