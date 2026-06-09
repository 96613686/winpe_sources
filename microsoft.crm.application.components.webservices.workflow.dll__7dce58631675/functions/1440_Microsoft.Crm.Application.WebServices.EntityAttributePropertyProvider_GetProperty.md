# Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::GetProperty

- ea: `0x1440`
- end: `0x1460`
- name: `Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::GetProperty`
- size: `32`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xde0`
- `0xf40`
- `0x1040`
- `0x1080`
- `0x1130`
- `0x1170`
- `0x1260`
- `0x12a0`
- `0x1300`
- `0x14c0`

## callees

- `0x13c0`
- `0x13e0`
- `0x1400`

## pseudocode

```c

```

## disassembly

```asm
0x1440  ldarg.0
0x1441  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::get_Workflow()
0x1446  ldc.i4.0
0x1447  ldarg.0
0x1448  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression[] Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::get_SourceAttributeExpressions()
0x144d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x1452  stloc.0
0x1453  ldarg.0
0x1454  call     instance string Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::get_TargetAttributeName()
0x1459  ldloc.0
0x145a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::.ctor(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x145f  ret
```
