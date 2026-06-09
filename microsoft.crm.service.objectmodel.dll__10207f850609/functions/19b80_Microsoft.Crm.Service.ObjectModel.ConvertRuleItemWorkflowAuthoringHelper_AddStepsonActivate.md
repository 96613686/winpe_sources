# Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::AddStepsonActivate

- ea: `0x19b80`
- end: `0x19c12`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::AddStepsonActivate`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x17e90`

## callees

- `0x19b80`
- `0x19c20`
- `0x19cd0`
- `0x19d20`
- `0x19e80`

## pseudocode

```c

```

## disassembly

```asm
0x19b80  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19b85  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19b8a  dup
0x19b8b  ldarg.s  4
0x19b8d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::set_OverriddenOwnerId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x19b92  ldarg.0
0x19b93  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_workflowId
0x19b98  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x19b9d  stloc.0
0x19b9e  ldloc.0
0x19b9f  call     void Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::RemoveStepsInternal(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x19ba4  ldloc.0
0x19ba5  ldstr    aConditionbranc_5// "ConditionBranchStep2"
0x19baa  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x19baf  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x19bb4  stloc.1
0x19bb5  ldloc.1
0x19bb6  brfalse.s loc_19BC5
0x19bb8  ldloc.1
0x19bb9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x19bbe  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x19bc3  brfalse.s loc_19BC6
0x19bc5  ret
0x19bc6  ldloc.1
0x19bc7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x19bcc  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep
0x19bd1  stloc.2
0x19bd2  ldarg.0
0x19bd3  ldloc.0
0x19bd4  ldloc.2
0x19bd5  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpdatePrimaryActionBlockSuccessCondition(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep)
0x19bda  ldarg.0
0x19bdb  ldloc.2
0x19bdc  ldloc.0
0x19bdd  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::AddPrimaryEntityUpdateStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x19be2  ldarg.0
0x19be3  ldloc.0
0x19be4  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::AddTargetEntityUpdateStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x19be9  ldarg.3
0x19bea  brfalse.s loc_19BF7
0x19bec  ldarg.0
0x19bed  ldloc.0
0x19bee  ldloc.1
0x19bef  ldloc.2
0x19bf0  ldarg.2
0x19bf1  ldarg.1
0x19bf2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::AddSendEmailStepForConvertRuleAndConvertRuleItemWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, valuetype [mscorlib]System.Guid)
0x19bf7  ldloc.0
0x19bf8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x19bfd  ldstr    aConvertruleite_1// "convertruleitem"
0x19c02  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_WorkflowRendererObjectTypeCode(string)
0x19c07  ldarg.0
0x19c08  ldloc.0
0x19c09  ldarg.s  5
0x19c0b  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0x19c10  pop
0x19c11  ret
```
