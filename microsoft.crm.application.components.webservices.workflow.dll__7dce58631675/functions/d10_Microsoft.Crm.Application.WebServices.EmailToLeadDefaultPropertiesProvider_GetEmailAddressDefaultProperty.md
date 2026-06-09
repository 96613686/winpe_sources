# Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetEmailAddressDefaultProperty

- ea: `0xd10`
- end: `0xd26`
- name: `Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetEmailAddressDefaultProperty`
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
0xd10  ldstr    aEmailaddress1// "emailaddress1"
0xd15  ldstr    aSender// "sender"
0xd1a  ldarg.1
0xd1b  newobj   instance void Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor(string targetAttributeName, string sourceAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xd20  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::GetProperty()
0xd25  ret
```
