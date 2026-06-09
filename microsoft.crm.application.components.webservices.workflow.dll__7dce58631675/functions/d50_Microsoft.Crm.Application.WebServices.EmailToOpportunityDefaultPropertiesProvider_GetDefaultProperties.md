# Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetDefaultProperties

- ea: `0xd50`
- end: `0xd98`
- name: `Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetDefaultProperties`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0xda0`
- `0xdc0`
- `0xde0`
- `0xe40`
- `0xe60`

## pseudocode

```c

```

## disassembly

```asm
0xd50  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::.ctor()
0xd55  dup
0xd56  ldarg.0
0xd57  ldarg.2
0xd58  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetNameDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xd5d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xd62  dup
0xd63  ldarg.0
0xd64  ldarg.2
0xd65  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetParentContactIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xd6a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xd6f  dup
0xd70  ldarg.0
0xd71  ldarg.2
0xd72  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetParentAccountIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xd77  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xd7c  dup
0xd7d  ldarg.0
0xd7e  ldarg.2
0xd7f  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetCustomerIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xd84  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xd89  dup
0xd8a  ldarg.0
0xd8b  ldarg.2
0xd8c  ldarg.3
0xd8d  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetTransactionCurrencyIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xd92  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xd97  ret
```
