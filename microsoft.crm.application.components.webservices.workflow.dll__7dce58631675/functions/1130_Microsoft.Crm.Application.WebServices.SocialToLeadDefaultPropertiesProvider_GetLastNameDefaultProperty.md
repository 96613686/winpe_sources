# Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetLastNameDefaultProperty

- ea: `0x1130`
- end: `0x1168`
- name: `Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::GetLastNameDefaultProperty`
- size: `56`
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
0x1130  ldarg.1
0x1131  ldstr    aPostfromprofil// "postfromprofileid"
0x1136  ldstr    aSocialprofile// "socialprofile"
0x113b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1140  stloc.0
0x1141  ldc.i4.1
0x1142  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression
0x1147  dup
0x1148  ldc.i4.0
0x1149  ldloc.0
0x114a  ldstr    aCustomerid// "customerid"
0x114f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x1154  stelem.ref
0x1155  stloc.1
0x1156  ldstr    aLastname// "lastname"
0x115b  ldloc.1
0x115c  ldarg.1
0x115d  newobj   instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::.ctor(string targetAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression[] sourceAttributeExpressions, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1162  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::GetProperty()
0x1167  ret
```
