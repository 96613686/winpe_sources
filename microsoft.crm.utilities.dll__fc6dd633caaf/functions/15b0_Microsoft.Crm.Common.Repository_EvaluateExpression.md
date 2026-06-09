# Microsoft.Crm.Common.Repository::EvaluateExpression

- ea: `0x15b0`
- end: `0x15b7`
- name: `Microsoft.Crm.Common.Repository::EvaluateExpression`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x12c0`

## callees

- `0x610`

## pseudocode

```c

```

## disassembly

```asm
0x15b0  ldarg.0
0x15b1  call     object Microsoft.Crm.Common.ExpressionUtility::EvaluateExpression(class [System.Core]System.Linq.Expressions.Expression expression)
0x15b6  ret
```
