# Microsoft.Crm.Query.DeserializeFetchVisitor::Visit_0

- ea: `0x16600`
- end: `0x1680e`
- name: `Microsoft.Crm.Query.DeserializeFetchVisitor::Visit_0`
- size: `526`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callees

- `0x132d0`
- `0x13340`
- `0x13380`
- `0x133b0`
- `0x133c0`
- `0x133f0`
- `0x13400`
- `0x13420`
- `0x13430`
- `0x134a0`
- `0x134d0`
- `0x13520`
- `0x13530`
- `0x16600`
- `0x17a10`
- `0x17a50`
- `0x17ba0`
- `0x17c90`
- `0x17db0`
- `0x199c0`
- `0x1b9b0`
- `0x1e3d0`
- `0x52e20`
- `0x52e60`
- `0x52eb0`

## string_xrefs

- `0x167b0`: `An attribute can not be requested when an aggregate operation has been specified and its neither groupby nor aggregate.  NodeXml : {0}`
- `0x167e9`: `An alias must be specified for every attribute in an aggregate query. NodeXml: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x16600  ldarg.0
0x16601  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x16606  stloc.0
0x16607  ldloc.0
0x16608  ldstr    aName// "name"
0x1660d  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::GetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x16612  stloc.1
0x16613  ldarg.0
0x16614  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::skipMissingAttributes
0x16619  brtrue.s loc_1662A
0x1661b  ldarg.0
0x1661c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x16621  ldloc.1
0x16622  ldc.i4.1
0x16623  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x16628  br.s     loc_16637
0x1662a  ldarg.0
0x1662b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x16630  ldloc.1
0x16631  ldc.i4.1
0x16632  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x16637  stloc.2
0x16638  ldloc.2
0x16639  brtrue.s loc_1663C
0x1663b  ret
0x1663c  ldloc.2
0x1663d  ldarg.0
0x1663e  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Query.DeserializeFetchVisitor::_attributesAccounted
0x16643  call     void Microsoft.Crm.Query.QueryHelper::ValidateMaxCalculatedFieldAllowed(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> accountedAttributes)
0x16648  ldarg.0
0x16649  ldc.i4.1
0x1664a  stfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bAttributesAdded
0x1664f  ldloc.2
0x16650  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x16655  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1665a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1665f  brfalse.s loc_16678
0x16661  ldarg.0
0x16662  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bHasAggregate
0x16667  brtrue.s loc_16678
0x16669  ldloc.2
0x1666a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayMask()
0x1666f  ldc.i4   0x800000
0x16674  and
0x16675  brtrue.s loc_16678
0x16677  ret
0x16678  ldarg.1
0x16679  ldloc.2
0x1667a  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_Attribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x1667f  ldarg.0
0x16680  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bInLinkEntity
0x16685  brfalse.s loc_16695
0x16687  ldarg.1
0x16688  ldarg.0
0x16689  ldfld    class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::linkEntityExpression
0x1668e  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_ParentLinkEntity(class Microsoft.Crm.Query.LinkEntityExpression value)
0x16693  br.s     loc_166A1
0x16695  ldarg.1
0x16696  ldarg.0
0x16697  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x1669c  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_ParentEntity(class Microsoft.Crm.Query.EntityExpression value)
0x166a1  ldnull
0x166a2  stloc.3
0x166a3  ldloc.0
0x166a4  ldstr    aAlias// "alias"
0x166a9  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x166ae  stloc.3
0x166af  ldloc.3
0x166b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x166b5  brtrue.s loc_166E7
0x166b7  ldarg.1
0x166b8  ldloc.3
0x166b9  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_Alias(string value)
0x166be  ldarg.1
0x166bf  ldc.i4.1
0x166c0  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_WasAliasProvided(bool value)
0x166c5  ldarg.0
0x166c6  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bInLinkEntity
0x166cb  brfalse.s loc_166DB
0x166cd  ldarg.1
0x166ce  callvirt instance class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.AttributeExpression::get_ParentLinkEntity()
0x166d3  ldloc.3
0x166d4  callvirt instance void Microsoft.Crm.Query.LinkEntityExpression::ValidateAttributeAliasUnique(string alias)
0x166d9  br.s     loc_166E7
0x166db  ldarg.1
0x166dc  callvirt instance class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.AttributeExpression::get_ParentEntity()
0x166e1  ldloc.3
0x166e2  callvirt instance void Microsoft.Crm.Query.EntityExpression::ValidateAttributeAliasUnique(string alias)
0x166e7  ldloc.0
0x166e8  ldstr    aRowaggregate// "rowaggregate"
0x166ed  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x166f2  stloc.s  4
0x166f4  ldloc.s  4
0x166f6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x166fb  brtrue.s loc_1670B
0x166fd  ldarg.1
0x166fe  ldarg.0
0x166ff  ldloc.s  4
0x16701  call     instance valuetype Microsoft.Crm.Query.RowAggregateType Microsoft.Crm.Query.DeserializeFetchVisitor::GetRowAggregateType(string aggregate)
0x16706  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_RowAggregate(valuetype Microsoft.Crm.Query.RowAggregateType value)
0x1670b  ldloc.0
0x1670c  ldstr    aAggregate// "aggregate"
0x16711  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x16716  stloc.s  5
0x16718  ldloc.s  5
0x1671a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1671f  brtrue.s loc_1678B
0x16721  ldarg.0
0x16722  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bHasAggregate
0x16727  brtrue.s loc_16739
0x16729  ldstr    aAnAggregateOpe// "An aggregate operation was not initiall"...
0x1672e  ldc.i4   0x8004111A
0x16733  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16738  throw
0x16739  ldarg.0
0x1673a  ldloc.s  5
0x1673c  call     instance valuetype Microsoft.Crm.Query.AggregateType Microsoft.Crm.Query.DeserializeFetchVisitor::GetAggregateType(string aggregate)
0x16741  stloc.s  6
0x16743  ldc.i4.0
0x16744  stloc.s  7
0x16746  ldarg.0
0x16747  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x1674c  ldstr    aDistinct// "distinct"
0x16751  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x16756  stloc.s  8
0x16758  ldloc.s  8
0x1675a  brfalse.s loc_16771
0x1675c  ldloc.s  6
0x1675e  ldc.i4.1
0x1675f  beq.s    loc_16771
0x16761  ldarg.0
0x16762  ldloc.s  8
0x16764  ldloc.0
0x16765  ldc.i4   0x8004111A
0x1676a  call     instance bool Microsoft.Crm.Query.DeserializeFetchVisitor::ParseFetchBool(string boolString, class [System.Xml.Linq]System.Xml.Linq.XElement node, int32 errorCode)
0x1676f  stloc.s  7
0x16771  ldloc.s  6
0x16773  ldloc.s  7
0x16775  newobj   instance void Microsoft.Crm.Query.Aggregate::.ctor(valuetype Microsoft.Crm.Query.AggregateType type, bool isDistinct)
0x1677a  stloc.s  9
0x1677c  ldarg.1
0x1677d  ldloc.s  9
0x1677f  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_Aggregate(class Microsoft.Crm.Query.Aggregate value)
0x16784  ldarg.0
0x16785  ldarg.1
0x16786  call     instance void Microsoft.Crm.Query.DeserializeFetchVisitor::ValidateAggregateAttributeType(class Microsoft.Crm.Query.AttributeExpression attribute)
0x1678b  ldarg.0
0x1678c  ldarg.1
0x1678d  ldloc.0
0x1678e  call     instance void Microsoft.Crm.Query.DeserializeFetchVisitor::ProcessGroupByAttribute(class Microsoft.Crm.Query.AttributeExpression attribute, class [System.Xml.Linq]System.Xml.Linq.XElement node)
0x16793  ldarg.0
0x16794  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bHasAggregate
0x16799  brfalse.s loc_167D4
0x1679b  ldarg.1
0x1679c  callvirt instance bool Microsoft.Crm.Query.AttributeExpression::get_HasGroupBy()
0x167a1  brtrue.s loc_167D4
0x167a3  ldarg.1
0x167a4  callvirt instance bool Microsoft.Crm.Query.AttributeExpression::get_HasAggregate()
0x167a9  brtrue.s loc_167D4
0x167ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x167b0  ldstr    aAnAttributeCan_0// "An attribute can not be requested when "...
0x167b5  ldc.i4.1
0x167b6  newarr   [mscorlib]System.Object
0x167bb  dup
0x167bc  ldc.i4.0
0x167bd  ldloc.0
0x167be  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::OuterXml(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x167c3  stelem.ref
0x167c4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x167c9  ldc.i4   0x8004111E
0x167ce  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x167d3  throw
0x167d4  ldarg.0
0x167d5  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bHasAggregate
0x167da  brfalse.s loc_1680D
0x167dc  ldarg.1
0x167dd  callvirt instance bool Microsoft.Crm.Query.AttributeExpression::get_WasAliasProvided()
0x167e2  brtrue.s loc_1680D
0x167e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x167e9  ldstr    aAnAliasMustBeS// "An alias must be specified for every at"...
0x167ee  ldc.i4.1
0x167ef  newarr   [mscorlib]System.Object
0x167f4  dup
0x167f5  ldc.i4.0
0x167f6  ldloc.0
0x167f7  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::OuterXml(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x167fc  stelem.ref
0x167fd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16802  ldc.i4   0x8004110B
0x16807  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1680c  throw
0x1680d  ret
```
