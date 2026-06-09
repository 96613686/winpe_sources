# Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetDefaultProperties

- ea: `0xeb0`
- end: `0xf1e`
- name: `Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetDefaultProperties`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0xf20`
- `0xf40`
- `0xfb0`
- `0xfe0`
- `0x1000`
- `0x1020`
- `0x1040`
- `0x1080`

## pseudocode

```c

```

## disassembly

```asm
0xeb0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::.ctor()
0xeb5  dup
0xeb6  ldarg.0
0xeb7  ldarg.2
0xeb8  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetTitleDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xebd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xec2  dup
0xec3  ldarg.0
0xec4  ldarg.2
0xec5  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetCustomerIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xeca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xecf  dup
0xed0  ldarg.0
0xed1  ldarg.2
0xed2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetCaseOriginCodeDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xed7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xedc  dup
0xedd  ldarg.0
0xede  ldarg.2
0xedf  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetSocialProfileIdDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xee4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xee9  dup
0xeea  ldarg.0
0xeeb  ldarg.2
0xeec  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetSentimentValueDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xef1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xef6  dup
0xef7  ldarg.0
0xef8  ldarg.2
0xef9  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetMessageTypeCodeDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xefe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xf03  dup
0xf04  ldarg.0
0xf05  ldarg.2
0xf06  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetBlockedProfileDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xf0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xf10  dup
0xf11  ldarg.0
0xf12  ldarg.2
0xf13  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetInfluencescoreDefaultProperty(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xf18  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0xf1d  ret
```
