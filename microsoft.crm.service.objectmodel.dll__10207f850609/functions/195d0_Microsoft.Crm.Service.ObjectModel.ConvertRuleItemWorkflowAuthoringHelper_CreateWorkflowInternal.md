# Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::CreateWorkflowInternal

- ea: `0x195d0`
- end: `0x19704`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::CreateWorkflowInternal`
- size: `308`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x195c0`
- `0x197f0`

## callees

- `0x19b30`
- `0x19ff0`

## pseudocode

```c

```

## disassembly

```asm
0x195d0  ldarg.0
0x195d1  ldarg.0
0x195d2  ldfld    string Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_workflowName
0x195d7  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowName(string)
0x195dc  ldarg.0
0x195dd  ldarg.0
0x195de  ldfld    string Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_entityName
0x195e3  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_PrimaryEntityName(string)
0x195e8  ldarg.0
0x195e9  ldc.i4.0
0x195ea  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_IsSyncWorkflow(bool)
0x195ef  ldarg.0
0x195f0  ldc.i4.0
0x195f1  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowCategory(int32)
0x195f6  ldarg.0
0x195f7  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::CreateWorkflow()
0x195fc  stloc.0
0x195fd  ldarg.0
0x195fe  ldloc.0
0x195ff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x19604  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_workflowId
0x19609  ldarg.0
0x1960a  ldstr    asc_1EEAE// ""
0x1960f  ldloc.0
0x19610  ldarg.0
0x19611  ldfld    string Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_successCondition
0x19616  ldstr    asc_1EEAE// ""
0x1961b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x19620  ldstr    aWebConvertrule_0// "Web.ConvertRuleItem.Workflow.SuccessCon"...
0x19625  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1962a  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddCheckStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x1962f  pop
0x19630  ldarg.0
0x19631  ldstr    asc_1EEAE// ""
0x19636  ldloc.0
0x19637  ldarg.0
0x19638  ldfld    string Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_successCondition
0x1963d  ldstr    asc_1EEAE// ""
0x19642  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x19647  ldstr    aWebConvertrule_0// "Web.ConvertRuleItem.Workflow.SuccessCon"...
0x1964c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19651  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddCheckStep(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x19656  pop
0x19657  ldarg.0
0x19658  ldstr    aConditionbranc_5// "ConditionBranchStep2"
0x1965d  ldarg.0
0x1965e  ldfld    string Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_successCondition
0x19663  ldloc.0
0x19664  ldstr    asc_1EEAE// ""
0x19669  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddElseIfStep(string, string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x1966e  pop
0x1966f  ldarg.0
0x19670  ldstr    aConditionbranc_5// "ConditionBranchStep2"
0x19675  ldarg.0
0x19676  ldloc.0
0x19677  ldarg.0
0x19678  ldfld    string Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_successCondition
0x1967d  ldc.i4.1
0x1967e  ldc.i4.0
0x1967f  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::GetSuccessCondition(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string defaultSuccessCondition, int32 conversionScenario, [opt] bool addRecordCreationCondition)
0x19684  ldloc.0
0x19685  ldstr    asc_1EEAE// ""
0x1968a  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpdateCondition(string stepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase expression, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x1968f  ldarg.0
0x19690  ldstr    aConditionbranc// "ConditionBranchStep4"
0x19695  ldarg.0
0x19696  ldloc.0
0x19697  ldarg.0
0x19698  ldfld    string Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_successCondition
0x1969d  ldc.i4.1
0x1969e  ldc.i4.0
0x1969f  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::GetSuccessCondition(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string defaultSuccessCondition, int32 conversionScenario, [opt] bool addRecordCreationCondition)
0x196a4  ldloc.0
0x196a5  ldstr    asc_1EEAE// ""
0x196aa  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpdateCondition(string stepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase expression, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x196af  ldarg.0
0x196b0  ldstr    aConditionbranc_7// "ConditionBranchStep5"
0x196b5  ldarg.0
0x196b6  ldloc.0
0x196b7  ldarg.0
0x196b8  ldfld    string Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_successCondition
0x196bd  ldc.i4.2
0x196be  ldc.i4.0
0x196bf  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::GetSuccessCondition(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string defaultSuccessCondition, int32 conversionScenario, [opt] bool addRecordCreationCondition)
0x196c4  ldloc.0
0x196c5  ldstr    asc_1EEAE// ""
0x196ca  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpdateCondition(string stepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase expression, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x196cf  ldloc.0
0x196d0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x196d5  dup
0x196d6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ResetTriggerConditions()
0x196db  dup
0x196dc  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ResetTriggers()
0x196e1  dup
0x196e2  ldc.i4.8
0x196e3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTrigger(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x196e8  dup
0x196e9  ldc.i4.4
0x196ea  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTrigger(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes)
0x196ef  ldstr    aConvertruleite_1// "convertruleitem"
0x196f4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_WorkflowRendererObjectTypeCode(string)
0x196f9  ldarg.0
0x196fa  ldloc.0
0x196fb  ldarg.1
0x196fc  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0x19701  pop
0x19702  ldloc.0
0x19703  ret
```
