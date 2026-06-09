# Microsoft.Crm.Common.Repository::IsLiftToNullValueType

- ea: `0x1440`
- end: `0x14c6`
- name: `Microsoft.Crm.Common.Repository::IsLiftToNullValueType`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x12c0`

## callees

- `0x1440`

## pseudocode

```c

```

## disassembly

```asm
0x1440  ldarg.0
0x1441  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0x1446  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x144b  ldc.i4.s 0xA
0x144d  bne.un.s loc_1482
0x144f  ldarg.0
0x1450  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0x1455  isinst   [System.Core]System.Linq.Expressions.UnaryExpression
0x145a  brfalse.s loc_1482
0x145c  ldarg.0
0x145d  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0x1462  castclass [System.Core]System.Linq.Expressions.UnaryExpression
0x1467  callvirt instance bool [System.Core]System.Linq.Expressions.UnaryExpression::get_IsLiftedToNull()
0x146c  brfalse.s loc_1482
0x146e  ldarg.0
0x146f  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0x1474  callvirt instance class [mscorlib]System.Type [System.Core]System.Linq.Expressions.Expression::get_Type()
0x1479  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x147e  brfalse.s loc_1482
0x1480  ldc.i4.1
0x1481  ret
0x1482  ldarg.0
0x1483  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Right()
0x1488  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x148d  ldc.i4.s 0xA
0x148f  bne.un.s loc_14C4
0x1491  ldarg.0
0x1492  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Right()
0x1497  isinst   [System.Core]System.Linq.Expressions.UnaryExpression
0x149c  brfalse.s loc_14C4
0x149e  ldarg.0
0x149f  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0x14a4  castclass [System.Core]System.Linq.Expressions.UnaryExpression
0x14a9  callvirt instance bool [System.Core]System.Linq.Expressions.UnaryExpression::get_IsLiftedToNull()
0x14ae  brfalse.s loc_14C4
0x14b0  ldarg.0
0x14b1  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Right()
0x14b6  callvirt instance class [mscorlib]System.Type [System.Core]System.Linq.Expressions.Expression::get_Type()
0x14bb  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x14c0  brfalse.s loc_14C4
0x14c2  ldc.i4.1
0x14c3  ret
0x14c4  ldc.i4.0
0x14c5  ret
```
