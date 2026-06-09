# Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetMessageTypeCodeDefaultProperty

- ea: `0x1020`
- end: `0x1036`
- name: `Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetMessageTypeCodeDefaultProperty`
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
0x1020  ldstr    aMessagetypecod// "messagetypecode"
0x1025  ldstr    aPostmessagetyp// "postmessagetype"
0x102a  ldarg.1
0x102b  newobj   instance void Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor(string targetAttributeName, string sourceAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1030  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty()
0x1035  ret
```
