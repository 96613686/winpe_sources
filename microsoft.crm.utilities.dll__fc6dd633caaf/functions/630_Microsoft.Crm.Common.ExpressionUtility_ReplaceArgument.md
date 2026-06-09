# Microsoft.Crm.Common.ExpressionUtility::ReplaceArgument

- ea: `0x630`
- end: `0x65e`
- name: `Microsoft.Crm.Common.ExpressionUtility::ReplaceArgument`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1010`

## callees

- `0x630`
- `0x1c90`

## pseudocode

```c

```

## disassembly

```asm
0x630  ldarg.0
0x631  brtrue.s loc_63E
0x633  ldstr    aExpression// "expression"
0x638  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x63d  throw
0x63e  ldarg.0
0x63f  isinst   [System.Core]System.Linq.Expressions.LambdaExpression
0x644  brfalse.s loc_651
0x646  ldstr    aLambdaexpressi// "LambdaExpression is not allowed.  Pleas"...
0x64b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x650  throw
0x651  ldarg.1
0x652  newobj   instance void ArgumentReplacer::.ctor(object argumentValue)
0x657  ldarg.0
0x658  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.ExpressionVisitor::Visit(class [System.Core]System.Linq.Expressions.Expression)
0x65d  ret
```
