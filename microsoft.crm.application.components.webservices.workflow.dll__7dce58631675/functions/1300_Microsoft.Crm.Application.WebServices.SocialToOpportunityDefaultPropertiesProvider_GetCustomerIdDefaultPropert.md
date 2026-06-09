# Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetCustomerIdDefaultProperty

- ea: `0x1300`
- end: `0x1365`
- name: `Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetCustomerIdDefaultProperty`
- size: `101`
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
0x1300  ldarg.1
0x1301  ldstr    aPostauthor// "postauthor"
0x1306  ldstr    aContact// "contact"
0x130b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1310  stloc.0
0x1311  ldarg.1
0x1312  ldstr    aPostauthor// "postauthor"
0x1317  ldstr    aAccount// "account"
0x131c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1321  stloc.1
0x1322  ldc.i4.3
0x1323  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression
0x1328  dup
0x1329  ldc.i4.0
0x132a  ldloc.0
0x132b  ldstr    aParentcustomer// "parentcustomerid"
0x1330  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x1335  stelem.ref
0x1336  dup
0x1337  ldc.i4.1
0x1338  ldloc.1
0x1339  ldstr    aAccountid// "accountid"
0x133e  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x1343  stelem.ref
0x1344  dup
0x1345  ldc.i4.2
0x1346  ldloc.0
0x1347  ldstr    aContactid// "contactid"
0x134c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x1351  stelem.ref
0x1352  stloc.2
0x1353  ldstr    aCustomerid// "customerid"
0x1358  ldloc.2
0x1359  ldarg.1
0x135a  newobj   instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::.ctor(string targetAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression[] sourceAttributeExpressions, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x135f  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::GetProperty()
0x1364  ret
```
