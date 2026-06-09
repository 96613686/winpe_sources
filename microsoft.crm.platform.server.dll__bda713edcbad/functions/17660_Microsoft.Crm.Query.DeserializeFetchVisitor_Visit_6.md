# Microsoft.Crm.Query.DeserializeFetchVisitor::Visit_6

- ea: `0x17660`
- end: `0x17a02`
- name: `Microsoft.Crm.Query.DeserializeFetchVisitor::Visit_6`
- size: `930`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callees

- `0x17660`
- `0x1a5a0`
- `0x1a860`
- `0x1a8f0`
- `0x1a920`
- `0x1a930`
- `0x1aa70`
- `0x1ab40`
- `0x1afa0`
- `0x1b0c0`
- `0x1b0d0`
- `0x1b110`
- `0x1b130`
- `0x1b140`
- `0x1b150`
- `0x1b160`
- `0x1b230`
- `0x1b240`
- `0x1b250`
- `0x1b270`
- `0x1b2c0`
- `0x1b2d0`
- `0x1b480`
- `0x1b580`
- `0x1e3d0`
- `0x1e500`
- `0x52e20`
- `0x52e60`
- `0x52e80`
- `0x52eb0`

## string_xrefs

- `0x178bd`: `link-entity`
- `0x176ff`: `link-type`
- `0x17766`: `Invalid link-type specified, valid values are: 'natural', 'inner', and 'outer'. link-type = {0} NodeXml = {1}`
- `0x1796d`: `Invalid Child Node, valid values are: filter, order or link-entity. NodeName = {0} NodeXml = {1}`

## pseudocode

```c

```

## disassembly

