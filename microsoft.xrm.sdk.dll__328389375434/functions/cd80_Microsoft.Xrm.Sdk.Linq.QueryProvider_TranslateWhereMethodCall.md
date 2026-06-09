# Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateWhereMethodCall

- ea: `0xcd80`
- end: `0xd0e0`
- name: `Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateWhereMethodCall`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0xcb40`

## callees

- `0x7c20`
- `0x8f10`
- `0x8fc0`
- `0x8ff0`
- `0x9000`
- `0xc9a0`
- `0xcc70`
- `0xcd80`
- `0xd0e0`
- `0xd1b0`
- `0xd1e0`
- `0xd950`
- `0xdb10`
- `0xdea0`

## string_xrefs

- `0xce94`: `Compare`

## pseudocode

```c

```

## disassembly

```asm
0xcd80  ldnull
0xcd81  stloc.0
0xcd82  ldsfld   string[] Microsoft.Xrm.Sdk.Linq.QueryProvider::_supportedMethods
0xcd87  ldarg.1
0xcd88  callvirt instance class [mscorlib]System.Reflection.MethodInfo [System.Core]System.Linq.Expressions.MethodCallExpression::get_Method()
0xcd8d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xcd92  call     T0x2B000036
0xcd97  brfalse  loc_CE89
0xcd9c  ldarg.1
0xcd9d  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0xcda2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Count()
0xcda7  ldc.i4.1
0xcda8  bne.un   loc_CE89
0xcdad  ldarg.0
0xcdae  ldarg.1
0xcdaf  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MethodCallExpression::get_Object()
0xcdb4  ldstr    aWhere_0// "where"
0xcdb9  callvirt instance class [System.Core]System.Linq.Expressions.Expression Microsoft.Xrm.Sdk.Linq.QueryProvider::FindValidEntityExpression(class [System.Core]System.Linq.Expressions.Expression exp, [opt] string operation)
0xcdbe  stloc.1
0xcdbf  ldarg.0
0xcdc0  ldloc.1
0xcdc1  ldarg.s  4
0xcdc3  call     instance string Microsoft.Xrm.Sdk.Linq.QueryProvider::GetLinkEntityAlias(class [System.Core]System.Linq.Expressions.Expression expression, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class LinkLookup> getLinkLookup)
0xcdc8  stloc.2
0xcdc9  ldarg.0
0xcdca  ldloc.1
0xcdcb  ldc.i4.0
0xcdcc  ldloca.s 0
0xcdce  callvirt instance string Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateExpressionToAttributeName(class [System.Core]System.Linq.Expressions.Expression exp, bool isSelectExpression, [out] string& alias)
0xcdd3  stloc.3
0xcdd4  ldarg.0
0xcdd5  ldarg.1
0xcdd6  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0xcddb  ldc.i4.0
0xcddc  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Item(!!T0)
0xcde1  ldc.i4.0
0xcde2  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xcde7  call     instance object Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateExpressionToConditionValue(class [System.Core]System.Linq.Expressions.Expression exp, class [System.Core]System.Linq.Expressions.ParameterExpression[] parameters)
0xcdec  stloc.s  4
0xcdee  ldarg.s  5
0xcdf0  brfalse.s loc_CE41
0xcdf2  ldarg.s  5
0xcdf4  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0xcdf9  ldc.i4.s 0x23
0xcdfb  bne.un.s loc_CE04
0xcdfd  ldarg.s  6
0xcdff  ldc.i4.0
0xce00  ceq
0xce02  starg.s  6
0xce04  ldarg.s  5
0xce06  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0xce0b  ldc.i4.s 0xD
0xce0d  beq.s    loc_CE1A
0xce0f  ldarg.s  5
0xce11  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0xce16  ldc.i4.s 0x23
0xce18  bne.un.s loc_CE41
0xce1a  ldarg.0
0xce1b  ldarg.s  5
0xce1d  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Right()
0xce22  ldc.i4.0
0xce23  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xce28  call     instance object Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateExpressionToConditionValue(class [System.Core]System.Linq.Expressions.Expression exp, class [System.Core]System.Linq.Expressions.ParameterExpression[] parameters)
0xce2d  ldc.i4.0
0xce2e  box      [mscorlib]System.Boolean
0xce33  call     bool [mscorlib]System.Object::Equals(object, object)
0xce38  brfalse.s loc_CE41
0xce3a  ldarg.s  6
0xce3c  ldc.i4.0
0xce3d  ceq
0xce3f  starg.s  6
0xce41  ldarg.0
0xce42  ldarg.1
0xce43  ldloc.3
0xce44  ldloc.s  4
0xce46  call     instance class Microsoft.Xrm.Sdk.Query.ConditionExpression Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateConditionMethodExpression(class [System.Core]System.Linq.Expressions.MethodCallExpression mce, string attributeName, object value)
0xce4b  stloc.s  5
0xce4d  ldloc.s  5
0xce4f  ldloc.2
0xce50  callvirt instance void Microsoft.Xrm.Sdk.Query.ConditionExpression::set_EntityName(string value)
0xce55  ldloc.s  5
0xce57  ldarg.s  6
0xce59  brtrue.s loc_CE64
0xce5b  ldloc.s  5
0xce5d  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Operator()
0xce62  br.s     loc_CE71
0xce64  ldarg.0
0xce65  ldloc.s  5
0xce67  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Operator()
0xce6c  call     instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Linq.QueryProvider::NegateOperator(valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator op)
0xce71  callvirt instance void Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator value)
0xce76  ldarg.0
0xce77  ldarg.0
0xce78  ldloc.1
0xce79  ldarg.2
0xce7a  ldarg.3
0xce7b  call     instance class FilterExpressionWrapper Microsoft.Xrm.Sdk.Linq.QueryProvider::GetFilter(class [System.Core]System.Linq.Expressions.Expression entityExpression, class FilterExpressionWrapper parentFilter, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class FilterExpressionWrapper> getFilter)
0xce80  ldloc.s  5
0xce82  ldloc.0
0xce83  call     instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::AddCondition(class FilterExpressionWrapper filter, class Microsoft.Xrm.Sdk.Query.ConditionExpression condition, string alias)
0xce88  ret
0xce89  ldarg.1
0xce8a  callvirt instance class [mscorlib]System.Reflection.MethodInfo [System.Core]System.Linq.Expressions.MethodCallExpression::get_Method()
0xce8f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xce94  ldstr    aCompare// "Compare"
0xce99  call     bool [mscorlib]System.String::op_Equality(string, string)
0xce9e  brfalse  loc_CF86
0xcea3  ldarg.1
0xcea4  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0xcea9  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Count()
0xceae  ldc.i4.2
0xceaf  bne.un   loc_CF86
0xceb4  ldarg.0
0xceb5  ldarg.1
0xceb6  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0xcebb  ldc.i4.0
0xcebc  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Item(!!T0)
0xcec1  ldstr    aWhere_0// "where"
0xcec6  callvirt instance class [System.Core]System.Linq.Expressions.Expression Microsoft.Xrm.Sdk.Linq.QueryProvider::FindValidEntityExpression(class [System.Core]System.Linq.Expressions.Expression exp, [opt] string operation)
0xcecb  stloc.s  6
0xcecd  ldarg.0
0xcece  ldloc.s  6
0xced0  ldarg.s  4
0xced2  call     instance string Microsoft.Xrm.Sdk.Linq.QueryProvider::GetLinkEntityAlias(class [System.Core]System.Linq.Expressions.Expression expression, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class LinkLookup> getLinkLookup)
0xced7  stloc.s  7
0xced9  ldarg.0
0xceda  ldloc.s  6
0xcedc  ldc.i4.0
0xcedd  ldloca.s 0
0xcedf  callvirt instance string Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateExpressionToAttributeName(class [System.Core]System.Linq.Expressions.Expression exp, bool isSelectExpression, [out] string& alias)
0xcee4  stloc.s  8
0xcee6  ldarg.0
0xcee7  ldarg.1
0xcee8  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0xceed  ldc.i4.1
0xceee  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Item(!!T0)
0xcef3  ldc.i4.0
0xcef4  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xcef9  call     instance object Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateExpressionToConditionValue(class [System.Core]System.Linq.Expressions.Expression exp, class [System.Core]System.Linq.Expressions.ParameterExpression[] parameters)
0xcefe  stloc.s  9
0xcf00  ldarg.s  5
0xcf02  brfalse  loc_D0DF
0xcf07  ldarg.0
0xcf08  ldarg.s  5
0xcf0a  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Right()
0xcf0f  ldc.i4.0
0xcf10  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xcf15  call     instance object Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateExpressionToConditionValue(class [System.Core]System.Linq.Expressions.Expression exp, class [System.Core]System.Linq.Expressions.ParameterExpression[] parameters)
0xcf1a  ldc.i4.0
0xcf1b  box      [mscorlib]System.Int32
0xcf20  call     bool [mscorlib]System.Object::Equals(object, object)
0xcf25  brfalse  loc_D0DF
0xcf2a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator> Microsoft.Xrm.Sdk.Linq.QueryProvider::_conditionLookup
0xcf2f  ldarg.s  5
0xcf31  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0xcf36  ldloca.s 0xA
0xcf38  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::TryGetValue(var<u1>, !!T0)
0xcf3d  brfalse  loc_D0DF
0xcf42  ldloc.s  7
0xcf44  ldloc.s  8
0xcf46  ldloc.s  0xA
0xcf48  ldloc.s  9
0xcf4a  newobj   instance void Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string entityName, string attributeName, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0xcf4f  stloc.s  0xB
0xcf51  ldloc.s  0xB
0xcf53  ldarg.s  6
0xcf55  brtrue.s loc_CF60
0xcf57  ldloc.s  0xB
0xcf59  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Operator()
0xcf5e  br.s     loc_CF6D
0xcf60  ldarg.0
0xcf61  ldloc.s  0xB
0xcf63  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Operator()
0xcf68  call     instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Linq.QueryProvider::NegateOperator(valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator op)
0xcf6d  callvirt instance void Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator value)
0xcf72  ldarg.0
0xcf73  ldarg.0
0xcf74  ldloc.s  6
0xcf76  ldarg.2
0xcf77  ldarg.3
0xcf78  call     instance class FilterExpressionWrapper Microsoft.Xrm.Sdk.Linq.QueryProvider::GetFilter(class [System.Core]System.Linq.Expressions.Expression entityExpression, class FilterExpressionWrapper parentFilter, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class FilterExpressionWrapper> getFilter)
0xcf7d  ldloc.s  0xB
0xcf7f  ldloc.0
0xcf80  call     instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::AddCondition(class FilterExpressionWrapper filter, class Microsoft.Xrm.Sdk.Query.ConditionExpression condition, string alias)
0xcf85  ret
0xcf86  ldarg.1
0xcf87  callvirt instance class [mscorlib]System.Reflection.MethodInfo [System.Core]System.Linq.Expressions.MethodCallExpression::get_Method()
0xcf8c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xcf91  ldstr    aLike// "Like"
0xcf96  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcf9b  brfalse  loc_D040
0xcfa0  ldarg.1
0xcfa1  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0xcfa6  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Count()
0xcfab  ldc.i4.2
0xcfac  bne.un   loc_D040
0xcfb1  ldarg.0
0xcfb2  ldarg.1
0xcfb3  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0xcfb8  ldc.i4.0
0xcfb9  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Item(!!T0)
0xcfbe  ldstr    aWhere_0// "where"
0xcfc3  callvirt instance class [System.Core]System.Linq.Expressions.Expression Microsoft.Xrm.Sdk.Linq.QueryProvider::FindValidEntityExpression(class [System.Core]System.Linq.Expressions.Expression exp, [opt] string operation)
0xcfc8  stloc.s  0xC
0xcfca  ldarg.0
0xcfcb  ldloc.s  0xC
0xcfcd  ldarg.s  4
0xcfcf  call     instance string Microsoft.Xrm.Sdk.Linq.QueryProvider::GetLinkEntityAlias(class [System.Core]System.Linq.Expressions.Expression expression, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class LinkLookup> getLinkLookup)
0xcfd4  stloc.s  0xD
0xcfd6  ldarg.0
0xcfd7  ldloc.s  0xC
0xcfd9  ldc.i4.0
0xcfda  ldloca.s 0
0xcfdc  callvirt instance string Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateExpressionToAttributeName(class [System.Core]System.Linq.Expressions.Expression exp, bool isSelectExpression, [out] string& alias)
0xcfe1  stloc.s  0xE
0xcfe3  ldarg.0
0xcfe4  ldarg.1
0xcfe5  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0xcfea  ldc.i4.1
0xcfeb  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Item(!!T0)
0xcff0  ldc.i4.0
0xcff1  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xcff6  call     instance object Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateExpressionToConditionValue(class [System.Core]System.Linq.Expressions.Expression exp, class [System.Core]System.Linq.Expressions.ParameterExpression[] parameters)
0xcffb  stloc.s  0xF
0xcffd  ldloc.s  0xD
0xcfff  ldloc.s  0xE
0xd001  ldc.i4.6
0xd002  ldloc.s  0xF
0xd004  newobj   instance void Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string entityName, string attributeName, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0xd009  stloc.s  0x10
0xd00b  ldloc.s  0x10
0xd00d  ldarg.s  6
0xd00f  brtrue.s loc_D01A
0xd011  ldloc.s  0x10
0xd013  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Operator()
0xd018  br.s     loc_D027
0xd01a  ldarg.0
0xd01b  ldloc.s  0x10
0xd01d  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Operator()
0xd022  call     instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Linq.QueryProvider::NegateOperator(valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator op)
0xd027  callvirt instance void Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator value)
0xd02c  ldarg.0
0xd02d  ldarg.0
0xd02e  ldloc.s  0xC
0xd030  ldarg.2
0xd031  ldarg.3
0xd032  call     instance class FilterExpressionWrapper Microsoft.Xrm.Sdk.Linq.QueryProvider::GetFilter(class [System.Core]System.Linq.Expressions.Expression entityExpression, class FilterExpressionWrapper parentFilter, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class FilterExpressionWrapper> getFilter)
0xd037  ldloc.s  0x10
0xd039  ldloc.0
0xd03a  call     instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::AddCondition(class FilterExpressionWrapper filter, class Microsoft.Xrm.Sdk.Query.ConditionExpression condition, string alias)
0xd03f  ret
0xd040  ldarg.s  5
0xd042  brfalse.s loc_D05A
0xd044  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator> Microsoft.Xrm.Sdk.Linq.QueryProvider::_booleanLookup
0xd049  ldarg.s  5
0xd04b  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0xd050  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator>::ContainsKey(var<u1>)
0xd055  brfalse  loc_D0DF
0xd05a  ldarg.1
0xd05b  callvirt instance class [mscorlib]System.Type [System.Core]System.Linq.Expressions.Expression::get_Type()
0xd060  call     class [mscorlib]System.Type Microsoft.Xrm.Sdk.TypeExtensions::GetUnderlyingType(class [mscorlib]System.Type type)
0xd065  ldtoken  [mscorlib]System.Boolean
0xd06a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd06f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xd074  brfalse.s loc_D0DF
0xd076  ldarg.0
0xd077  ldarg.1
0xd078  ldstr    aWhere_0// "where"
0xd07d  callvirt instance class [System.Core]System.Linq.Expressions.Expression Microsoft.Xrm.Sdk.Linq.QueryProvider::FindValidEntityExpression(class [System.Core]System.Linq.Expressions.Expression exp, [opt] string operation)
0xd082  stloc.s  0x11
0xd084  ldarg.0
0xd085  ldloc.s  0x11
0xd087  ldarg.s  4
0xd089  call     instance string Microsoft.Xrm.Sdk.Linq.QueryProvider::GetLinkEntityAlias(class [System.Core]System.Linq.Expressions.Expression expression, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class LinkLookup> getLinkLookup)
0xd08e  ldarg.0
0xd08f  ldloc.s  0x11
0xd091  ldc.i4.0
0xd092  ldloca.s 0
0xd094  callvirt instance string Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateExpressionToAttributeName(class [System.Core]System.Linq.Expressions.Expression exp, bool isSelectExpression, [out] string& alias)
0xd099  stloc.s  0x12
0xd09b  ldloc.s  0x12
0xd09d  ldc.i4.0
0xd09e  ldc.i4.1
0xd09f  box      [mscorlib]System.Boolean
0xd0a4  newobj   instance void Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string entityName, string attributeName, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0xd0a9  stloc.s  0x13
0xd0ab  ldloc.s  0x13
0xd0ad  ldarg.s  6
0xd0af  brtrue.s loc_D0BA
0xd0b1  ldloc.s  0x13
0xd0b3  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Operator()
0xd0b8  br.s     loc_D0C7
0xd0ba  ldarg.0
0xd0bb  ldloc.s  0x13
0xd0bd  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Operator()
0xd0c2  call     instance valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator Microsoft.Xrm.Sdk.Linq.QueryProvider::NegateOperator(valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator op)
0xd0c7  callvirt instance void Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator value)
0xd0cc  ldarg.0
0xd0cd  ldarg.0
0xd0ce  ldloc.s  0x11
  ... truncated ...
```
