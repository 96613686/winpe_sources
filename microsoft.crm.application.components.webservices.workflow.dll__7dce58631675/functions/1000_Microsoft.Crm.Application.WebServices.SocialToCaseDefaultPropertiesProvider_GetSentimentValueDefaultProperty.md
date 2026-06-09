# Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetSentimentValueDefaultProperty

- ea: `0x1000`
- end: `0x1016`
- name: `Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetSentimentValueDefaultProperty`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xeb0`

## callees

- `0x1490`
- `0x14c0`

## pseudocode

```c

```

## disassembly

```asm
0x1000  ldstr    aSentimentvalue// "sentimentvalue"
0x1005  ldstr    aSentimentvalue// "sentimentvalue"
0x100a  ldarg.1
0x100b  newobj   instance void Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor(string targetAttributeName, string sourceAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1010  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty()
0x1015  ret
```