```asm
0x17660  ldarg.0
0x17661  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::_isReportContext
0x17666  brtrue.s loc_17675
0x17668  ldarg.1
0x17669  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Query.Expression::get_OrganizationId()
0x1766e  call     int32 Microsoft.Crm.Query.QueryHelper::RetrieveQueryLinkEntityLimit(valuetype [mscorlib]System.Guid organizationId)
0x17673  br.s     loc_17684
0x17675  ldarg.1
0x17676  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Query.Expression::get_OrganizationId()
0x1767b  call     int32 Microsoft.Crm.Query.QueryHelper::RetrieveQueryLinkEntityLimit(valuetype [mscorlib]System.Guid organizationId)
0x17680  ldc.i4.2
0x17681  mul
0x17682  ldc.i4.1
0x17683  add
0x17684  stloc.0
0x17685  ldarg.0
0x17686  ldarg.0
0x17687  ldfld    int32 Microsoft.Crm.Query.DeserializeFetchVisitor::linkEntityCount
0x1768c  ldc.i4.1
0x1768d  add
0x1768e  stloc.s  9
0x17690  ldloc.s  9
0x17692  stfld    int32 Microsoft.Crm.Query.DeserializeFetchVisitor::linkEntityCount
0x17697  ldloc.s  9
0x17699  ldloc.0
0x1769a  ble.s    loc_176AD
0x1769c  ldc.i4   0x8004430D
0x176a1  ldc.i4.0
0x176a2  newarr   [mscorlib]System.Object
0x176a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x176ac  throw
0x176ad  ldarg.0
0x176ae  ldc.i4.1
0x176af  stfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bInLinkEntity
0x176b4  ldarg.0
0x176b5  ldarg.1
0x176b6  stfld    class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::linkEntityExpression
0x176bb  ldarg.0
0x176bc  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x176c1  stloc.1
0x176c2  ldc.i4.0
0x176c3  stloc.2
0x176c4  ldarg.0
0x176c5  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x176ca  ldstr    aName// "name"
0x176cf  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::GetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x176d4  stloc.3
0x176d5  ldarg.0
0x176d6  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x176db  ldstr    aTo// "to"
0x176e0  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x176e5  stloc.s  4
0x176e7  ldarg.0
0x176e8  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x176ed  ldstr    aFrom_0// "from"
0x176f2  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x176f7  stloc.s  5
0x176f9  ldarg.0
0x176fa  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x176ff  ldstr    aLinkType// "link-type"
0x17704  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x17709  stloc.s  6
0x1770b  ldarg.0
0x1770c  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x17711  ldstr    aAlias// "alias"
0x17716  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x1771b  stloc.s  7
0x1771d  ldloc.s  6
0x1771f  brtrue.s loc_17726
0x17721  ldc.i4.0
0x17722  stloc.s  8
0x17724  br.s     loc_17794
0x17726  ldloc.s  6
0x17728  ldstr    aNatural// "natural"
0x1772d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17732  brtrue.s loc_17752
0x17734  ldloc.s  6
0x17736  ldstr    aInner// "inner"
0x1773b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17740  brtrue.s loc_17757
0x17742  ldloc.s  6
0x17744  ldstr    aOuter// "outer"
0x17749  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1774e  brtrue.s loc_1775C
0x17750  br.s     loc_17761
0x17752  ldc.i4.2
0x17753  stloc.s  8
0x17755  br.s     loc_17794
0x17757  ldc.i4.0
0x17758  stloc.s  8
0x1775a  br.s     loc_17794
0x1775c  ldc.i4.1
0x1775d  stloc.s  8
0x1775f  br.s     loc_17794
0x17761  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17766  ldstr    aInvalidLinkTyp// "Invalid link-type specified, valid valu"...
0x1776b  ldc.i4.2
0x1776c  newarr   [mscorlib]System.Object
0x17771  dup
0x17772  ldc.i4.0
0x17773  ldloc.s  6
0x17775  stelem.ref
0x17776  dup
0x17777  ldc.i4.1
0x17778  ldarg.0
0x17779  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x1777e  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::InnerXml(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x17783  stelem.ref
0x17784  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17789  ldc.i4   0x80041117
0x1778e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x17793  throw
0x17794  ldarg.0
0x17795  ldarg.1
0x17796  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Query.Expression::get_Cache()
0x1779b  ldloc.3
0x1779c  ldc.i4.1
0x1779d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x177a2  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x177a7  ldloc.s  4
0x177a9  brtrue.s loc_177BB
0x177ab  ldloc.s  5
0x177ad  brtrue.s loc_177BB
0x177af  ldarg.1
0x177b0  ldloc.3
0x177b1  ldc.i4.1
0x177b2  callvirt instance class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.LinkEntityExpression::SetLinkProperties(string entityName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType mappingType)
0x177b7  starg.s  1
0x177b9  br.s     loc_177CA
0x177bb  ldarg.1
0x177bc  ldloc.3
0x177bd  ldloc.s  5
0x177bf  ldloc.s  4
0x177c1  ldc.i4.0
0x177c2  ldloc.s  8
0x177c4  ldc.i4.1
0x177c5  callvirt instance void Microsoft.Crm.Query.LinkEntityExpression::SetLinkProperties(string entityName, string attributeFrom, string attributeTo, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator joinOperator, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType mappingType)
0x177ca  ldloc.s  7
0x177cc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x177d1  brtrue.s loc_177E2
0x177d3  ldarg.1
0x177d4  ldloc.s  7
0x177d6  callvirt instance void Microsoft.Crm.Query.LinkEntityExpression::set_TableAlias(string value)
0x177db  ldarg.1
0x177dc  ldc.i4.1
0x177dd  callvirt instance void Microsoft.Crm.Query.LinkEntityExpression::set_FetchAliasWasSpecified(bool value)
0x177e2  ldarg.1
0x177e3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkFromAttribute()
0x177e8  ldarg.0
0x177e9  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Query.DeserializeFetchVisitor::_attributesAccounted
0x177ee  call     void Microsoft.Crm.Query.QueryHelper::ValidateMaxCalculatedFieldAllowed(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> accountedAttributes)
0x177f3  ldarg.1
0x177f4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkToAttribute()
0x177f9  ldarg.0
0x177fa  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Query.DeserializeFetchVisitor::_attributesAccounted
0x177ff  call     void Microsoft.Crm.Query.QueryHelper::ValidateMaxCalculatedFieldAllowed(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> accountedAttributes)
0x17804  ldarg.1
0x17805  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkFromAttribute()
0x1780a  call     void Microsoft.Crm.Query.ExpressionVisitor::ValidateMetaDataAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0x1780f  ldarg.1
0x17810  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.LinkEntityExpression::get_LinkToAttribute()
0x17815  call     void Microsoft.Crm.Query.ExpressionVisitor::ValidateMetaDataAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0x1781a  ldarg.1
0x1781b  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x17820  ldarg.0
0x17821  callvirt instance void Microsoft.Crm.Query.Expression::Deserialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x17826  ldarg.0
0x17827  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x1782c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements()
0x17831  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x17836  stloc.s  0xA
0x17838  br       loc_1799C
0x1783d  ldloc.s  0xA
0x1783f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x17844  stloc.s  0xB
0x17846  ldloc.s  0xB
0x17848  isinst   [System.Xml.Linq]System.Xml.Linq.XElement
0x1784d  stloc.s  0xC
0x1784f  ldloc.s  0xC
0x17851  brfalse  loc_1799C
0x17856  ldarg.0
0x17857  ldloc.s  0xC
0x17859  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x1785e  ldloc.s  0xC
0x17860  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x17865  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XName::get_LocalName()
0x1786a  stloc.s  0xD
0x1786c  ldloc.s  0xD
0x1786e  ldstr    aAttribute_0// "attribute"
0x17873  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17878  brtrue   loc_1799C
0x1787d  ldloc.s  0xD
0x1787f  ldstr    aAllAttributes// "all-attributes"
0x17884  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17889  brtrue   loc_1799C
0x1788e  ldloc.s  0xD
0x17890  ldstr    aNoAttrs// "no-attrs"
0x17895  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1789a  brtrue   loc_1799C
0x1789f  ldloc.s  0xD
0x178a1  ldstr    aFilter// "filter"
0x178a6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x178ab  brtrue.s loc_178CE
0x178ad  ldloc.s  0xD
0x178af  ldstr    aOrder// "order"
0x178b4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x178b9  brtrue.s loc_1790A
0x178bb  ldloc.s  0xD
0x178bd  ldstr    aLinkEntity// "link-entity"
0x178c2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x178c7  brtrue.s loc_1791B
0x178c9  br       loc_17968
0x178ce  ldarg.0
0x178cf  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x178d4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x178d9  ldarg.1
0x178da  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext Microsoft.Crm.Query.Expression::get_UserAndOrganizationContext()
0x178df  ldarg.1
0x178e0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Query.Expression::get_Cache()
0x178e5  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x178ea  stloc.s  0xE
0x178ec  ldloc.s  0xE
0x178ee  ldarg.0
0x178ef  callvirt instance void Microsoft.Crm.Query.Expression::Deserialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x178f4  ldarg.1
0x178f5  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x178fa  ldloc.s  0xE
0x178fc  callvirt instance void Microsoft.Crm.Query.FilterExpression::AddFilter(class Microsoft.Crm.Query.FilterExpression childFilter)
0x17901  ldloc.2
0x17902  ldc.i4.1
0x17903  add
0x17904  stloc.2
0x17905  br       loc_1799C
0x1790a  ldarg.1
0x1790b  callvirt instance class Microsoft.Crm.Query.OrderExpression Microsoft.Crm.Query.LinkEntityExpression::get_Order()
0x17910  ldarg.0
0x17911  callvirt instance void Microsoft.Crm.Query.Expression::Deserialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x17916  br       loc_1799C
0x1791b  ldarg.1
0x1791c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Query.Expression::get_Cache()
0x17921  ldarg.1
0x17922  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext Microsoft.Crm.Query.Expression::get_UserAndOrganizationContext()
0x17927  newobj   instance void Microsoft.Crm.Query.LinkEntityExpression::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x1792c  stloc.s  0xF
0x1792e  ldloc.s  0xF
0x17930  ldarg.1
0x17931  callvirt instance class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.LinkEntityExpression::get_ParentEntity()
0x17936  callvirt instance void Microsoft.Crm.Query.LinkEntityExpression::set_ParentEntity(class Microsoft.Crm.Query.EntityExpression value)
0x1793b  ldloc.s  0xF
0x1793d  ldarg.1
0x1793e  callvirt instance void Microsoft.Crm.Query.LinkEntityExpression::set_ParentLinkEntity(class Microsoft.Crm.Query.LinkEntityExpression value)
0x17943  ldloc.s  0xF
0x17945  ldarg.0
0x17946  callvirt instance void Microsoft.Crm.Query.Expression::Deserialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x1794b  ldarg.0
0x1794c  ldarg.1
0x1794d  stfld    class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::linkEntityExpression
0x17952  ldarg.0
0x17953  ldc.i4.1
0x17954  stfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bInLinkEntity
0x17959  ldarg.1
0x1795a  callvirt instance class Microsoft.Crm.Query.LinkEntityExpressionCollection Microsoft.Crm.Query.LinkEntityExpression::get_LinkedEntities()
0x1795f  ldloc.s  0xF
0x17961  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LinkEntityExpression>::Add(var<u1>)
0x17966  br.s     loc_1799C
0x17968  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1796d  ldstr    aInvalidChildNo_2// "Invalid Child Node, valid values are: f"...
0x17972  ldc.i4.2
0x17973  newarr   [mscorlib]System.Object
0x17978  dup
0x17979  ldc.i4.0
0x1797a  ldloc.s  0xC
0x1797c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x17981  stelem.ref
0x17982  dup
0x17983  ldc.i4.1
0x17984  ldloc.s  0xB
0x17986  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::OuterXml(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x1798b  stelem.ref
0x1798c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17991  ldc.i4   0x8004111C
0x17996  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1799b  throw
0x1799c  ldloc.s  0xA
0x1799e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x179a3  brtrue   loc_1783D
0x179a8  leave.s  loc_179B6
0x179aa  ldloc.s  0xA
0x179ac  brfalse.s loc_179B5
0x179ae  ldloc.s  0xA
0x179b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x179b5  endfinally
0x179b6  ldloc.2
0x179b7  ldc.i4.1
0x179b8  bne.un.s loc_179F3
0x179ba  ldarg.0
0x179bb  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x179c0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x179c5  ldarg.1
0x179c6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext Microsoft.Crm.Query.Expression::get_UserAndOrganizationContext()
  ... truncated ...
```
