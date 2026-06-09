# Microsoft.Crm.Application.WebServices.ResolvedSenderContactReferenceExpressionProvider::GetExpressions

- ea: `0x15a0`
- end: `0x15c7`
- name: `Microsoft.Crm.Application.WebServices.ResolvedSenderContactReferenceExpressionProvider::GetExpressions`
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
0x15a0  ldc.i4.1
0x15a1  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression
0x15a6  dup
0x15a7  ldc.i4.0
0x15a8  ldarg.1
0x15a9  ldc.i4.s 0xE
0x15ab  ldc.i4.1
0x15ac  newarr   [mscorlib]System.Object
0x15b1  dup
0x15b2  ldc.i4.0
0x15b3  ldstr    aResolvedsender_0// "ResolvedSenderContactReference"
0x15b8  ldc.i4.6
0x15b9  ldc.i4.1
0x15ba  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x15bf  stelem.ref
0x15c0  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x15c5  stelem.ref
0x15c6  ret
```
