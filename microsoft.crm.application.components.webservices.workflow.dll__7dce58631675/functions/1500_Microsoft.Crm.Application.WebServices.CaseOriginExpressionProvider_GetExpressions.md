# Microsoft.Crm.Application.WebServices.CaseOriginExpressionProvider::GetExpressions

- ea: `0x1500`
- end: `0x1527`
- name: `Microsoft.Crm.Application.WebServices.CaseOriginExpressionProvider::GetExpressions`
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
0x1500  ldc.i4.1
0x1501  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression
0x1506  dup
0x1507  ldc.i4.0
0x1508  ldarg.1
0x1509  ldc.i4.s 0xE
0x150b  ldc.i4.1
0x150c  newarr   [mscorlib]System.Object
0x1511  dup
0x1512  ldc.i4.0
0x1513  ldstr    aCaseorigin// "caseorigin"
0x1518  ldc.i4.5
0x1519  ldc.i4.1
0x151a  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x151f  stelem.ref
0x1520  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x1525  stelem.ref
0x1526  ret
```
