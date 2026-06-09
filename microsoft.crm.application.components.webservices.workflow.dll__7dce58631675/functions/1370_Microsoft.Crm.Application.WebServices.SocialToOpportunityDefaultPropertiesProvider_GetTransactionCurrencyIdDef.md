# Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetTransactionCurrencyIdDefaultProperty

- ea: `0x1370`
- end: `0x1392`
- name: `Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::GetTransactionCurrencyIdDefaultProperty`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x11f0`

## callees

- `0x14e0`
- `0x1610`

## pseudocode

```c

```

## disassembly

```asm
0x1370  ldarg.2
0x1371  newobj   instance void Microsoft.Crm.Application.WebServices.TransactionCurrencyExpressionProvider::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1376  stloc.0
0x1377  ldarg.1
0x1378  ldc.i4.0
0x1379  ldloc.0
0x137a  ldarg.1
0x137b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[] Microsoft.Crm.Application.WebServices.IExpressionProvider::GetExpressions(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x1380  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x1385  stloc.1
0x1386  ldstr    aTransactioncur// "transactioncurrencyid"
0x138b  ldloc.1
0x138c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::.ctor(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x1391  ret
```
