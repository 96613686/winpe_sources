# Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::GetConditionExpression

- ea: `0x161a0`
- end: `0x1627b`
- name: `Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::GetConditionExpression`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x15cb0`
- `0x161a0`
- `0x16280`
- `0x23e90`

## string_xrefs

- `0x161cc`: `The left side of the "{0}" operator must be a property of the entity.`
- `0x1624a`: `The right side of the "{0}" operator must be a Enum value.`

## pseudocode

```c

```

## disassembly

```asm
0x161a0  ldarg.2
0x161a1  call     void class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator>::ValidateRightValueForBinaryOperator(class [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorNode)
0x161a6  ldnull
0x161a7  stloc.0
0x161a8  ldarg.1
0x161a9  isinst   [mscorlib]System.String
0x161ae  stloc.1
0x161af  ldarg.1
0x161b0  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty
0x161b5  brfalse.s loc_161C7
0x161b7  ldarg.1
0x161b8  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty
0x161bd  stloc.0
0x161be  ldloc.0
0x161bf  call     string Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataAttributeNameFromEdmProperty(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x161c4  stloc.1
0x161c5  br.s     loc_161EB
0x161c7  ldc.i4   0x1F5
0x161cc  ldstr    aTheLeftSideOfT// "The left side of the \"{0}\" operator m"...
0x161d1  ldc.i4.1
0x161d2  newarr   [mscorlib]System.Object
0x161d7  dup
0x161d8  ldc.i4.0
0x161d9  ldarg.2
0x161da  callvirt instance valuetype [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorNode::get_OperatorKind()
0x161df  box      [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind
0x161e4  stelem.ref
0x161e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x161ea  throw
0x161eb  ldarg.0
0x161ec  ldarg.0
0x161ed  ldarg.2
0x161ee  callvirt instance valuetype [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorNode::get_OperatorKind()
0x161f3  callvirt instance var<u1> class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator>::GetConditionOperator(char)
0x161f8  ldarg.s  4
0x161fa  call     instance var<u1> class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator>::GetCrmConditionalOperator(char, var<u1>)
0x161ff  stloc.2
0x16200  ldnull
0x16201  stloc.3
0x16202  ldarg.3
0x16203  brtrue.s loc_16214
0x16205  ldarg.0
0x16206  ldloc.2
0x16207  ldarg.2
0x16208  callvirt instance valuetype [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorNode::get_OperatorKind()
0x1620d  call     instance void Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::ValidateConditionOperatorForNullValues(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator op, valuetype [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind operatorKind)
0x16212  br.s     loc_16272
0x16214  ldloc.0
0x16215  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x1621a  call     bool [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::IsEnum(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x1621f  brfalse.s loc_16264
0x16221  ldarg.3
0x16222  isinst   [Microsoft.OData.Core]Microsoft.OData.ODataEnumValue
0x16227  brfalse.s loc_16239
0x16229  ldloc.0
0x1622a  ldarg.3
0x1622b  ldarg.0
0x1622c  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator>::edmModel
0x16231  call     object Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmAttributeValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, object propertyValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x16236  stloc.3
0x16237  br.s     loc_16272
0x16239  ldarg.3
0x1623a  isinst   [mscorlib]System.Enum
0x1623f  brfalse.s loc_16245
0x16241  ldarg.3
0x16242  stloc.3
0x16243  br.s     loc_16272
0x16245  ldc.i4   0x1F5
0x1624a  ldstr    aTheRightSideOf_1// "The right side of the \"{0}\" operator "...
0x1624f  ldc.i4.1
0x16250  newarr   [mscorlib]System.Object
0x16255  dup
0x16256  ldc.i4.0
0x16257  ldloc.2
0x16258  box      [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator
0x1625d  stelem.ref
0x1625e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x16263  throw
0x16264  ldarg.0
0x16265  ldarg.3
0x16266  ldloc.2
0x16267  box      [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator
0x1626c  call     instance object class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator>::TranslateValueToCrmType(object, class [mscorlib]System.Enum)
0x16271  stloc.3
0x16272  ldloc.1
0x16273  ldloc.2
0x16274  ldloc.3
0x16275  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator, object)
0x1627a  ret
```
