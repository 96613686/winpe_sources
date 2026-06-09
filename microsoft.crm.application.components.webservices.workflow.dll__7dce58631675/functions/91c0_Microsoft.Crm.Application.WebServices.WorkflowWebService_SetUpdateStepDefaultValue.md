# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetUpdateStepDefaultValue

- ea: `0x91c0`
- end: `0x91fb`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetUpdateStepDefaultValue`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4cf0`
- `0x4d60`

## callees

- `0x91c0`

## string_xrefs

- `0x91ea`: `No entities available for update step`

## pseudocode

```c

```

## disassembly

```asm
0x91c0  ldarg.1
0x91c1  ldarg.1
0x91c2  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.StepControlHelper::GetDefaultEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x91c7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x91cc  ldarg.1
0x91cd  ldarg.1
0x91ce  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x91d3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x91d8  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x91dd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::set_EntitySpec(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x91e2  ldarg.1
0x91e3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::get_Entity()
0x91e8  brtrue.s loc_91FA
0x91ea  ldstr    aNoEntitiesAvai_1// "No entities available for update step"
0x91ef  ldstr    aEntity// "entity"
0x91f4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x91f9  throw
0x91fa  ret
```
