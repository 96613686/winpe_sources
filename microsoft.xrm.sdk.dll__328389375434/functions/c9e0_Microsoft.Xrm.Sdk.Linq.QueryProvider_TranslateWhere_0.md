# Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateWhere_0

- ea: `0xc9e0`
- end: `0xcb0d`
- name: `Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateWhere_0`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0xcb40`

## callees

- `0x9100`
- `0x9110`
- `0x9210`
- `0xc9b0`
- `0xc9e0`
- `0xcb10`
- `0xcb40`
- `0xcca0`
- `0xd1e0`
- `0xd1f0`
- `0xdc10`
- `0x22530`
- `0x22550`
- `0x22570`

## string_xrefs

- `0xcac4`: `Compare`

## pseudocode

```c

```

## disassembly

```asm
0xc9e0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator> Microsoft.Xrm.Sdk.Linq.QueryProvider::_booleanLookup
0xc9e5  ldarg.2
0xc9e6  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0xc9eb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator>::ContainsKey(var<u1>)
0xc9f0  brfalse  loc_CA8D
0xc9f5  ldarg.0
0xc9f6  ldarg.2
0xc9f7  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0xc9fc  call     instance class [System.Core]System.Linq.Expressions.Expression Microsoft.Xrm.Sdk.Linq.QueryProvider::FindEntityExpression(class [System.Core]System.Linq.Expressions.Expression exp)
0xca01  stloc.0
0xca02  ldarg.0
0xca03  ldloc.0
0xca04  ldarg.3
0xca05  ldarg.s  4
0xca07  call     instance class FilterExpressionWrapper Microsoft.Xrm.Sdk.Linq.QueryProvider::GetFilter(class [System.Core]System.Linq.Expressions.Expression entityExpression, class FilterExpressionWrapper parentFilter, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class FilterExpressionWrapper> getFilter)
0xca0c  starg.s  3
0xca0e  ldarg.3
0xca0f  callvirt instance class Microsoft.Xrm.Sdk.Query.FilterExpression FilterExpressionWrapper::get_Filter()
0xca14  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator> Microsoft.Xrm.Sdk.Linq.QueryProvider::_booleanLookup
0xca19  ldarg.2
0xca1a  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0xca1f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator>::get_Item(void)
0xca24  callvirt instance class Microsoft.Xrm.Sdk.Query.FilterExpression Microsoft.Xrm.Sdk.Query.FilterExpression::AddFilter(valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator logicalOperator)
0xca29  ldarg.3
0xca2a  callvirt instance string FilterExpressionWrapper::get_Alias()
0xca2f  newobj   instance void FilterExpressionWrapper::.ctor(class Microsoft.Xrm.Sdk.Query.FilterExpression filter, string alias)
0xca34  stloc.1
0xca35  ldloc.1
0xca36  callvirt instance class Microsoft.Xrm.Sdk.Query.FilterExpression FilterExpressionWrapper::get_Filter()
0xca3b  ldarg.s  6
0xca3d  brtrue.s loc_CA4C
0xca3f  ldloc.1
0xca40  callvirt instance class Microsoft.Xrm.Sdk.Query.FilterExpression FilterExpressionWrapper::get_Filter()
0xca45  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator Microsoft.Xrm.Sdk.Query.FilterExpression::get_FilterOperator()
0xca4a  br.s     loc_CA5D
0xca4c  ldarg.0
0xca4d  ldloc.1
0xca4e  callvirt instance class Microsoft.Xrm.Sdk.Query.FilterExpression FilterExpressionWrapper::get_Filter()
0xca53  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator Microsoft.Xrm.Sdk.Query.FilterExpression::get_FilterOperator()
0xca58  call     instance valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator Microsoft.Xrm.Sdk.Linq.QueryProvider::NegateOperator(valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator op)
0xca5d  callvirt instance void Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype Microsoft.Xrm.Sdk.Query.LogicalOperator value)
0xca62  ldarg.0
0xca63  ldarg.1
0xca64  ldarg.2
0xca65  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0xca6a  ldloc.1
0xca6b  ldarg.s  4
0xca6d  ldarg.s  5
0xca6f  ldarg.2
0xca70  ldarg.s  6
0xca72  callvirt instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateWhereBoolean(string parameterName, class [System.Core]System.Linq.Expressions.Expression exp, class FilterExpressionWrapper parentFilter, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class FilterExpressionWrapper> getFilter, class [mscorlib]System.Collections.Generic.List`1<class LinkLookup> linkLookups, class [System.Core]System.Linq.Expressions.BinaryExpression parent, bool negate)
0xca77  ldarg.0
0xca78  ldarg.1
0xca79  ldarg.2
0xca7a  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Right()
0xca7f  ldloc.1
0xca80  ldarg.s  4
0xca82  ldarg.s  5
0xca84  ldarg.2
0xca85  ldarg.s  6
0xca87  callvirt instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateWhereBoolean(string parameterName, class [System.Core]System.Linq.Expressions.Expression exp, class FilterExpressionWrapper parentFilter, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class FilterExpressionWrapper> getFilter, class [mscorlib]System.Collections.Generic.List`1<class LinkLookup> linkLookups, class [System.Core]System.Linq.Expressions.BinaryExpression parent, bool negate)
0xca8c  ret
0xca8d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator> Microsoft.Xrm.Sdk.Linq.QueryProvider::_conditionLookup
0xca92  ldarg.2
0xca93  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0xca98  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Core]System.Linq.Expressions.ExpressionType, valuetype Microsoft.Xrm.Sdk.Query.ConditionOperator>::ContainsKey(var<u1>)
0xca9d  brfalse.s loc_CB0C
0xca9f  ldarg.s  6
0xcaa1  stloc.2
0xcaa2  ldarg.0
0xcaa3  ldarg.2
0xcaa4  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.BinaryExpression::get_Left()
0xcaa9  ldloca.s 2
0xcaab  callvirt instance class [System.Core]System.Linq.Expressions.Expression Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateWhere(class [System.Core]System.Linq.Expressions.Expression exp, bool& negate)
0xcab0  isinst   [System.Core]System.Linq.Expressions.MethodCallExpression
0xcab5  stloc.3
0xcab6  ldloc.3
0xcab7  brfalse.s loc_CAF7
0xcab9  ldloc.3
0xcaba  callvirt instance class [mscorlib]System.Reflection.MethodInfo [System.Core]System.Linq.Expressions.MethodCallExpression::get_Method()
0xcabf  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xcac4  ldstr    aCompare// "Compare"
0xcac9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcace  brtrue.s loc_CAE7
0xcad0  ldsfld   string[] Microsoft.Xrm.Sdk.Linq.QueryProvider::_supportedMethods
0xcad5  ldloc.3
0xcad6  callvirt instance class [mscorlib]System.Reflection.MethodInfo [System.Core]System.Linq.Expressions.MethodCallExpression::get_Method()
0xcadb  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xcae0  call     T0x2B000036
0xcae5  brfalse.s loc_CAF7
0xcae7  ldarg.0
0xcae8  ldarg.1
0xcae9  ldloc.3
0xcaea  ldarg.3
0xcaeb  ldarg.s  4
0xcaed  ldarg.s  5
0xcaef  ldarg.2
0xcaf0  ldloc.2
0xcaf1  callvirt instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateWhereBoolean(string parameterName, class [System.Core]System.Linq.Expressions.Expression exp, class FilterExpressionWrapper parentFilter, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class FilterExpressionWrapper> getFilter, class [mscorlib]System.Collections.Generic.List`1<class LinkLookup> linkLookups, class [System.Core]System.Linq.Expressions.BinaryExpression parent, bool negate)
0xcaf6  ret
0xcaf7  ldarg.0
0xcaf8  ldarg.2
0xcaf9  ldarg.3
0xcafa  ldarg.s  4
0xcafc  ldarg.0
0xcafd  ldarg.1
0xcafe  ldarg.s  5
0xcb00  callvirt instance class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class LinkLookup> Microsoft.Xrm.Sdk.Linq.QueryProvider::GetLinkLookup(string parameterName, class [mscorlib]System.Collections.Generic.List`1<class LinkLookup> linkLookups)
0xcb05  ldarg.s  6
0xcb07  call     instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::TranslateWhereCondition(class [System.Core]System.Linq.Expressions.BinaryExpression be, class FilterExpressionWrapper parentFilter, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class FilterExpressionWrapper> getFilter, class [mscorlib]System.Func`2<class [System.Core]System.Linq.Expressions.Expression, class LinkLookup> getLinkLookup, bool negate)
0xcb0c  ret
```
