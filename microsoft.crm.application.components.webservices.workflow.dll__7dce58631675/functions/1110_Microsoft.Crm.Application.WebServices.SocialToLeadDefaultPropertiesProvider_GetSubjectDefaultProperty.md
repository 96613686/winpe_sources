# Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetSubjectDefaultProperty

- ea: `0x1110`
- end: `0x1126`
- name: `Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetSubjectDefaultProperty`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x10e0`

## callees

- `0x1490`
- `0x14c0`

## pseudocode

```c

```

## disassembly

```asm
0x1110  ldstr    aSubject// "subject"
0x1115  ldstr    aSubject// "subject"
0x111a  ldarg.1
0x111b  newobj   instance void Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor(string targetAttributeName, string sourceAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1120  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty()
0x1125  ret
```
