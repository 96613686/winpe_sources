# Microsoft.Crm.Application.WebServices.WorkflowWebService::ExtractTimeSpanExpression

- ea: `0x49f0`
- end: `0x4a41`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::ExtractTimeSpanExpression`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4860`
- `0x4940`

## callees

- `0x49f0`

## pseudocode

```c

```

## disassembly

```asm
0x49f0  ldarg.1
0x49f1  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression
0x49f6  stloc.0
0x49f7  ldloc.0
0x49f8  brfalse.s loc_4A03
0x49fa  ldloc.0
0x49fb  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::get_Method()
0x4a00  ldc.i4.3
0x4a01  beq.s    loc_4A05
0x4a03  ldarg.1
0x4a04  ret
0x4a05  ldloc.0
0x4a06  callvirt instance object[] [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::GetParameters()
0x4a0b  stloc.1
0x4a0c  ldloc.1
0x4a0d  ldlen
0x4a0e  conv.i4
0x4a0f  ldc.i4.3
0x4a10  bne.un.s loc_4A3F
0x4a12  ldloc.1
0x4a13  ldc.i4.1
0x4a14  ldelem.ref
0x4a15  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression
0x4a1a  stloc.2
0x4a1b  ldloc.2
0x4a1c  brfalse.s loc_4A3F
0x4a1e  ldloc.2
0x4a1f  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::ExtractSelectFirstNull(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression)
0x4a24  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression
0x4a29  stloc.2
0x4a2a  ldloc.2
0x4a2b  brfalse.s loc_4A3F
0x4a2d  ldloc.2
0x4a2e  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::get_Method()
0x4a33  ldc.i4.6
0x4a34  bne.un.s loc_4A3F
0x4a36  ldloc.1
0x4a37  ldc.i4.2
0x4a38  ldelem.ref
0x4a39  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x4a3e  ret
0x4a3f  ldarg.1
0x4a40  ret
```
