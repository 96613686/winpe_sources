# Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetEmailAddressDefaultProperty

- ea: `0x1170`
- end: `0x11c7`
- name: `Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetEmailAddressDefaultProperty`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x10e0`

## callees

- `0x1420`
- `0x1440`

## pseudocode

```c

```

## disassembly

```asm
0x1170  ldarg.1
0x1171  ldstr    aPostauthor// "postauthor"
0x1176  ldstr    aContact// "contact"
0x117b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1180  stloc.0
0x1181  ldarg.1
0x1182  ldstr    aPostauthor// "postauthor"
0x1187  ldstr    aAccount// "account"
0x118c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1191  stloc.1
0x1192  ldc.i4.2
0x1193  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression
0x1198  dup
0x1199  ldc.i4.0
0x119a  ldloc.0
0x119b  ldstr    aEmailaddress1// "emailaddress1"
0x11a0  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x11a5  stelem.ref
0x11a6  dup
0x11a7  ldc.i4.1
0x11a8  ldloc.1
0x11a9  ldstr    aEmailaddress1// "emailaddress1"
0x11ae  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x11b3  stelem.ref
0x11b4  stloc.2
0x11b5  ldstr    aEmailaddress1// "emailaddress1"
0x11ba  ldloc.2
0x11bb  ldarg.1
0x11bc  newobj   instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::.ctor(string targetAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression[] sourceAttributeExpressions, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x11c1  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::GetProperty()
0x11c6  ret
```
