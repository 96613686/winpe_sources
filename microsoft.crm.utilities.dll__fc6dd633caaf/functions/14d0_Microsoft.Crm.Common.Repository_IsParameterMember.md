# Microsoft.Crm.Common.Repository::IsParameterMember

- ea: `0x14d0`
- end: `0x1565`
- name: `Microsoft.Crm.Common.Repository::IsParameterMember`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x12c0`

## callees

- `0x14d0`
- `0x1570`

## pseudocode

```c

```

## disassembly

```asm
0x14d0  ldarg.2
0x14d1  ldnull
0x14d2  stind.ref
0x14d3  ldarg.0
0x14d4  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x14d9  ldc.i4.s 0x17
0x14db  bne.un.s loc_14E7
0x14dd  ldarg.2
0x14de  ldarg.0
0x14df  isinst   [System.Core]System.Linq.Expressions.MemberExpression
0x14e4  stind.ref
0x14e5  br.s     loc_1529
0x14e7  ldarg.0
0x14e8  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x14ed  ldc.i4.s 0xA
0x14ef  bne.un.s loc_1529
0x14f1  ldarg.0
0x14f2  isinst   [System.Core]System.Linq.Expressions.UnaryExpression
0x14f7  stloc.0
0x14f8  ldloc.0
0x14f9  brfalse.s loc_1529
0x14fb  ldc.i4.1
0x14fc  stloc.1
0x14fd  ldloc.0
0x14fe  callvirt instance bool [System.Core]System.Linq.Expressions.UnaryExpression::get_IsLiftedToNull()
0x1503  brfalse.s loc_1519
0x1505  ldloc.0
0x1506  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.UnaryExpression::get_Operand()
0x150b  callvirt instance class [mscorlib]System.Type [System.Core]System.Linq.Expressions.Expression::get_Type()
0x1510  call     bool Microsoft.Crm.Common.Repository::IsNullableEnum(class [mscorlib]System.Type type)
0x1515  brtrue.s loc_1519
0x1517  ldc.i4.0
0x1518  stloc.1
0x1519  ldloc.1
0x151a  brfalse.s loc_1529
0x151c  ldarg.2
0x151d  ldloc.0
0x151e  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.UnaryExpression::get_Operand()
0x1523  isinst   [System.Core]System.Linq.Expressions.MemberExpression
0x1528  stind.ref
0x1529  ldarg.2
0x152a  ldind.ref
0x152b  brfalse.s loc_1563
0x152d  ldarg.2
0x152e  ldind.ref
0x152f  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MemberExpression::get_Expression()
0x1534  brtrue.s loc_1538
0x1536  ldc.i4.0
0x1537  ret
0x1538  ldarg.2
0x1539  ldind.ref
0x153a  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MemberExpression::get_Expression()
0x153f  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x1544  ldc.i4.s 0x26
0x1546  bne.un.s loc_1563
0x1548  ldarg.2
0x1549  ldind.ref
0x154a  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MemberExpression::get_Expression()
0x154f  isinst   [System.Core]System.Linq.Expressions.ParameterExpression
0x1554  callvirt instance class [mscorlib]System.Type [System.Core]System.Linq.Expressions.Expression::get_Type()
0x1559  ldarg.1
0x155a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x155f  brfalse.s loc_1563
0x1561  ldc.i4.1
0x1562  ret
0x1563  ldc.i4.0
0x1564  ret
```
