# Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetBlockedProfileDefaultProperty

- ea: `0x1040`
- end: `0x1078`
- name: `Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetBlockedProfileDefaultProperty`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xeb0`

## callees

- `0x1420`
- `0x1440`

## pseudocode

```c

```

## disassembly

```asm
0x1040  ldarg.1
0x1041  ldstr    aPostfromprofil// "postfromprofileid"
0x1046  ldstr    aSocialprofile// "socialprofile"
0x104b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1050  stloc.0
0x1051  ldc.i4.1
0x1052  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression
0x1057  dup
0x1058  ldc.i4.0
0x1059  ldloc.0
0x105a  ldstr    aBlocked// "blocked"
0x105f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x1064  stelem.ref
0x1065  stloc.1
0x1066  ldstr    aBlockedprofile// "blockedprofile"
0x106b  ldloc.1
0x106c  ldarg.1
0x106d  newobj   instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::.ctor(string targetAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression[] sourceAttributeExpressions, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1072  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::GetProperty()
0x1077  ret
```
