# Microsoft.Crm.Common.Repository::UpdateSpecificInternal

- ea: `0xf40`
- end: `0x100d`
- name: `Microsoft.Crm.Common.Repository::UpdateSpecificInternal`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0xf40`
- `0x1150`
- `0x11b0`
- `0x1e50`

## pseudocode

```c

```

## disassembly

```asm
0xf40  ldtoken  mvar<u1>
0xf45  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf4a  stloc.0
0xf4b  ldarg.2
0xf4c  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.LambdaExpression::get_Body()
0xf51  isinst   [System.Core]System.Linq.Expressions.MemberExpression
0xf56  stloc.1
0xf57  ldarg.2
0xf58  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.LambdaExpression::get_Body()
0xf5d  callvirt instance valuetype [System.Core]System.Linq.Expressions.ExpressionType [System.Core]System.Linq.Expressions.Expression::get_NodeType()
0xf62  ldc.i4.s 0xA
0xf64  bne.un.s loc_F7C
0xf66  ldarg.2
0xf67  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.LambdaExpression::get_Body()
0xf6c  isinst   [System.Core]System.Linq.Expressions.UnaryExpression
0xf71  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.UnaryExpression::get_Operand()
0xf76  isinst   [System.Core]System.Linq.Expressions.MemberExpression
0xf7b  stloc.1
0xf7c  ldloc.1
0xf7d  brtrue.s loc_F8A
0xf7f  ldstr    aExpressionWasN// "Expression was not a MemberExpression"
0xf84  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xf89  throw
0xf8a  ldarg.2
0xf8b  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.ParameterExpression> [System.Core]System.Linq.Expressions.LambdaExpression::get_Parameters()
0xf90  ldc.i4.0
0xf91  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.ParameterExpression>::get_Item(!!T0)
0xf96  callvirt instance string [System.Core]System.Linq.Expressions.ParameterExpression::get_Name()
0xf9b  stloc.2
0xf9c  ldloc.0
0xf9d  ldloc.2
0xf9e  ldloc.1
0xf9f  call     void Microsoft.Crm.Common.Repository::VerifyPropertySelectorMemberExpression(class [mscorlib]System.Type objectType, string inputParameterName, class [System.Core]System.Linq.Expressions.MemberExpression memberExp)
0xfa4  ldloc.1
0xfa5  callvirt instance class [mscorlib]System.Reflection.MemberInfo [System.Core]System.Linq.Expressions.MemberExpression::get_Member()
0xfaa  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xfaf  stloc.3
0xfb0  call     T0x2B000009
0xfb5  stloc.s  4
0xfb7  ldloc.0
0xfb8  ldloc.3
0xfb9  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0xfbe  ldloc.s  4
0xfc0  box      mvar<u1>
0xfc5  ldarg.3
0xfc6  box      mvar<u1>
0xfcb  ldnull
0xfcc  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object, object[])
0xfd1  ldarg.0
0xfd2  ldloc.0
0xfd3  call     instance string Microsoft.Crm.Common.Repository::InferPrimaryKeyName(class [mscorlib]System.Type objectType)
0xfd8  stloc.s  5
0xfda  ldloc.0
0xfdb  ldloc.s  5
0xfdd  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0xfe2  ldloc.s  4
0xfe4  box      mvar<u1>
0xfe9  ldarg.1
0xfea  ldnull
0xfeb  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object, object[])
0xff0  ldarg.0
0xff1  call     T0x2B000004
0xff6  callvirt instance class Microsoft.Crm.Common.IDataProvider TypeInformation::get_DataProvider()
0xffb  ldloc.s  4
0xffd  ldc.i4.1
0xffe  newarr   [mscorlib]System.String
0x1003  dup
0x1004  ldc.i4.0
0x1005  ldloc.3
0x1006  stelem.ref
0x1007  callvirt T0x2B000005
0x100c  ret
```
