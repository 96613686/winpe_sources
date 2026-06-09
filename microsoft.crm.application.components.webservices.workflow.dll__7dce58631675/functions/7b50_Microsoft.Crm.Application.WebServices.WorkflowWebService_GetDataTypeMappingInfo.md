# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDataTypeMappingInfo

- ea: `0x7b50`
- end: `0x7b75`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDataTypeMappingInfo`
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
0x7b50  ldarg.0
0x7b51  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x7b56  ldarg.1
0x7b57  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7b5c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x7b61  dup
0x7b62  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_LastStep()
0x7b67  stloc.0
0x7b68  ldloc.0
0x7b69  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::CreateInstance(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x7b6e  ldarg.2
0x7b6f  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::GetHiddenValueSelectorHtml(string)
0x7b74  ret
```
