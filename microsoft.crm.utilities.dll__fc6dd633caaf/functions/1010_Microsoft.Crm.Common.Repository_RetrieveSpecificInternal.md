# Microsoft.Crm.Common.Repository::RetrieveSpecificInternal

- ea: `0x1010`
- end: `0x1096`
- name: `Microsoft.Crm.Common.Repository::RetrieveSpecificInternal`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x610`
- `0x630`
- `0x1010`
- `0x10a0`
- `0x11b0`
- `0x19a0`
- `0x19d0`
- `0x1a60`

## pseudocode

```c

```

## disassembly

```asm
0x1010  ldarg.2
0x1011  brtrue.s loc_101E
0x1013  ldstr    aSelectorexpres// "selectorExpression"
0x1018  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x101d  throw
0x101e  newobj   instance void Microsoft.Crm.Common.RepositoryQuery::.ctor()
0x1023  stloc.0
0x1024  ldtoken  mvar<u1>
0x1029  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x102e  stloc.1
0x102f  ldarg.0
0x1030  ldloc.1
0x1031  call     instance string Microsoft.Crm.Common.Repository::InferPrimaryKeyName(class [mscorlib]System.Type objectType)
0x1036  stloc.2
0x1037  ldloc.0
0x1038  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Common.Specification> Microsoft.Crm.Common.RepositoryQuery::get_Specifications()
0x103d  ldloc.2
0x103e  ldc.i4.0
0x103f  ldarg.1
0x1040  newobj   instance void Microsoft.Crm.Common.Specification::.ctor(string property, valuetype Microsoft.Crm.Common.ComparisonOperator op, object value)
0x1045  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Common.Specification>::Add(var<u1>)
0x104a  ldarg.2
0x104b  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.ParameterExpression> [System.Core]System.Linq.Expressions.LambdaExpression::get_Parameters()
0x1050  ldc.i4.0
0x1051  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.ParameterExpression>::get_Item(!!T0)
0x1056  callvirt instance string [System.Core]System.Linq.Expressions.ParameterExpression::get_Name()
0x105b  stloc.3
0x105c  ldarg.2
0x105d  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.LambdaExpression::get_Body()
0x1062  ldloc.0
0x1063  ldloc.1
0x1064  ldloc.3
0x1065  call     void Microsoft.Crm.Common.Repository::ParseSelectorExpression(class [System.Core]System.Linq.Expressions.Expression selBody, class Microsoft.Crm.Common.RepositoryQuery query, class [mscorlib]System.Type objectType, string inputParameterName)
0x106a  ldarg.0
0x106b  ldloc.0
0x106c  ldarg.3
0x106d  call     T0x2B000003
0x1072  call     T0x2B00000A
0x1077  stloc.s  4
0x1079  ldarg.2
0x107a  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.LambdaExpression::get_Body()
0x107f  ldloc.s  4
0x1081  box      mvar<u1>
0x1086  call     class [System.Core]System.Linq.Expressions.Expression Microsoft.Crm.Common.ExpressionUtility::ReplaceArgument(class [System.Core]System.Linq.Expressions.Expression expression, object argumentValue)
0x108b  call     object Microsoft.Crm.Common.ExpressionUtility::EvaluateExpression(class [System.Core]System.Linq.Expressions.Expression expression)
0x1090  unbox.any mvar<u1>
0x1095  ret
```
