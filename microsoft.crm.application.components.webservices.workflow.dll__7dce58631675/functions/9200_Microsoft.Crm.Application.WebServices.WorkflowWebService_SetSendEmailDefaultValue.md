# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetSendEmailDefaultValue

- ea: `0x9200`
- end: `0x9218`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetSendEmailDefaultValue`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x5690`
- `0x5700`

## pseudocode

```c

```

## disassembly

```asm
0x9200  ldarg.1
0x9201  ldc.i4.0
0x9202  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_SendEmailStepType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailType)
0x9207  ldarg.1
0x9208  ldstr    aEmail// "email"
0x920d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x9212  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification)
0x9217  ret
```
