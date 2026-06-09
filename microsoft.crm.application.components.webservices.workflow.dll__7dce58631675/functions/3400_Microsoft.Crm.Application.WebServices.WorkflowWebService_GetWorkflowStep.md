# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowStep

- ea: `0x3400`
- end: `0x3412`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowStep`
- size: `18`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3460`
- `0x3570`
- `0x3910`
- `0x3930`

## callees

- `0x1ab0`

## pseudocode

```c

```

## disassembly

```asm
0x3400  ldarg.0
0x3401  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x3406  ldarg.1
0x3407  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x340c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x3411  ret
```
