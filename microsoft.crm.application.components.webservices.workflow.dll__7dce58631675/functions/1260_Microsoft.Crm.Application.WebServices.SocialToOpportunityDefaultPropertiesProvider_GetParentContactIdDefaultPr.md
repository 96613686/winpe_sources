# Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetParentContactIdDefaultProperty

- ea: `0x1260`
- end: `0x1298`
- name: `Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetParentContactIdDefaultProperty`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x11f0`

## callees

- `0x1420`
- `0x1440`

## pseudocode

```c

```

## disassembly

```asm
0x1260  ldarg.1
0x1261  ldstr    aPostauthor// "postauthor"
0x1266  ldstr    aContact// "contact"
0x126b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1270  stloc.0
0x1271  ldc.i4.1
0x1272  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression
0x1277  dup
0x1278  ldc.i4.0
0x1279  ldloc.0
0x127a  ldstr    aContactid// "contactid"
0x127f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x1284  stelem.ref
0x1285  stloc.1
0x1286  ldstr    aParentcontacti// "parentcontactid"
0x128b  ldloc.1
0x128c  ldarg.1
0x128d  newobj   instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::.ctor(string targetAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression[] sourceAttributeExpressions, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1292  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::GetProperty()
0x1297  ret
```
