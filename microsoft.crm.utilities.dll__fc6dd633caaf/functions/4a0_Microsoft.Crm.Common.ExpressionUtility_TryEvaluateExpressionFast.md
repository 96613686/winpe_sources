# Microsoft.Crm.Common.ExpressionUtility::TryEvaluateExpressionFast

- ea: `0x4a0`
- end: `0x5ee`
- name: `Microsoft.Crm.Common.ExpressionUtility::TryEvaluateExpressionFast`
- size: `334`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4a0`
- `0x610`
- `0x660`

## callees

- `0x4a0`
- `0x660`

## pseudocode

```c

```

## disassembly

```asm
0x4a0  ldarg.0
0x4a1  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x4a6  ldc.i4.s 9
0x4a8  bne.un.s loc_4BB
0x4aa  ldarg.0
0x4ab  castclass [System.Core]System.Linq.Expressions.ConstantExpression
0x4b0  stloc.0
0x4b1  ldarg.1
0x4b2  ldloc.0
0x4b3  callvirt instance object [System.Core]System.Linq.Expressions.ConstantExpression::get_Value()
0x4b8  stind.ref
0x4b9  ldc.i4.1
0x4ba  ret
0x4bb  ldarg.0
0x4bc  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x4c1  ldc.i4.s 0x17
0x4c3  bne.un.s loc_53D
0x4c5  ldarg.0
0x4c6  castclass [System.Core]System.Linq.Expressions.MemberExpression
0x4cb  stloc.1
0x4cc  ldnull
0x4cd  stloc.2
0x4ce  ldloc.1
0x4cf  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MemberExpression::get_Expression()
0x4d4  brfalse.s loc_4EA
0x4d6  ldloc.1
0x4d7  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MemberExpression::get_Expression()
0x4dc  ldloca.s 2
0x4de  call     bool Microsoft.Crm.Common.ExpressionUtility::TryEvaluateExpressionFast(class [System.Core]System.Linq.Expressions.Expression expression, [out] object& result)
0x4e3  brtrue.s loc_4EA
0x4e5  ldarg.1
0x4e6  ldnull
0x4e7  stind.ref
0x4e8  ldc.i4.0
0x4e9  ret
0x4ea  ldloc.1
0x4eb  callvirt instance class [mscorlib]System.Reflection.MemberInfo [System.Core]System.Linq.Expressions.MemberExpression::get_Member()
0x4f0  callvirt instance valuetype [mscorlib]System.Reflection.MemberTypes [mscorlib]System.Reflection.MemberInfo::get_MemberType()
0x4f5  ldc.i4.4
0x4f6  bne.un.s loc_50F
0x4f8  ldloc.1
0x4f9  callvirt instance class [mscorlib]System.Reflection.MemberInfo [System.Core]System.Linq.Expressions.MemberExpression::get_Member()
0x4fe  isinst   [mscorlib]System.Reflection.FieldInfo
0x503  stloc.3
0x504  ldarg.1
0x505  ldloc.3
0x506  ldloc.2
0x507  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0x50c  stind.ref
0x50d  ldc.i4.1
0x50e  ret
0x50f  ldloc.1
0x510  callvirt instance class [mscorlib]System.Reflection.MemberInfo [System.Core]System.Linq.Expressions.MemberExpression::get_Member()
0x515  callvirt instance valuetype [mscorlib]System.Reflection.MemberTypes [mscorlib]System.Reflection.MemberInfo::get_MemberType()
0x51a  ldc.i4.s 0x10
0x51c  bne.un.s loc_538
0x51e  ldloc.1
0x51f  callvirt instance class [mscorlib]System.Reflection.MemberInfo [System.Core]System.Linq.Expressions.MemberExpression::get_Member()
0x524  isinst   [mscorlib]System.Reflection.PropertyInfo
0x529  stloc.s  4
0x52b  ldarg.1
0x52c  ldloc.s  4
0x52e  ldloc.2
0x52f  ldnull
0x530  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x535  stind.ref
0x536  ldc.i4.1
0x537  ret
0x538  ldarg.1
0x539  ldnull
0x53a  stind.ref
0x53b  ldc.i4.0
0x53c  ret
0x53d  ldarg.0
0x53e  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x543  ldc.i4.s 0x1F
0x545  bne.un.s loc_582
0x547  ldarg.0
0x548  isinst   [System.Core]System.Linq.Expressions.NewExpression
0x54d  stloc.s  5
0x54f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0x554  stloc.s  6
0x556  ldloc.s  5
0x558  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.NewExpression::get_Arguments()
0x55d  ldloca.s 6
0x55f  call     bool Microsoft.Crm.Common.ExpressionUtility::TryEvaluateArguments(class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Core]System.Linq.Expressions.Expression> arguments, [out] class [mscorlib]System.Collections.Generic.List`1<object>& argumentList)
0x564  brtrue.s loc_56B
0x566  ldarg.1
0x567  ldnull
0x568  stind.ref
0x569  ldc.i4.0
0x56a  ret
0x56b  ldarg.1
0x56c  ldloc.s  5
0x56e  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [System.Core]System.Linq.Expressions.NewExpression::get_Constructor()
0x573  ldloc.s  6
0x575  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<object>::ToArray()
0x57a  callvirt instance object [mscorlib]System.Reflection.ConstructorInfo::Invoke(object[])
0x57f  stind.ref
0x580  ldc.i4.1
0x581  ret
0x582  ldarg.0
0x583  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x588  ldc.i4.6
0x589  bne.un.s loc_5E9
0x58b  ldarg.0
0x58c  isinst   [System.Core]System.Linq.Expressions.MethodCallExpression
0x591  stloc.s  7
0x593  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0x598  stloc.s  8
0x59a  ldloc.s  7
0x59c  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0x5a1  ldloca.s 8
0x5a3  call     bool Microsoft.Crm.Common.ExpressionUtility::TryEvaluateArguments(class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Core]System.Linq.Expressions.Expression> arguments, [out] class [mscorlib]System.Collections.Generic.List`1<object>& argumentList)
0x5a8  brtrue.s loc_5AF
0x5aa  ldarg.1
0x5ab  ldnull
0x5ac  stind.ref
0x5ad  ldc.i4.0
0x5ae  ret
0x5af  ldnull
0x5b0  stloc.s  9
0x5b2  ldloc.s  7
0x5b4  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MethodCallExpression::get_Object()
0x5b9  brfalse.s loc_5D0
0x5bb  ldloc.s  7
0x5bd  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MethodCallExpression::get_Object()
0x5c2  ldloca.s 9
0x5c4  call     bool Microsoft.Crm.Common.ExpressionUtility::TryEvaluateExpressionFast(class [System.Core]System.Linq.Expressions.Expression expression, [out] object& result)
0x5c9  brtrue.s loc_5D0
0x5cb  ldarg.1
0x5cc  ldnull
0x5cd  stind.ref
0x5ce  ldc.i4.0
0x5cf  ret
0x5d0  ldarg.1
0x5d1  ldloc.s  7
0x5d3  callvirt instance class [mscorlib]System.Reflection.MethodInfo [System.Core]System.Linq.Expressions.MethodCallExpression::get_Method()
0x5d8  ldloc.s  9
0x5da  ldloc.s  8
0x5dc  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<object>::ToArray()
0x5e1  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x5e6  stind.ref
0x5e7  ldc.i4.1
0x5e8  ret
0x5e9  ldarg.1
0x5ea  ldnull
0x5eb  stind.ref
0x5ec  ldc.i4.0
0x5ed  ret
```
