# Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::GetDefaultProperties

- ea: `0xbb0`
- end: `0xbea`
- name: `Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::GetDefaultProperties`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xbf0`
- `0xc10`
- `0xc30`
- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0xbb0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::.ctor()
0xbb5  dup
0xbb6  ldarg.0
0xbb7  ldarg.2
0xbb8  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::GetTitleDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xbbd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xbc2  dup
0xbc3  ldarg.0
0xbc4  ldarg.2
0xbc5  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::GetCustomerIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xbca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xbcf  dup
0xbd0  ldarg.0
0xbd1  ldarg.2
0xbd2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::GetCaseOriginCodeDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xbd7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xbdc  dup
0xbdd  ldarg.0
0xbde  ldarg.2
0xbdf  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::GetPrimaryContactIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xbe4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xbe9  ret
```
