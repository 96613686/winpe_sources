# Microsoft.Crm.Common.Repository::ParseSelectorExpression

- ea: `0x10a0`
- end: `0x114f`
- name: `Microsoft.Crm.Common.Repository::ParseSelectorExpression`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1010`

## callees

- `0x10a0`
- `0x1150`
- `0x19f0`

## string_xrefs

- `0x1143`: `Expression was not either MemberAccess or New`

## pseudocode

```c

```

## disassembly

```asm
0x10a0  ldarg.0
0x10a1  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x10a6  ldc.i4.s 0x17
0x10a8  bne.un.s loc_10D0
0x10aa  ldarg.0
0x10ab  isinst   [System.Core]System.Linq.Expressions.MemberExpression
0x10b0  stloc.0
0x10b1  ldarg.2
0x10b2  ldarg.3
0x10b3  ldloc.0
0x10b4  call     void Microsoft.Crm.Common.Repository::VerifyPropertySelectorMemberExpression(class [mscorlib]System.Type objectType, string inputParameterName, class [System.Core]System.Linq.Expressions.MemberExpression memberExp)
0x10b9  ldarg.1
0x10ba  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<string> Microsoft.Crm.Common.RepositoryQuery::get_PropertiesToReturn()
0x10bf  ldloc.0
0x10c0  callvirt instance class [mscorlib]System.Reflection.MemberInfo [System.Core]System.Linq.Expressions.MemberExpression::get_Member()
0x10c5  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10ca  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x10cf  ret
0x10d0  ldarg.0
0x10d1  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x10d6  ldc.i4.s 0x1F
0x10d8  bne.un.s loc_1143
0x10da  ldarg.0
0x10db  isinst   [System.Core]System.Linq.Expressions.NewExpression
0x10e0  dup
0x10e1  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.NewExpression::get_Arguments()
0x10e6  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Count()
0x10eb  brtrue.s loc_10F8
0x10ed  ldstr    aNewexpressionI// "NewExpression is expected to have at le"...
0x10f2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x10f7  throw
0x10f8  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.NewExpression::get_Arguments()
0x10fd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::GetEnumerator()
0x1102  stloc.1
0x1103  br.s     loc_112F
0x1105  ldloc.1
0x1106  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.Expressions.Expression>::get_Current()
0x110b  isinst   [System.Core]System.Linq.Expressions.MemberExpression
0x1110  stloc.2
0x1111  ldarg.2
0x1112  ldarg.3
0x1113  ldloc.2
0x1114  call     void Microsoft.Crm.Common.Repository::VerifyPropertySelectorMemberExpression(class [mscorlib]System.Type objectType, string inputParameterName, class [System.Core]System.Linq.Expressions.MemberExpression memberExp)
0x1119  ldarg.1
0x111a  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<string> Microsoft.Crm.Common.RepositoryQuery::get_PropertiesToReturn()
0x111f  ldloc.2
0x1120  callvirt instance class [mscorlib]System.Reflection.MemberInfo [System.Core]System.Linq.Expressions.MemberExpression::get_Member()
0x1125  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x112a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x112f  ldloc.1
0x1130  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1135  brtrue.s loc_1105
0x1137  leave.s  loc_114E
0x1139  ldloc.1
0x113a  brfalse.s loc_1142
0x113c  ldloc.1
0x113d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1142  endfinally
0x1143  ldstr    aExpressionWasN_0// "Expression was not either MemberAccess "...
0x1148  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x114d  throw
0x114e  ret
```
