# Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetLastNameDefaultProperty

- ea: `0xcf0`
- end: `0xd06`
- name: `Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetLastNameDefaultProperty`
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
0xcf0  ldstr    aLastname// "lastname"
0xcf5  ldstr    aFrom// "from"
0xcfa  ldarg.1
0xcfb  newobj   instance void Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor(string targetAttributeName, string sourceAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xd00  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty()
0xd05  ret
```
