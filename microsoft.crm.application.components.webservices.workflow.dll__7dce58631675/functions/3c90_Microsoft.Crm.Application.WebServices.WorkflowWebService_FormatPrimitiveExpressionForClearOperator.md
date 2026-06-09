# Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatPrimitiveExpressionForClearOperator

- ea: `0x3c90`
- end: `0x3cae`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatPrimitiveExpressionForClearOperator`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x35d0`
- `0x3990`

## callees

- `0x3c90`

## pseudocode

```c

```

## disassembly

```asm
0x3c90  ldarg.2
0x3c91  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression
0x3c96  stloc.0
0x3c97  ldloc.0
0x3c98  brfalse.s loc_3CAC
0x3c9a  ldloc.0
0x3c9b  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::get_Value()
0x3ca0  brtrue.s loc_3CAC
0x3ca2  ldarg.1
0x3ca3  ldarg.3
0x3ca4  ldarg.s  4
0x3ca6  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x3cab  ret
0x3cac  ldarg.2
0x3cad  ret
```
