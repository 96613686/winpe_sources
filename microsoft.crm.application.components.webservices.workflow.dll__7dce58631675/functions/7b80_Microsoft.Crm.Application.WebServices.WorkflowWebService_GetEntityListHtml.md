# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetEntityListHtml

- ea: `0x7b80`
- end: `0x7ba5`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetEntityListHtml`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`

## pseudocode

```c

```

## disassembly

```asm
0x7b80  ldarg.0
0x7b81  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x7b86  ldarg.1
0x7b87  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7b8c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x7b91  dup
0x7b92  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x7b97  stloc.0
0x7b98  ldloc.0
0x7b99  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::CreateInstance(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x7b9e  ldarg.2
0x7b9f  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::GetEntityListHtml(string)
0x7ba4  ret
```
