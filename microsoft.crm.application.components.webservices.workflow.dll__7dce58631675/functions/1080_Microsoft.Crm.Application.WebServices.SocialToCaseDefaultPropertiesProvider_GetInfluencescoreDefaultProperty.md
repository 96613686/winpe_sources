# Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetInfluencescoreDefaultProperty

- ea: `0x1080`
- end: `0x10b8`
- name: `Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::GetInfluencescoreDefaultProperty`
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
0x1080  ldarg.1
0x1081  ldstr    aPostfromprofil// "postfromprofileid"
0x1086  ldstr    aSocialprofile// "socialprofile"
0x108b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1090  stloc.0
0x1091  ldc.i4.1
0x1092  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression
0x1097  dup
0x1098  ldc.i4.0
0x1099  ldloc.0
0x109a  ldstr    aInfluencescore// "influencescore"
0x109f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x10a4  stelem.ref
0x10a5  stloc.1
0x10a6  ldstr    aInfluencescore// "influencescore"
0x10ab  ldloc.1
0x10ac  ldarg.1
0x10ad  newobj   instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::.ctor(string targetAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression[] sourceAttributeExpressions, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x10b2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::GetProperty()
0x10b7  ret
```
