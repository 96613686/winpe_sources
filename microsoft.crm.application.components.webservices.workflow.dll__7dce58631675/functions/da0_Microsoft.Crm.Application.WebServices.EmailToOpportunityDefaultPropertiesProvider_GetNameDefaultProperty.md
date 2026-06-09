# Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetNameDefaultProperty

- ea: `0xda0`
- end: `0xdb6`
- name: `Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetNameDefaultProperty`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd50`

## callees

- `0x1490`
- `0x14c0`

## pseudocode

```c

```

## disassembly

```asm
0xda0  ldstr    aName// "name"
0xda5  ldstr    aSubject// "subject"
0xdaa  ldarg.1
0xdab  newobj   instance void Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor(string targetAttributeName, string sourceAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xdb0  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty()
0xdb5  ret
```
