# Microsoft.Crm.Application.WebServices.WorkflowWebService::CheckStepEntity

- ea: `0x9220`
- end: `0x9228`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::CheckStepEntity`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2070`

## pseudocode

```c

```

## disassembly

```asm
0x9220  ldarg.2
0x9221  ldarg.1
0x9222  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.StepControlHelper::ContainValidCreatedByEntityForControl(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x9227  ret
```
