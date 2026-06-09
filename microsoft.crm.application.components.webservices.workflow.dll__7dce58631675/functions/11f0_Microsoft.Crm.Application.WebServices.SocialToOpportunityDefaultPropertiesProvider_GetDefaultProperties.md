# Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetDefaultProperties

- ea: `0x11f0`
- end: `0x1238`
- name: `Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetDefaultProperties`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1240`
- `0x1260`
- `0x12a0`
- `0x1300`
- `0x1370`

## pseudocode

```c

```

## disassembly

```asm
0x11f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::.ctor()
0x11f5  dup
0x11f6  ldarg.0
0x11f7  ldarg.2
0x11f8  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetNameDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x11fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x1202  dup
0x1203  ldarg.0
0x1204  ldarg.2
0x1205  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetParentContactIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x120a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x120f  dup
0x1210  ldarg.0
0x1211  ldarg.2
0x1212  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetParentAccountIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1217  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x121c  dup
0x121d  ldarg.0
0x121e  ldarg.2
0x121f  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetCustomerIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1224  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x1229  dup
0x122a  ldarg.0
0x122b  ldarg.2
0x122c  ldarg.3
0x122d  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetTransactionCurrencyIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1232  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x1237  ret
```
