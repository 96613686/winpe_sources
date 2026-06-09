# Microsoft.Crm.Common.ExpressionUtility::EvaluateExpression

- ea: `0x610`
- end: `0x627`
- name: `Microsoft.Crm.Common.ExpressionUtility::EvaluateExpression`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1010`
- `0x15b0`

## callees

- `0x4a0`
- `0x5f0`
- `0x610`

## pseudocode

```c

```

## disassembly

```asm
0x610  ldnull
0x611  stloc.0
0x612  ldarg.0
0x613  ldloca.s 0
0x615  call     bool Microsoft.Crm.Common.ExpressionUtility::TryEvaluateExpressionFast(class [System.Core]System.Linq.Expressions.Expression expression, [out] object& result)
0x61a  brfalse.s loc_61E
0x61c  ldloc.0
0x61d  ret
0x61e  ldarg.0
0x61f  call     object Microsoft.Crm.Common.ExpressionUtility::EvaluateExpressionSlow(class [System.Core]System.Linq.Expressions.Expression expression)
0x624  stloc.0
0x625  ldloc.0
0x626  ret
```
