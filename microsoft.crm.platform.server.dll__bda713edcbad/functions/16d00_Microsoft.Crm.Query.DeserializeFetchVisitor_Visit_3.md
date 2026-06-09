# Microsoft.Crm.Query.DeserializeFetchVisitor::Visit_3

- ea: `0x16d00`
- end: `0x16f91`
- name: `Microsoft.Crm.Query.DeserializeFetchVisitor::Visit_3`
- size: `657`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14370`
- `0x14440`
- `0x16d00`
- `0x17db0`
- `0x18610`
- `0x18620`
- `0x1a860`
- `0x1a8f0`
- `0x1a930`
- `0x1a9b0`
- `0x1a9c0`
- `0x1a9d0`
- `0x1a9e0`
- `0x1ab00`
- `0x1ab40`
- `0x1adc0`
- `0x1afa0`
- `0x52e60`
- `0x52e80`
- `0x52eb0`

## string_xrefs

- `0x16d3b`: `Invalid filter type specified. Valid values are 'and', or 'or'. Filter Type Value = {0} NodeXml = {1}`
- `0x16dc7`: `Invalid filter hint specified. only 1 union hint allowed. NodeXml = {0}`
- `0x16dec`: `Invalid filter hint specified. Valid values are 'union' with filterType 'or'. Filter Hint Value = {0} NodeXml = {1}`
- `0x16f4a`: `Invalid Child Node. There can only be condition and filter nodes. NodeName = {0} NodeXml = {1}`

## pseudocode

```c

