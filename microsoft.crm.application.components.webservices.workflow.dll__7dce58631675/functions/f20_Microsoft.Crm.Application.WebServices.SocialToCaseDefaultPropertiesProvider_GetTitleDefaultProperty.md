# Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetTitleDefaultProperty

- ea: `0xf20`
- end: `0xf36`
- name: `Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetTitleDefaultProperty`
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
0xf20  ldstr    aTitle// "title"
0xf25  ldstr    aSubject// "subject"
0xf2a  ldarg.1
0xf2b  newobj   instance void Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor(string targetAttributeName, string sourceAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xf30  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty()
0xf35  ret
```
