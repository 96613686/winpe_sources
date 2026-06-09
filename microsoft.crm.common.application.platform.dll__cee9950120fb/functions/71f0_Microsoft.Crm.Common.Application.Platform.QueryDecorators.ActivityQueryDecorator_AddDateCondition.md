# Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddDateCondition

- ea: `0x71f0`
- end: `0x7268`
- name: `Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddDateCondition`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6f20`
- `0x6ff0`

## callees

- `0x71f0`

## pseudocode

```c

```

## disassembly

```asm
0x71f0  ldarg.3
0x71f1  ldc.i4.1
0x71f2  newarr   [mscorlib]System.Char
0x71f7  dup
0x71f8  ldc.i4.0
0x71f9  ldc.i4.s 0x3B
0x71fb  stelem.i2
0x71fc  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x7201  stloc.0
0x7202  ldloc.0
0x7203  ldlen
0x7204  conv.i4
0x7205  ldc.i4.1
0x7206  bgt.s    loc_7210
0x7208  ldc.i4.0
0x7209  newarr   [mscorlib]System.Object
0x720e  br.s     loc_721C
0x7210  ldc.i4.1
0x7211  newarr   [mscorlib]System.Object
0x7216  dup
0x7217  ldc.i4.0
0x7218  ldloc.0
0x7219  ldc.i4.1
0x721a  ldelem.ref
0x721b  stelem.ref
0x721c  stloc.1
0x721d  ldarg.2
0x721e  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator
0x7223  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7228  ldloc.0
0x7229  ldc.i4.0
0x722a  ldelem.ref
0x722b  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x7230  unbox.any [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator
0x7235  ldloc.1
0x7236  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x723b  stloc.2
0x723c  ldloc.2
0x723d  ldarg.2
0x723e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x7243  ldloc.2
0x7244  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator
0x7249  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x724e  ldloc.0
0x724f  ldc.i4.0
0x7250  ldelem.ref
0x7251  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x7256  unbox.any [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator
0x725b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x7260  ldarg.1
0x7261  ldloc.2
0x7262  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x7267  ret
```
