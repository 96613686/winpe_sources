# Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::CreateLinkStateTrackedSearchFolder

- ea: `0x39c50`
- end: `0x39d53`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::CreateLinkStateTrackedSearchFolder`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x39820`

## callees

- `0x15af0`
- `0x15b00`
- `0x21790`
- `0x21d10`
- `0x21d20`
- `0x21d50`
- `0x21d70`
- `0x21d90`
- `0x21db0`
- `0x21dc0`
- `0x21df0`
- `0x21e00`
- `0x21e20`
- `0x21e50`
- `0x21e90`
- `0x21eb0`
- `0x21ed0`
- `0x21ef0`
- `0x21f10`
- `0x21f30`
- `0x21f40`
- `0x21f70`
- `0x21f80`
- `0x22100`
- `0x22130`
- `0x22150`
- `0x22190`
- `0x221a0`
- `0x41c90`
- `0x41cb0`

## string_xrefs

- `0x39cf8`: `CrmEmailMessagesPendingLinking`

## pseudocode

```c

```

## disassembly

```asm
0x39c50  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.IsEqualToType::.ctor()
0x39c55  dup
0x39c56  ldarg.0
0x39c57  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39c5c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetLinkStateTrackerExtendedFieldTypePath()
0x39c61  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.TwoOperandExpressionType::set_Item(class Microsoft.Crm.Asynchronous.EmailConnector.BasePathToElementType value)
0x39c66  dup
0x39c67  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.FieldURIOrConstantType::.ctor()
0x39c6c  dup
0x39c6d  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ConstantValueType::.ctor()
0x39c72  dup
0x39c73  ldstr    a1// "1"
0x39c78  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ConstantValueType::set_Value(string value)
0x39c7d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.FieldURIOrConstantType::set_Item(object value)
0x39c82  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.TwoOperandExpressionType::set_FieldURIOrConstant(class Microsoft.Crm.Asynchronous.EmailConnector.FieldURIOrConstantType value)
0x39c87  stloc.0
0x39c88  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ContainsExpressionType::.ctor()
0x39c8d  dup
0x39c8e  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ConstantValueType::.ctor()
0x39c93  dup
0x39c94  ldstr    aIpmNote// "IPM.NOTE"
0x39c99  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ConstantValueType::set_Value(string value)
0x39c9e  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ContainsExpressionType::set_Constant(class Microsoft.Crm.Asynchronous.EmailConnector.ConstantValueType value)
0x39ca3  dup
0x39ca4  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.PathToUnindexedFieldType::.ctor()
0x39ca9  dup
0x39caa  ldc.i4.s 0x11
0x39cac  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.PathToUnindexedFieldType::set_FieldURI(valuetype Microsoft.Crm.Asynchronous.EmailConnector.UnindexedFieldURIType value)
0x39cb1  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ContainsExpressionType::set_Item(class Microsoft.Crm.Asynchronous.EmailConnector.BasePathToElementType value)
0x39cb6  dup
0x39cb7  ldc.i4.1
0x39cb8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ContainsExpressionType::set_ContainmentComparison(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ContainmentComparisonType value)
0x39cbd  dup
0x39cbe  ldc.i4.1
0x39cbf  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ContainsExpressionType::set_ContainmentComparisonSpecified(bool value)
0x39cc4  dup
0x39cc5  ldc.i4.1
0x39cc6  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ContainsExpressionType::set_ContainmentMode(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ContainmentModeType value)
0x39ccb  dup
0x39ccc  ldc.i4.1
0x39ccd  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ContainsExpressionType::set_ContainmentModeSpecified(bool value)
0x39cd2  stloc.1
0x39cd3  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.AndType::.ctor()
0x39cd8  stloc.3
0x39cd9  ldloc.3
0x39cda  ldc.i4.2
0x39cdb  newarr   Microsoft.Crm.Asynchronous.EmailConnector.SearchExpressionType
0x39ce0  dup
0x39ce1  ldc.i4.0
0x39ce2  ldloc.0
0x39ce3  stelem.ref
0x39ce4  dup
0x39ce5  ldc.i4.1
0x39ce6  ldloc.1
0x39ce7  stelem.ref
0x39ce8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MultipleOperandBooleanExpressionType::set_Items(class Microsoft.Crm.Asynchronous.EmailConnector.SearchExpressionType[] value)
0x39ced  ldloc.3
0x39cee  stloc.2
0x39cef  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SearchFolderType::.ctor()
0x39cf4  stloc.s  4
0x39cf6  ldloc.s  4
0x39cf8  ldstr    aCrmemailmessag// "CrmEmailMessagesPendingLinking"
0x39cfd  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::set_DisplayName(string value)
0x39d02  ldloc.s  4
0x39d04  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SearchParametersType::.ctor()
0x39d09  stloc.s  5
0x39d0b  ldloc.s  5
0x39d0d  ldc.i4.1
0x39d0e  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SearchParametersType::set_Traversal(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SearchFolderTraversalType value)
0x39d13  ldloc.s  5
0x39d15  ldc.i4.1
0x39d16  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SearchParametersType::set_TraversalSpecified(bool value)
0x39d1b  ldloc.s  5
0x39d1d  ldc.i4.1
0x39d1e  newarr   Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderIdType
0x39d23  dup
0x39d24  ldc.i4.0
0x39d25  ldarg.0
0x39d26  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39d2b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.DistinguishedFolderIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetMsgFolderRootDistinguishedFolderIdType()
0x39d30  stelem.ref
0x39d31  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SearchParametersType::set_BaseFolderIds(class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderIdType[] value)
0x39d36  ldloc.s  5
0x39d38  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.RestrictionType::.ctor()
0x39d3d  dup
0x39d3e  ldloc.2
0x39d3f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.RestrictionType::set_Item(class Microsoft.Crm.Asynchronous.EmailConnector.SearchExpressionType value)
0x39d44  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SearchParametersType::set_Restriction(class Microsoft.Crm.Asynchronous.EmailConnector.RestrictionType value)
0x39d49  ldloc.s  5
0x39d4b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SearchFolderType::set_SearchParameters(class Microsoft.Crm.Asynchronous.EmailConnector.SearchParametersType value)
0x39d50  ldloc.s  4
0x39d52  ret
```
