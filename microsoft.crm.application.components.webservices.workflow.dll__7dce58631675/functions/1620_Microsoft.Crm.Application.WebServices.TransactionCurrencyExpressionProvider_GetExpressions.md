# Microsoft.Crm.Application.WebServices.TransactionCurrencyExpressionProvider::GetExpressions

- ea: `0x1620`
- end: `0x1660`
- name: `Microsoft.Crm.Application.WebServices.TransactionCurrencyExpressionProvider::GetExpressions`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x15f0`

## pseudocode

```c

```

## disassembly

```asm
0x1620  ldarg.0
0x1621  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.WebServices.TransactionCurrencyExpressionProvider::get_OrganizationContext()
0x1626  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ObtainDefaultCurrency(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x162b  stloc.0
0x162c  ldc.i4.1
0x162d  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression
0x1632  dup
0x1633  ldc.i4.0
0x1634  ldarg.1
0x1635  ldarg.1
0x1636  ldloc.0
0x1637  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x163c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1641  box      [mscorlib]System.Guid
0x1646  ldc.i4.s 0xF
0x1648  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x164d  ldc.i4.6
0x164e  ldstr    aTransactioncur_0// "transactioncurrency"
0x1653  ldloc.0
0x1654  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Name()
0x1659  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x165e  stelem.ref
0x165f  ret
```
