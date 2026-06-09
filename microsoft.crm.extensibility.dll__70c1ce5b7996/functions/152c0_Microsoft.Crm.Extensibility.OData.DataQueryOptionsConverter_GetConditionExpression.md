# Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::GetConditionExpression

- ea: `0x152c0`
- end: `0x153ba`
- name: `Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::GetConditionExpression`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xfb80`
- `0xfba0`
- `0x152c0`

## string_xrefs

- `0x152e1`: `The left side of the "{0}" operator must be a property of the entity.`
- `0x15374`: `The right side of the "{0}" operator can't be NULL.`

## pseudocode

```c

```

## disassembly

```asm
0x152c0  ldarg.2
0x152c1  call     void class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::ValidateRightValueForBinaryOperator(class [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorNode)
0x152c6  ldarg.1
0x152c7  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty
0x152cc  brfalse.s loc_152DC
0x152ce  ldarg.1
0x152cf  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty
0x152d4  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetCrmAttributeNameFromEdmAttributeName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x152d9  pop
0x152da  br.s     loc_15300
0x152dc  ldc.i4   0x1F5
0x152e1  ldstr    aTheLeftSideOfT// "The left side of the \"{0}\" operator m"...
0x152e6  ldc.i4.1
0x152e7  newarr   [mscorlib]System.Object
0x152ec  dup
0x152ed  ldc.i4.0
0x152ee  ldarg.2
0x152ef  callvirt instance valuetype [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorNode::get_OperatorKind()
0x152f4  box      [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind
0x152f9  stelem.ref
0x152fa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x152ff  throw
0x15300  ldarg.0
0x15301  ldarg.0
0x15302  ldarg.2
0x15303  callvirt instance valuetype [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorNode::get_OperatorKind()
0x15308  callvirt instance var<u1> class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::GetConditionOperator(char)
0x1530d  ldarg.s  4
0x1530f  call     instance var<u1> class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::GetCrmConditionalOperator(char, var<u1>)
0x15314  stloc.0
0x15315  ldnull
0x15316  stloc.1
0x15317  ldarg.3
0x15318  brtrue.s loc_15393
0x1531a  ldloc.0
0x1531b  brtrue.s loc_15344
0x1531d  ldarg.0
0x1531e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::context
0x15323  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x15328  dup
0x15329  ldarg.1
0x1532a  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty
0x1532f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Extensibility.OData.EdmUtilities::GetCrmAttributeMetadata(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x15334  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x15339  dup
0x1533a  ldc.i4.s 0xC
0x1533c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_ConditionOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x15341  stloc.1
0x15342  br.s     loc_153B8
0x15344  ldloc.0
0x15345  ldc.i4.1
0x15346  bne.un.s loc_1536F
0x15348  ldarg.0
0x15349  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::context
0x1534e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x15353  dup
0x15354  ldarg.1
0x15355  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty
0x1535a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Extensibility.OData.EdmUtilities::GetCrmAttributeMetadata(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x1535f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x15364  dup
0x15365  ldc.i4.s 0xD
0x15367  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::set_ConditionOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x1536c  stloc.1
0x1536d  br.s     loc_153B8
0x1536f  ldc.i4   0x190
0x15374  ldstr    aTheRightSideOf_0// "The right side of the \"{0}\" operator "...
0x15379  ldc.i4.1
0x1537a  newarr   [mscorlib]System.Object
0x1537f  dup
0x15380  ldc.i4.0
0x15381  ldarg.2
0x15382  callvirt instance valuetype [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorNode::get_OperatorKind()
0x15387  box      [Microsoft.OData.Core]Microsoft.OData.UriParser.BinaryOperatorKind
0x1538c  stelem.ref
0x1538d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x15392  throw
0x15393  ldarg.1
0x15394  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty
0x15399  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Extensibility.OData.EdmUtilities::GetCrmAttributeMetadata(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x1539e  ldloc.0
0x1539f  ldarg.0
0x153a0  ldarg.3
0x153a1  ldloc.0
0x153a2  box      [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator
0x153a7  call     instance object class Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::TranslateValueToCrmType(object, class [mscorlib]System.Enum)
0x153ac  ldarg.0
0x153ad  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.OData.DataQueryOptionsConverter::context
0x153b2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x153b7  stloc.1
0x153b8  ldloc.1
0x153b9  ret
```
