# Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetDefaultProperties

- ea: `0xca0`
- end: `0xccd`
- name: `Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetDefaultProperties`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xcd0`
- `0xcf0`
- `0xd10`

## pseudocode

```c

```

## disassembly

```asm
0xca0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::.ctor()
0xca5  dup
0xca6  ldarg.0
0xca7  ldarg.2
0xca8  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetSubjectDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xcad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xcb2  dup
0xcb3  ldarg.0
0xcb4  ldarg.2
0xcb5  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetLastNameDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xcba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xcbf  dup
0xcc0  ldarg.0
0xcc1  ldarg.2
0xcc2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::GetEmailAddressDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xcc7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xccc  ret
```
