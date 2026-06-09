# Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4::ValidateRightValueForBinaryOperator

- ea: `0x142f0`
- end: `0x14329`
- name: `Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4::ValidateRightValueForBinaryOperator`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x142f0`

## string_xrefs

- `0x14309`: `The right side of the "{0}" operator must be a constant value.`

## pseudocode

```c

```

## disassembly

```asm
0x142f0  ldarg.0
0x142f1  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SingleValueNode [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorNode::get_Right()
0x142f6  callvirt instance valuetype [Microsoft.OData.Core]Microsoft.OData.UriParser.QueryNodeKind [Microsoft.OData.Core]Microsoft.OData.UriParser.QueryNode::get_Kind()
0x142fb  stloc.0
0x142fc  ldloc.0
0x142fd  ldc.i4.1
0x142fe  beq.s    loc_14328
0x14300  ldloc.0
0x14301  ldc.i4.2
0x14302  beq.s    loc_14328
0x14304  ldc.i4   0x1F5
0x14309  ldstr    aTheRightSideOf// "The right side of the \"{0}\" operator "...
0x1430e  ldc.i4.1
0x1430f  newarr   [mscorlib]System.Object
0x14314  dup
0x14315  ldc.i4.0
0x14316  ldarg.0
0x14317  callvirt instance valuetype [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorNode::get_OperatorKind()
0x1431c  box      [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind
0x14321  stelem.ref
0x14322  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x14327  throw
0x14328  ret
```
