# Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddStepIfKPICreatedPausable

- ea: `0x178e0`
- end: `0x17a74`
- name: `Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddStepIfKPICreatedPausable`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x16ea0`

## callees

- `0x17130`
- `0x17380`
- `0x17580`
- `0x17670`
- `0x177e0`
- `0x17ab0`

## pseudocode

```c

```

## disassembly

```asm
0x178e0  ldarg.0
0x178e1  ldarg.2
0x178e2  ldarg.1
0x178e3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x178e8  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddIsApplicableEntityOnHoldCondition(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string stepId)
0x178ed  pop
0x178ee  ldarg.1
0x178ef  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x178f4  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x178f9  stloc.0
0x178fa  ldarg.0
0x178fb  ldarg.2
0x178fc  ldarg.s  5
0x178fe  ldloc.0
0x178ff  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x17904  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x17909  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::CheckApplicableEntityStatusAndInvokeChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string relatedKPI, string stepId)
0x1790e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x17913  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x17918  stloc.1
0x17919  ldarg.2
0x1791a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1791f  stloc.2
0x17920  ldloc.1
0x17921  ldloc.2
0x17922  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x17927  ldarg.0
0x17928  ldarg.2
0x17929  ldloc.2
0x1792a  ldarg.s  5
0x1792c  ldarg.s  6
0x1792e  ldnull
0x1792f  ldnull
0x17930  ldc.i4.3
0x17931  ldc.i4.1
0x17932  ldc.i4.0
0x17933  call     instance void Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::UpdateSLAKPI(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep updateStep, string relatedKPI, string stepDescription, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionWarnAfter, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionFailAfter, int32 Status, [opt] bool updateWarningTime, [opt] bool resetHasNearedVioaltion)
0x17938  ldarg.0
0x17939  ldloc.1
0x1793a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x1793f  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x17944  ldarg.2
0x17945  ldstr    asc_1EEAE// ""
0x1794a  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x1794f  ldarg.2
0x17950  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x17955  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x1795a  pop
0x1795b  ldarg.2
0x1795c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x17961  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x17966  ldarg.2
0x17967  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1796c  stloc.3
0x1796d  ldloc.3
0x1796e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x17973  ldarg.0
0x17974  ldarg.2
0x17975  ldloc.3
0x17976  ldarg.s  5
0x17978  ldarg.s  6
0x1797a  ldnull
0x1797b  ldnull
0x1797c  ldc.i4.m1
0x1797d  ldc.i4.1
0x1797e  ldc.i4.0
0x1797f  call     instance void Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::UpdateSLAKPI(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep updateStep, string relatedKPI, string stepDescription, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionWarnAfter, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionFailAfter, int32 Status, [opt] bool updateWarningTime, [opt] bool resetHasNearedVioaltion)
0x17984  ldarg.0
0x17985  ldloc.0
0x17986  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x1798b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x17990  ldarg.2
0x17991  ldstr    asc_1EEAE// ""
0x17996  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x1799b  ldarg.2
0x1799c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x179a1  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x179a6  stloc.s  4
0x179a8  ldarg.0
0x179a9  ldarg.2
0x179aa  ldarg.s  5
0x179ac  ldloc.s  4
0x179ae  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x179b3  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::CheckKPIStatusPausedNowGtWarning(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string relatedKPI, string stepId)
0x179b8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x179bd  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x179c2  stloc.s  5
0x179c4  ldarg.2
0x179c5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x179ca  stloc.s  6
0x179cc  ldloc.s  5
0x179ce  ldloc.s  6
0x179d0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x179d5  ldarg.0
0x179d6  ldarg.2
0x179d7  ldloc.s  6
0x179d9  ldarg.s  5
0x179db  ldarg.s  6
0x179dd  ldarg.s  4
0x179df  ldarg.3
0x179e0  ldc.i4.2
0x179e1  ldc.i4.0
0x179e2  ldc.i4.0
0x179e3  call     instance void Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::UpdateSLAKPI(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep updateStep, string relatedKPI, string stepDescription, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionWarnAfter, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionFailAfter, int32 Status, [opt] bool updateWarningTime, [opt] bool resetHasNearedVioaltion)
0x179e8  ldarg.0
0x179e9  ldloc.s  5
0x179eb  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x179f0  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x179f5  ldarg.2
0x179f6  ldstr    asc_1EEAE// ""
0x179fb  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x17a00  ldarg.2
0x17a01  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x17a06  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x17a0b  stloc.s  7
0x17a0d  ldarg.0
0x17a0e  ldarg.2
0x17a0f  ldarg.s  5
0x17a11  ldloc.s  7
0x17a13  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x17a18  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::CheckKPIStatusPaused(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string relatedKPI, string stepId)
0x17a1d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x17a22  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x17a27  stloc.s  8
0x17a29  ldarg.2
0x17a2a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x17a2f  stloc.s  9
0x17a31  ldloc.s  8
0x17a33  ldloc.s  9
0x17a35  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x17a3a  ldarg.0
0x17a3b  ldarg.2
0x17a3c  ldloc.s  9
0x17a3e  ldarg.s  5
0x17a40  ldarg.s  6
0x17a42  ldarg.s  4
0x17a44  ldarg.3
0x17a45  ldc.i4.0
0x17a46  ldc.i4.1
0x17a47  ldc.i4.0
0x17a48  call     instance void Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::UpdateSLAKPI(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep updateStep, string relatedKPI, string stepDescription, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionWarnAfter, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionFailAfter, int32 Status, [opt] bool updateWarningTime, [opt] bool resetHasNearedVioaltion)
0x17a4d  ldarg.0
0x17a4e  ldloc.s  8
0x17a50  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x17a55  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x17a5a  ldarg.2
0x17a5b  ldstr    asc_1EEAE// ""
0x17a60  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x17a65  ldarg.0
0x17a66  ldarg.2
0x17a67  ldarg.s  5
0x17a69  ldarg.s  6
0x17a6b  ldarg.s  4
0x17a6d  ldarg.3
0x17a6e  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddLastStepCheckInvokeChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string relatedKPI, string stepDescription, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionWarnAfter, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase methodCallExpressionFailAfter)
0x17a73  ret
```
