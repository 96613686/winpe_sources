# Microsoft.Crm.Common.ExpressionUtility::EvaluateExpressionSlow

- ea: `0x5f0`
- end: `0x603`
- name: `Microsoft.Crm.Common.ExpressionUtility::EvaluateExpressionSlow`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x610`

## pseudocode

```c

```

## disassembly

```asm
0x5f0  ldarg.0
0x5f1  ldnull
0x5f2  call     class [System.Core]System.Linq.Expressions.LambdaExpression [System.Core]System.Linq.Expressions.Expression::Lambda(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.ParameterExpression[])
0x5f7  callvirt instance class [mscorlib]System.Delegate [System.Core]System.Linq.Expressions.LambdaExpression::Compile()
0x5fc  ldnull
0x5fd  callvirt instance object [mscorlib]System.Delegate::DynamicInvoke(object[])
0x602  ret
```
