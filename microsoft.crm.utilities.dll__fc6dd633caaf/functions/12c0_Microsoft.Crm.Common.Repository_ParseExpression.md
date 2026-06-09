# Microsoft.Crm.Common.Repository::ParseExpression

- ea: `0x12c0`
- end: `0x143f`
- name: `Microsoft.Crm.Common.Repository::ParseExpression`
- size: `383`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xd60`
- `0xda0`
- `0x12c0`
- `0x1600`

## callees

- `0x12c0`
- `0x1440`
- `0x14d0`
- `0x15b0`
- `0x19d0`
- `0x1a60`

## string_xrefs

- `0x134b`: `Parameter member was found on both sides of the expression : `

## pseudocode

```c

```

## disassembly

```asm
0x12c0  ldarg.0
0x12c1  isinst   [System.Core]System.Linq.Expressions.BinaryExpression
0x12c6  stloc.0
0x12c7  ldarg.0
0x12c8  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x12cd  ldc.i4.3
0x12ce  bne.un.s loc_12EB
0x12d0  ldloc.0
0x12d1  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0x12d6  ldarg.1
0x12d7  ldarg.2
0x12d8  call     void Microsoft.Crm.Common.Repository::ParseExpression(class [System.Core]System.Linq.Expressions.Expression expression, class Microsoft.Crm.Common.RepositoryQuery query, class [mscorlib]System.Type expectedType)
0x12dd  ldloc.0
0x12de  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Right()
0x12e3  ldarg.1
0x12e4  ldarg.2
0x12e5  call     void Microsoft.Crm.Common.Repository::ParseExpression(class [System.Core]System.Linq.Expressions.Expression expression, class Microsoft.Crm.Common.RepositoryQuery query, class [mscorlib]System.Type expectedType)
0x12ea  ret
0x12eb  ldloc.0
0x12ec  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0x12f1  ldarg.2
0x12f2  ldloca.s 1
0x12f4  call     bool Microsoft.Crm.Common.Repository::IsParameterMember(class [System.Core]System.Linq.Expressions.Expression expression, class [mscorlib]System.Type expectedType, [out] class [System.Core]System.Linq.Expressions.MemberExpression& member)
0x12f9  stloc.3
0x12fa  ldloc.0
0x12fb  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Right()
0x1300  ldarg.2
0x1301  ldloca.s 2
0x1303  call     bool Microsoft.Crm.Common.Repository::IsParameterMember(class [System.Core]System.Linq.Expressions.Expression expression, class [mscorlib]System.Type expectedType, [out] class [System.Core]System.Linq.Expressions.MemberExpression& member)
0x1308  stloc.s  4
0x130a  ldloc.3
0x130b  brtrue.s loc_1345
0x130d  ldloc.s  4
0x130f  brtrue.s loc_1345
0x1311  ldloc.0
0x1312  call     bool Microsoft.Crm.Common.Repository::IsLiftToNullValueType(class [System.Core]System.Linq.Expressions.BinaryExpression binary)
0x1317  brfalse.s loc_132F
0x1319  ldstr    aParameterMembe// "Parameter member cannot be converted to"...
0x131e  ldarg.0
0x131f  callvirt instance string [mscorlib]System.Object::ToString()
0x1324  call     string [mscorlib]System.String::Concat(string, string)
0x1329  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x132e  throw
0x132f  ldstr    aParameterMembe_0// "Parameter member was not found in the e"...
0x1334  ldarg.0
0x1335  callvirt instance string [mscorlib]System.Object::ToString()
0x133a  call     string [mscorlib]System.String::Concat(string, string)
0x133f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1344  throw
0x1345  ldloc.3
0x1346  ldloc.s  4
0x1348  and
0x1349  brfalse.s loc_1361
0x134b  ldstr    aParameterMembe_1// "Parameter member was found on both side"...
0x1350  ldarg.0
0x1351  callvirt instance string [mscorlib]System.Object::ToString()
0x1356  call     string [mscorlib]System.String::Concat(string, string)
0x135b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1360  throw
0x1361  ldloc.3
0x1362  brtrue.s loc_1367
0x1364  ldloc.2
0x1365  br.s     loc_1368
0x1367  ldloc.1
0x1368  stloc.s  5
0x136a  ldloc.3
0x136b  brtrue.s loc_1375
0x136d  ldloc.0
0x136e  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0x1373  br.s     loc_137B
0x1375  ldloc.0
0x1376  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Right()
0x137b  call     object Microsoft.Crm.Common.Repository::EvaluateExpression(class [System.Core]System.Linq.Expressions.Expression expression)
0x1380  stloc.s  6
0x1382  ldc.i4.0
0x1383  stloc.s  7
0x1385  ldarg.0
0x1386  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x138b  stloc.s  8
0x138d  ldloc.s  8
0x138f  ldc.i4.s 0xD
0x1391  sub
0x1392  switch   loc_13C3, loc_13F9, loc_13E3, loc_13EE, loc_13F9, loc_13F9, loc_13F9, loc_13CD, loc_13D8
0x13bb  ldloc.s  8
0x13bd  ldc.i4.s 0x23
0x13bf  beq.s    loc_13C8
0x13c1  br.s     loc_13F9
0x13c3  ldc.i4.0
0x13c4  stloc.s  7
0x13c6  br.s     loc_141E
0x13c8  ldc.i4.5
0x13c9  stloc.s  7
0x13cb  br.s     loc_141E
0x13cd  ldloc.3
0x13ce  brtrue.s loc_13D3
0x13d0  ldc.i4.1
0x13d1  br.s     loc_13D4
0x13d3  ldc.i4.3
0x13d4  stloc.s  7
0x13d6  br.s     loc_141E
0x13d8  ldloc.3
0x13d9  brtrue.s loc_13DE
0x13db  ldc.i4.2
0x13dc  br.s     loc_13DF
0x13de  ldc.i4.4
0x13df  stloc.s  7
0x13e1  br.s     loc_141E
0x13e3  ldloc.3
0x13e4  brtrue.s loc_13E9
0x13e6  ldc.i4.3
0x13e7  br.s     loc_13EA
0x13e9  ldc.i4.1
0x13ea  stloc.s  7
0x13ec  br.s     loc_141E
0x13ee  ldloc.3
0x13ef  brtrue.s loc_13F4
0x13f1  ldc.i4.4
0x13f2  br.s     loc_13F5
0x13f4  ldc.i4.2
0x13f5  stloc.s  7
0x13f7  br.s     loc_141E
0x13f9  ldstr    aUnsupportedNod// "Unsupported NodeType : "
0x13fe  ldarg.0
0x13ff  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0x1404  box      [System.Core]System.Linq.Expressions.ExpressionType
0x1409  ldstr    aG// "G"
0x140e  call     instance string [mscorlib]System.Enum::ToString(string)
0x1413  call     string [mscorlib]System.String::Concat(string, string)
0x1418  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x141d  throw
0x141e  ldarg.1
0x141f  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Common.Specification> Microsoft.Crm.Common.RepositoryQuery::get_Specifications()
0x1424  ldloc.s  5
0x1426  callvirt instance class [mscorlib]System.Reflection.MemberInfo [System.Core]System.Linq.Expressions.MemberExpression::get_Member()
0x142b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1430  ldloc.s  7
0x1432  ldloc.s  6
0x1434  newobj   instance void Microsoft.Crm.Common.Specification::.ctor(string property, valuetype Microsoft.Crm.Common.ComparisonOperator op, object value)
0x1439  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Common.Specification>::Add(var<u1>)
0x143e  ret
```