```

## disassembly

```asm
0x16d00  ldarg.0
0x16d01  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x16d06  ldstr    aType// "type"
0x16d0b  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x16d10  stloc.0
0x16d11  ldloc.0
0x16d12  brtrue.s loc_16D1C
0x16d14  ldstr    aAnd// "and"
0x16d19  stloc.0
0x16d1a  br.s     loc_16D68
0x16d1c  ldloc.0
0x16d1d  ldstr    aAnd// "and"
0x16d22  callvirt instance bool [mscorlib]System.String::Equals(string)
0x16d27  brtrue.s loc_16D68
0x16d29  ldloc.0
0x16d2a  ldstr    aOr// "or"
0x16d2f  callvirt instance bool [mscorlib]System.String::Equals(string)
0x16d34  brtrue.s loc_16D68
0x16d36  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16d3b  ldstr    aInvalidFilterT// "Invalid filter type specified. Valid va"...
0x16d40  ldc.i4.2
0x16d41  newarr   [mscorlib]System.Object
0x16d46  dup
0x16d47  ldc.i4.0
0x16d48  ldloc.0
0x16d49  stelem.ref
0x16d4a  dup
0x16d4b  ldc.i4.1
0x16d4c  ldarg.0
0x16d4d  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x16d52  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::InnerXml(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x16d57  stelem.ref
0x16d58  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16d5d  ldc.i4   0x80041122
0x16d62  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16d67  throw
0x16d68  ldarg.1
0x16d69  ldloc.0
0x16d6a  call     valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.QuerySerializationUtil::LogicalOperatorFromString(string)
0x16d6f  callvirt instance void Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator value)
0x16d74  ldarg.0
0x16d75  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x16d7a  ldstr    aHint// "hint"
0x16d7f  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x16d84  stloc.1
0x16d85  ldloc.1
0x16d86  brfalse  loc_16E19
0x16d8b  ldarg.1
0x16d8c  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator Microsoft.Crm.Query.FilterExpression::get_FilterOperator()
0x16d91  ldc.i4.1
0x16d92  bne.un.s loc_16DE7
0x16d94  ldloc.1
0x16d95  ldstr    aUnion// "union"
0x16d9a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16d9f  brfalse.s loc_16DE7
0x16da1  ldarg.1
0x16da2  ldstr    aUnion// "union"
0x16da7  callvirt instance void Microsoft.Crm.Query.FilterExpression::set_FilterHint(string value)
0x16dac  ldarg.0
0x16dad  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x16db2  callvirt instance bool Microsoft.Crm.Query.EntityExpression::get_HasUnionHint()
0x16db7  brtrue.s loc_16DC7
0x16db9  ldarg.0
0x16dba  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x16dbf  ldc.i4.1
0x16dc0  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_HasUnionHint(bool value)
0x16dc5  br.s     loc_16E19
0x16dc7  ldstr    aInvalidFilterH// "Invalid filter hint specified. only 1 u"...
0x16dcc  ldarg.0
0x16dcd  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x16dd2  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::InnerXml(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x16dd7  call     string [mscorlib]System.String::Format(string, object)
0x16ddc  ldc.i4   0x80041122
0x16de1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16de6  throw
0x16de7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16dec  ldstr    aInvalidFilterH_0// "Invalid filter hint specified. Valid va"...
0x16df1  ldc.i4.2
0x16df2  newarr   [mscorlib]System.Object
0x16df7  dup
0x16df8  ldc.i4.0
0x16df9  ldloc.1
0x16dfa  stelem.ref
0x16dfb  dup
0x16dfc  ldc.i4.1
0x16dfd  ldarg.0
0x16dfe  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x16e03  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::InnerXml(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x16e08  stelem.ref
0x16e09  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16e0e  ldc.i4   0x80041122
0x16e13  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16e18  throw
0x16e19  ldarg.0
0x16e1a  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x16e1f  ldstr    aIsquickfindfie// "isquickfindfields"
0x16e24  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x16e29  stloc.2
0x16e2a  ldloc.2
0x16e2b  brfalse.s loc_16E56
0x16e2d  ldc.i4.1
0x16e2e  ldarg.1
0x16e2f  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator Microsoft.Crm.Query.FilterExpression::get_FilterOperator()
0x16e34  bne.un.s loc_16E56
0x16e36  ldarg.0
0x16e37  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::_processingLinkEntity
0x16e3c  brtrue.s loc_16E56
0x16e3e  ldarg.1
0x16e3f  ldarg.0
0x16e40  ldloc.2
0x16e41  ldarg.0
0x16e42  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x16e47  ldc.i4   0x80041138
0x16e4c  call     instance bool Microsoft.Crm.Query.DeserializeFetchVisitor::ParseFetchBool(string boolString, class [System.Xml.Linq]System.Xml.Linq.XElement node, int32 errorCode)
0x16e51  callvirt instance void Microsoft.Crm.Query.FilterExpression::set_IsQuickFindFilter(bool value)
0x16e56  ldarg.0
0x16e57  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x16e5c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements()
0x16e61  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x16e66  stloc.3
0x16e67  br       loc_16F79
0x16e6c  ldloc.3
0x16e6d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x16e72  stloc.s  4
0x16e74  ldloc.s  4
0x16e76  isinst   [System.Xml.Linq]System.Xml.Linq.XElement
0x16e7b  stloc.s  5
0x16e7d  ldloc.s  5
0x16e7f  brfalse  loc_16F79
0x16e84  ldarg.0
0x16e85  ldloc.s  5
0x16e87  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x16e8c  ldloc.s  5
0x16e8e  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x16e93  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XName::get_LocalName()
0x16e98  ldstr    aCondition// "condition"
0x16e9d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16ea2  brfalse.s loc_16EFD
0x16ea4  ldarg.1
0x16ea5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext Microsoft.Crm.Query.Expression::get_UserAndOrganizationContext()
0x16eaa  ldarg.1
0x16eab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Query.Expression::get_Cache()
0x16eb0  newobj   instance void Microsoft.Crm.Query.ConditionExpression::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x16eb5  stloc.s  6
0x16eb7  ldarg.0
0x16eb8  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::currentConditionIsQuickFindCondition
0x16ebd  stloc.s  7
0x16ebf  ldarg.0
0x16ec0  ldarg.1
0x16ec1  callvirt instance bool Microsoft.Crm.Query.FilterExpression::get_IsQuickFindFilter()
0x16ec6  stfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::currentConditionIsQuickFindCondition
0x16ecb  ldloc.s  6
0x16ecd  ldarg.0
0x16ece  callvirt instance void Microsoft.Crm.Query.Expression::Deserialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x16ed3  leave.s  loc_16EDE
0x16ed5  ldarg.0
0x16ed6  ldloc.s  7
0x16ed8  stfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::currentConditionIsQuickFindCondition
0x16edd  endfinally
0x16ede  ldarg.0
0x16edf  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::skipMissingAttributes
0x16ee4  brfalse.s loc_16EF2
0x16ee6  ldloc.s  6
0x16ee8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.ConditionExpression::get_Attribute()
0x16eed  brfalse  loc_16F79
0x16ef2  ldarg.1
0x16ef3  ldloc.s  6
0x16ef5  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(class Microsoft.Crm.Query.ConditionExpression condition)
0x16efa  pop
0x16efb  br.s     loc_16F79
0x16efd  ldloc.s  5
0x16eff  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x16f04  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XName::get_LocalName()
0x16f09  ldstr    aFilter// "filter"
0x16f0e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16f13  brfalse.s loc_16F45
0x16f15  ldarg.0
0x16f16  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x16f1b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x16f20  ldarg.1
0x16f21  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext Microsoft.Crm.Query.Expression::get_UserAndOrganizationContext()
0x16f26  ldarg.1
0x16f27  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Query.Expression::get_Cache()
0x16f2c  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x16f31  stloc.s  8
0x16f33  ldloc.s  8
0x16f35  ldarg.0
0x16f36  callvirt instance void Microsoft.Crm.Query.Expression::Deserialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x16f3b  ldarg.1
0x16f3c  ldloc.s  8
0x16f3e  callvirt instance void Microsoft.Crm.Query.FilterExpression::AddFilter(class Microsoft.Crm.Query.FilterExpression childFilter)
0x16f43  br.s     loc_16F79
0x16f45  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16f4a  ldstr    aInvalidChildNo_0// "Invalid Child Node. There can only be c"...
0x16f4f  ldc.i4.2
0x16f50  newarr   [mscorlib]System.Object
0x16f55  dup
0x16f56  ldc.i4.0
0x16f57  ldloc.s  5
0x16f59  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x16f5e  stelem.ref
0x16f5f  dup
0x16f60  ldc.i4.1
0x16f61  ldloc.s  4
0x16f63  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::OuterXml(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x16f68  stelem.ref
0x16f69  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16f6e  ldc.i4   0x8004111C
0x16f73  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16f78  throw
0x16f79  ldloc.3
0x16f7a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16f7f  brtrue   loc_16E6C
0x16f84  leave.s  loc_16F90
0x16f86  ldloc.3
0x16f87  brfalse.s loc_16F8F
0x16f89  ldloc.3
0x16f8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16f8f  endfinally
0x16f90  ret
```
