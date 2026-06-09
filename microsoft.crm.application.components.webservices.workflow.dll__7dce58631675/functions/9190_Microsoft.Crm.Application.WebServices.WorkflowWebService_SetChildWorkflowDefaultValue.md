# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChildWorkflowDefaultValue

- ea: `0x9190`
- end: `0x91b5`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChildWorkflowDefaultValue`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4fd0`
- `0x5040`

## callees

- `0x9190`

## pseudocode

```c

```

## disassembly

```asm
0x9190  ldarg.1
0x9191  ldarg.1
0x9192  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.StepControlHelper::GetDefaultEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x9197  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x919c  ldarg.1
0x919d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::get_Entity()
0x91a2  brtrue.s loc_91B4
0x91a4  ldstr    aNoEntitiesAvai// "No entities available for child workflo"...
0x91a9  ldstr    aEntity// "entity"
0x91ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x91b3  throw
0x91b4  ret
```
