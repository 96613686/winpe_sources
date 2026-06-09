# Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AddElseStep

- ea: `0x53d0`
- end: `0x541b`
- name: `Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::AddElseStep`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5490`

## callees

- `0x53d0`

## pseudocode

```c

```

## disassembly

```asm
0x53d0  ldarg.1
0x53d1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x53d6  brtrue.s loc_53DA
0x53d8  ldnull
0x53d9  ret
0x53da  ldarg.1
0x53db  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x53e0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x53e5  brtrue.s loc_53E9
0x53e7  ldnull
0x53e8  ret
0x53e9  ldarg.1
0x53ea  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x53ef  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x53f4  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep
0x53f9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x53fe  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep
0x5403  ldarg.0
0x5404  ldarg.1
0x5405  ldarg.2
0x5406  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x540b  dup
0x540c  ldnull
0x540d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x5412  stloc.0
0x5413  ldloc.0
0x5414  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x5419  ldloc.0
0x541a  ret
```
