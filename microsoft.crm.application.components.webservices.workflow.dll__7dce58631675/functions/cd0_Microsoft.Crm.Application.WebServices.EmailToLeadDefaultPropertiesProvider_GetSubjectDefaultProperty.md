# Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetSubjectDefaultProperty

- ea: `0xcd0`
- end: `0xce6`
- name: `Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetSubjectDefaultProperty`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xca0`

## callees

- `0x1490`
- `0x14c0`

## pseudocode

```c

```

## disassembly

```asm
0xcd0  ldstr    aSubject// "subject"
0xcd5  ldstr    aSubject// "subject"
0xcda  ldarg.1
0xcdb  newobj   instance void Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor(string targetAttributeName, string sourceAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xce0  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty()
0xce5  ret
```
