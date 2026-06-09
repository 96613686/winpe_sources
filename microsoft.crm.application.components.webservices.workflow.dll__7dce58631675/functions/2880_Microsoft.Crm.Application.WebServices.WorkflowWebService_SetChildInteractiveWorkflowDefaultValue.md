# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChildInteractiveWorkflowDefaultValue

- ea: `0x2880`
- end: `0x28a5`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChildInteractiveWorkflowDefaultValue`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x27d0`
- `0x2820`

## callees

- `0x2880`

## pseudocode

```c

```

## disassembly

```asm
0x2880  ldarg.1
0x2881  ldarg.1
0x2882  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.StepControlHelper::GetDefaultEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2887  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x288c  ldarg.1
0x288d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::get_Entity()
0x2892  brtrue.s loc_28A4
0x2894  ldstr    aNoEntitiesAvai// "No entities available for child workflo"...
0x2899  ldstr    aEntity// "entity"
0x289e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x28a3  throw
0x28a4  ret
```
