# Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetDefaultProperties

- ea: `0x10e0`
- end: `0x110d`
- name: `Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetDefaultProperties`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1110`
- `0x1130`
- `0x1170`

## pseudocode

```c

```

## disassembly

```asm
0x10e0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::.ctor()
0x10e5  dup
0x10e6  ldarg.0
0x10e7  ldarg.2
0x10e8  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetSubjectDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x10ed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x10f2  dup
0x10f3  ldarg.0
0x10f4  ldarg.2
0x10f5  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetLastNameDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x10fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x10ff  dup
0x1100  ldarg.0
0x1101  ldarg.2
0x1102  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetEmailAddressDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1107  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x110c  ret
```
