# Microsoft.Crm.Workflow.BulkMailWorkflow::CreateWorkflow

- ea: `0xbb0`
- end: `0xe24`
- name: `Microsoft.Crm.Workflow.BulkMailWorkflow::CreateWorkflow`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x20`

## callees

- `0x3020`
- `0x3140`
- `0x3160`
- `0x3180`
- `0x31a0`
- `0x33e0`
- `0x3400`
- `0x3420`
- `0x36e0`

## pseudocode

```c

```

## disassembly

```asm
0xbb0  newobj   instance void <>c__DisplayClass0_0::.ctor()
0xbb5  stloc.0
0xbb6  ldloc.0
0xbb7  ldstr    aCounter// "counter"
0xbbc  ldc.i4.0
0xbbd  newobj   instance void class [System.Activities]System.Activities.Variable`1<int32>::.ctor(string, var<u1>)
0xbc2  stfld    class [System.Activities]System.Activities.Variable`1<int32> <>c__DisplayClass0_0::count
0xbc7  ldloc.0
0xbc8  ldstr    aBulkmailexpand// "bulkMailExpandMaxCount"
0xbcd  ldc.i4.0
0xbce  newobj   instance void class [System.Activities]System.Activities.Variable`1<int32>::.ctor(string, var<u1>)
0xbd3  stfld    class [System.Activities]System.Activities.Variable`1<int32> <>c__DisplayClass0_0::bulkMailExpandMaxCount
0xbd8  ldstr    aEntityname// "entityName"
0xbdd  newobj   instance void class [System.Activities]System.Activities.Variable`1<string>::.ctor(string)
0xbe2  stloc.1
0xbe3  ldstr    aFailures// "failures"
0xbe8  newobj   instance void class [System.Activities]System.Activities.Variable`1<int32>::.ctor(string)
0xbed  stloc.2
0xbee  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0xbf3  stloc.3
0xbf4  ldloc.3
0xbf5  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0xbfa  ldloc.0
0xbfb  ldfld    class [System.Activities]System.Activities.Variable`1<int32> <>c__DisplayClass0_0::count
0xc00  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::Add(var<u1>)
0xc05  ldloc.3
0xc06  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0xc0b  ldloc.0
0xc0c  ldfld    class [System.Activities]System.Activities.Variable`1<int32> <>c__DisplayClass0_0::bulkMailExpandMaxCount
0xc11  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::Add(var<u1>)
0xc16  ldloc.3
0xc17  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0xc1c  ldloc.1
0xc1d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::Add(var<u1>)
0xc22  ldloc.3
0xc23  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0xc28  ldloc.2
0xc29  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::Add(var<u1>)
0xc2e  ldloc.3
0xc2f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0xc34  newobj   instance void Microsoft.Crm.Workflow.Activities.BulkMailExpand::.ctor()
0xc39  stloc.s  4
0xc3b  ldloc.s  4
0xc3d  ldloc.0
0xc3e  ldfld    class [System.Activities]System.Activities.Variable`1<int32> <>c__DisplayClass0_0::bulkMailExpandMaxCount
0xc43  call     class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.OutArgument`1<int32>::op_Implicit(!!T0)
0xc48  callvirt instance void Microsoft.Crm.Workflow.Activities.BulkMailExpand::set_MaxCount(class [System.Activities]System.Activities.OutArgument`1<int32> value)
0xc4d  ldloc.s  4
0xc4f  ldloc.1
0xc50  call     class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.OutArgument`1<string>::op_Implicit(!!T0)
0xc55  callvirt instance void Microsoft.Crm.Workflow.Activities.BulkMailExpand::set_EntityName(class [System.Activities]System.Activities.OutArgument`1<string> value)
0xc5a  ldloc.s  4
0xc5c  ldtoken  [System.Activities]System.Activities.ActivityContext
0xc61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc66  ldstr    aEnv// "env"
0xc6b  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xc70  stloc.s  6
0xc72  ldloc.0
0xc73  ldtoken  <>c__DisplayClass0_0
0xc78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc7d  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0xc82  ldtoken  class [System.Activities]System.Activities.Variable`1<int32> <>c__DisplayClass0_0::count
0xc87  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0xc8c  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0xc91  ldtoken  instance var<u1> class [System.Activities]System.Activities.Variable`1<int32>::Get(!!T0)
0xc96  ldtoken  class [System.Activities]System.Activities.Variable`1<int32>
0xc9b  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle, valuetype [mscorlib]System.RuntimeTypeHandle)
0xca0  castclass [mscorlib]System.Reflection.MethodInfo
0xca5  ldc.i4.1
0xca6  newarr   [System.Core]System.Linq.Expressions.Expression
0xcab  dup
0xcac  ldc.i4.0
0xcad  ldloc.s  6
0xcaf  stelem.ref
0xcb0  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0xcb5  ldloc.0
0xcb6  ldtoken  <>c__DisplayClass0_0
0xcbb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcc0  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0xcc5  ldtoken  class [System.Activities]System.Activities.Variable`1<int32> <>c__DisplayClass0_0::bulkMailExpandMaxCount
0xcca  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0xccf  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0xcd4  ldtoken  instance var<u1> class [System.Activities]System.Activities.Variable`1<int32>::Get(!!T0)
0xcd9  ldtoken  class [System.Activities]System.Activities.Variable`1<int32>
0xcde  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle, valuetype [mscorlib]System.RuntimeTypeHandle)
0xce3  castclass [mscorlib]System.Reflection.MethodInfo
0xce8  ldc.i4.1
0xce9  newarr   [System.Core]System.Linq.Expressions.Expression
0xcee  dup
0xcef  ldc.i4.0
0xcf0  ldloc.s  6
0xcf2  stelem.ref
0xcf3  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0xcf8  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::LessThan(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression)
0xcfd  ldc.i4.1
0xcfe  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xd03  dup
0xd04  ldc.i4.0
0xd05  ldloc.s  6
0xd07  stelem.ref
0xd08  call     T0x2B000001
0xd0d  newobj   instance void [System.Activities]System.Activities.Statements.While::.ctor(class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<class [System.Activities]System.Activities.ActivityContext, bool>>)
0xd12  stloc.s  5
0xd14  ldloc.s  5
0xd16  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0xd1b  stloc.s  7
0xd1d  ldloc.s  7
0xd1f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0xd24  newobj   instance void Microsoft.Crm.Workflow.Activities.BulkMailItem::.ctor()
0xd29  dup
0xd2a  ldloc.1
0xd2b  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0xd30  callvirt instance void Microsoft.Crm.Workflow.Activities.BulkMailItem::set_EntityName(class [System.Activities]System.Activities.InArgument`1<string> value)
0xd35  dup
0xd36  ldloc.0
0xd37  ldfld    class [System.Activities]System.Activities.Variable`1<int32> <>c__DisplayClass0_0::count
0xd3c  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<int32>::op_Implicit(!!T0)
0xd41  callvirt instance void Microsoft.Crm.Workflow.Activities.BulkMailItem::set_Count(class [System.Activities]System.Activities.InArgument`1<int32> value)
0xd46  dup
0xd47  ldloc.2
0xd48  call     class [System.Activities]System.Activities.InOutArgument`1<var<u1>> class [System.Activities]System.Activities.InOutArgument`1<int32>::op_Implicit(!!T0)
0xd4d  callvirt instance void Microsoft.Crm.Workflow.Activities.BulkMailItem::set_Failures(class [System.Activities]System.Activities.InOutArgument`1<int32> value)
0xd52  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0xd57  ldloc.s  7
0xd59  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0xd5e  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<int32>::.ctor()
0xd63  stloc.s  8
0xd65  ldloc.s  8
0xd67  ldloc.0
0xd68  ldfld    class [System.Activities]System.Activities.Variable`1<int32> <>c__DisplayClass0_0::count
0xd6d  call     class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.OutArgument`1<int32>::op_Implicit(!!T0)
0xd72  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<int32>::set_To(class [System.Activities]System.Activities.OutArgument`1<var<u1>>)
0xd77  ldloc.s  8
0xd79  ldtoken  [System.Activities]System.Activities.ActivityContext
0xd7e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd83  ldstr    aEnv// "env"
0xd88  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xd8d  stloc.s  6
0xd8f  ldloc.0
0xd90  ldtoken  <>c__DisplayClass0_0
0xd95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd9a  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0xd9f  ldtoken  class [System.Activities]System.Activities.Variable`1<int32> <>c__DisplayClass0_0::count
0xda4  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0xda9  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0xdae  ldtoken  instance var<u1> class [System.Activities]System.Activities.Variable`1<int32>::Get(!!T0)
0xdb3  ldtoken  class [System.Activities]System.Activities.Variable`1<int32>
0xdb8  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle, valuetype [mscorlib]System.RuntimeTypeHandle)
0xdbd  castclass [mscorlib]System.Reflection.MethodInfo
0xdc2  ldc.i4.1
0xdc3  newarr   [System.Core]System.Linq.Expressions.Expression
0xdc8  dup
0xdc9  ldc.i4.0
0xdca  ldloc.s  6
0xdcc  stelem.ref
0xdcd  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0xdd2  ldc.i4.1
0xdd3  box      [mscorlib]System.Int32
0xdd8  ldtoken  [mscorlib]System.Int32
0xddd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xde2  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0xde7  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::Add(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression)
0xdec  ldc.i4.1
0xded  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xdf2  dup
0xdf3  ldc.i4.0
0xdf4  ldloc.s  6
0xdf6  stelem.ref
0xdf7  call     T0x2B000002
0xdfc  newobj   instance void class [System.Activities]System.Activities.InArgument`1<int32>::.ctor(class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<class [System.Activities]System.Activities.ActivityContext, var<u1>>>)
0xe01  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<int32>::set_Value(class [System.Activities]System.Activities.InArgument`1<var<u1>>)
0xe06  ldloc.s  8
0xe08  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0xe0d  ldloc.s  7
0xe0f  callvirt instance void [System.Activities]System.Activities.Statements.While::set_Body(class [System.Activities]System.Activities.Activity)
0xe14  ldloc.s  5
0xe16  callvirt instance void Microsoft.Crm.Workflow.Activities.BulkMailExpand::set_Body(class [System.Activities]System.Activities.Activity value)
0xe1b  ldloc.s  4
0xe1d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0xe22  ldloc.3
0xe23  ret
```
