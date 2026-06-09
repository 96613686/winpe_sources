# Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::CreateStepsForUseSLAKPI

- ea: `0x17bf0`
- end: `0x17c8f`
- name: `Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::CreateStepsForUseSLAKPI`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x165e0`

## callees

- `0x17d80`
- `0x17de0`

## string_xrefs

- `0x17c5b`: `computedwarningtime`
- `0x17c7e`: `computedfailuretime`

## pseudocode

```c

```

## disassembly

```asm
0x17bf0  ldarg.0
0x17bf1  ldarg.2
0x17bf2  ldarg.1
0x17bf3  ldarg.0
0x17bf4  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::_defaultSuccessCondition
0x17bf9  ldstr    asc_1EEAE// ""
0x17bfe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x17c03  ldstr    aWebSlaWorkflow_3// "Web.SLA.Workflow.SuccessCheckCondition"
0x17c08  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17c0d  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddCheckStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x17c12  stloc.0
0x17c13  ldloc.0
0x17c14  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x17c19  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x17c1e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x17c23  starg.s  4
0x17c25  ldarg.0
0x17c26  ldarg.1
0x17c27  ldloc.0
0x17c28  call     instance void Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::AddSuccessStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase successCriteriaStep)
0x17c2d  ldarg.0
0x17c2e  ldarg.s  4
0x17c30  ldarg.1
0x17c31  ldstr    asc_1EEAE// ""
0x17c36  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x17c3b  ldloc.0
0x17c3c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x17c41  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x17c46  starg.s  3
0x17c48  ldarg.0
0x17c49  ldarg.3
0x17c4a  ldarg.1
0x17c4b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x17c50  ldstr    aWebSlaWorkflow_5// "Web.SLA.Workflow.TimeoutWarnAt"
0x17c55  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17c5a  ldc.i4.2
0x17c5b  ldstr    aComputedwarnin// "computedwarningtime"
0x17c60  ldarg.0
0x17c61  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::_successWhenStep
0x17c66  call     instance void Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::AddwaitAndTimeoutPeriodSteps(string waitStepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string stepDescription, int32 slaKpiStatus, string computedDateTime, string _successStep)
0x17c6b  ldarg.0
0x17c6c  ldarg.3
0x17c6d  ldarg.1
0x17c6e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x17c73  ldstr    aWebSlaWorkflow_7// "Web.SLA.Workflow.TimeoutFailureAt"
0x17c78  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17c7d  ldc.i4.1
0x17c7e  ldstr    aComputedfailur// "computedfailuretime"
0x17c83  ldarg.0
0x17c84  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::_successWhenStep
0x17c89  call     instance void Microsoft.Crm.Service.ObjectModel.SLAItemForKPIHelper::AddwaitAndTimeoutPeriodSteps(string waitStepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string stepDescription, int32 slaKpiStatus, string computedDateTime, string _successStep)
0x17c8e  ret
```
