# Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::AddwaitAndTimeoutPeriodSteps

- ea: `0x17de0`
- end: `0x17e35`
- name: `Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::AddwaitAndTimeoutPeriodSteps`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x17bf0`

## callees

- `0x17b40`
- `0x17c90`
- `0x17d30`
- `0x17d80`

## pseudocode

```c

```

## disassembly

```asm
0x17de0  ldnull
0x17de1  stloc.1
0x17de2  ldarg.0
0x17de3  ldarg.1
0x17de4  ldarg.2
0x17de5  ldstr    asc_1EEAE// ""
0x17dea  ldarg.3
0x17deb  ldarg.s  6
0x17ded  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::AddWaitStepHonourUseSlaKpi(string stepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml, string stepDescription, string successStep)
0x17df2  stloc.1
0x17df3  ldloc.1
0x17df4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x17df9  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x17dfe  stloc.0
0x17dff  ldarg.0
0x17e00  ldarg.2
0x17e01  ldloc.1
0x17e02  call     instance void Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::AddSuccessStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase successCriteriaStep)
0x17e07  ldarg.0
0x17e08  ldloc.0
0x17e09  ldarg.2
0x17e0a  ldstr    asc_1EEAE// ""
0x17e0f  ldarg.3
0x17e10  ldarg.0
0x17e11  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::_relatedfield
0x17e16  ldarg.s  5
0x17e18  call     instance void Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::InserttimeOutBranchStep(string siblingId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml, string stepDescription, string relatedfield, string computedDateTime)
0x17e1d  ldloc.1
0x17e1e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x17e23  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x17e28  stloc.0
0x17e29  ldarg.0
0x17e2a  ldloc.0
0x17e2b  ldarg.2
0x17e2c  ldarg.s  4
0x17e2e  ldc.i4.0
0x17e2f  call     instance void Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::AddUpdateEntityStep(string stepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, int32 slaKpiStatus, bool _successUpdate)
0x17e34  ret
```
