# Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetTransactionCurrencyIdDefaultProperty

- ea: `0xe60`
- end: `0xe82`
- name: `Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::GetTransactionCurrencyIdDefaultProperty`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd50`

## callees

- `0x14e0`
- `0x1610`

## pseudocode

```c

```

## disassembly

```asm
0xe60  ldarg.2
0xe61  newobj   instance void Microsoft.Crm.Application.WebServices.TransactionCurrencyExpressionProvider::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xe66  stloc.0
0xe67  ldarg.1
0xe68  ldc.i4.0
0xe69  ldloc.0
0xe6a  ldarg.1
0xe6b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[] Microsoft.Crm.Application.WebServices.IExpressionProvider::GetExpressions(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xe70  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0xe75  stloc.1
0xe76  ldstr    aTransactioncur// "transactioncurrencyid"
0xe7b  ldloc.1
0xe7c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::.ctor(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0xe81  ret
```
