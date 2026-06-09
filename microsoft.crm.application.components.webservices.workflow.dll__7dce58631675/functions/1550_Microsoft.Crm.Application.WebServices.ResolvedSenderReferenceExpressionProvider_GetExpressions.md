# Microsoft.Crm.Application.WebServices.ResolvedSenderReferenceExpressionProvider::GetExpressions

- ea: `0x1550`
- end: `0x1577`
- name: `Microsoft.Crm.Application.WebServices.ResolvedSenderReferenceExpressionProvider::GetExpressions`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1550  ldc.i4.1
0x1551  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression
0x1556  dup
0x1557  ldc.i4.0
0x1558  ldarg.1
0x1559  ldc.i4.s 0xE
0x155b  ldc.i4.1
0x155c  newarr   [mscorlib]System.Object
0x1561  dup
0x1562  ldc.i4.0
0x1563  ldstr    aResolvedsender// "ResolvedSenderReference"
0x1568  ldc.i4.6
0x1569  ldc.i4.1
0x156a  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x156f  stelem.ref
0x1570  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x1575  stelem.ref
0x1576  ret
```
