# Microsoft.Crm.Query.DeserializeFetchVisitor::Visit_5

- ea: `0x17110`
- end: `0x17651`
- name: `Microsoft.Crm.Query.DeserializeFetchVisitor::Visit_5`
- size: `1345`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `registry_config, broker_com_uri`

## callees

- `0x13ee0`
- `0x17110`
- `0x17db0`
- `0x17e20`
- `0x184b0`
- `0x184e0`
- `0x184f0`
- `0x18520`
- `0x18540`
- `0x18550`
- `0x18560`
- `0x18570`
- `0x185b0`
- `0x185c0`
- `0x185d0`
- `0x185e0`
- `0x186f0`
- `0x18710`
- `0x18770`
- `0x18790`
- `0x1a860`
- `0x1a8f0`
- `0x1a930`
- `0x1a9b0`
- `0x1aa70`
- `0x1ab40`
- `0x1afa0`
- `0x1b250`
- `0x1b2d0`
- `0x1d340`
- `0x1d500`
- `0x1d650`
- `0x21bf0`
- `0x21c10`
- `0x52e60`
- `0x52eb0`
- `0x6ca90`

## string_xrefs

- `0x17437`: `link-entity`
- `0x174f8`: `link-entity`
- `0x17587`: `Invalid Child Node, valid nodes are filter, order, link-entity, attribute, all-attributes, no-attrs. NodeName = {0} NodeXml = {1}`

## pseudocode

```c

```

## disassembly

```asm
0x17110  ldarg.1
0x17111  ldc.i4.0
0x17112  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_QuerySource(valuetype Microsoft.Crm.Query.QuerySourceType value)
0x17117  ldarg.0
0x17118  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::topElement
0x1711d  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x17122  ldstr    aFetch// "fetch"
0x17127  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x1712c  call     bool [System.Xml.Linq]System.Xml.Linq.XName::op_Inequality(class [System.Xml.Linq]System.Xml.Linq.XName, class [System.Xml.Linq]System.Xml.Linq.XName)
0x17131  brfalse.s loc_17169
0x17133  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17138  ldstr    aInvalidElement// "Invalid Element Name: {0}. Expecting: {"...
0x1713d  ldc.i4.2
0x1713e  newarr   [mscorlib]System.Object
0x17143  dup
0x17144  ldc.i4.0
0x17145  ldarg.0
0x17146  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::topElement
0x1714b  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x17150  stelem.ref
0x17151  dup
0x17152  ldc.i4.1
0x17153  ldstr    aFetch// "fetch"
0x17158  stelem.ref
0x17159  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1715e  ldc.i4   0x8004111C
0x17163  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x17168  throw
0x17169  ldarg.0
0x1716a  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x1716f  ldstr    aMapping// "mapping"
0x17174  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x17179  stloc.0
0x1717a  ldloc.0
0x1717b  brfalse.s loc_171BB
0x1717d  ldloc.0
0x1717e  ldstr    aLogical// "logical"
0x17183  callvirt instance bool [mscorlib]System.String::Equals(string)
0x17188  brtrue.s loc_171BB
0x1718a  ldloc.0
0x1718b  ldstr    aInternal// "internal"
0x17190  callvirt instance bool [mscorlib]System.String::Equals(string)
0x17195  brtrue.s loc_171BB
0x17197  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1719c  ldstr    aTheOnlyValidVa// "The only valid values for mapping are '"...
0x171a1  ldc.i4.1
0x171a2  newarr   [mscorlib]System.Object
0x171a7  dup
0x171a8  ldc.i4.0
0x171a9  ldloc.0
0x171aa  stelem.ref
0x171ab  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x171b0  ldc.i4   0x80041116
0x171b5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x171ba  throw
0x171bb  ldarg.0
0x171bc  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x171c1  ldstr    aAggregate// "aggregate"
0x171c6  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x171cb  stloc.1
0x171cc  ldloc.1
0x171cd  brfalse.s loc_171EA
0x171cf  ldloc.1
0x171d0  ldstr    aTrue// "true"
0x171d5  callvirt instance bool [mscorlib]System.String::Equals(string)
0x171da  brfalse.s loc_171EA
0x171dc  ldarg.0
0x171dd  ldc.i4.1
0x171de  stfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bHasAggregate
0x171e3  ldarg.1
0x171e4  ldc.i4.1
0x171e5  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_HasAggregates(bool value)
0x171ea  ldarg.0
0x171eb  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x171f0  ldstr    aDistinct// "distinct"
0x171f5  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x171fa  stloc.2
0x171fb  ldloc.2
0x171fc  brfalse.s loc_17222
0x171fe  ldarg.1
0x171ff  ldarg.0
0x17200  ldloc.2
0x17201  ldarg.0
0x17202  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x17207  ldc.i4   0x80041115
0x1720c  call     instance bool Microsoft.Crm.Query.DeserializeFetchVisitor::ParseFetchBool(string boolString, class [System.Xml.Linq]System.Xml.Linq.XElement node, int32 errorCode)
0x17211  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_Distinct(bool value)
0x17216  ldarg.0
0x17217  ldarg.1
0x17218  callvirt instance bool Microsoft.Crm.Query.EntityExpression::get_Distinct()
0x1721d  stfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bIsDistinct
0x17222  ldarg.0
0x17223  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x17228  ldstr    aTop// "top"
0x1722d  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x17232  stloc.3
0x17233  ldloc.3
0x17234  brfalse.s loc_1726E
0x17236  ldarg.0
0x17237  ldloc.3
0x17238  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1723d  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x17242  stfld    int32 Microsoft.Crm.Query.DeserializeFetchVisitor::topCount
0x17247  ldarg.0
0x17248  ldfld    int32 Microsoft.Crm.Query.DeserializeFetchVisitor::topCount
0x1724d  ldc.i4.0
0x1724e  call     int32 Microsoft.Crm.BusinessEntities.PagingHelper::get_RetrievalUpperLimitWithoutPagingCookie()
0x17253  ldstr    aTop// "top"
0x17258  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfOutOfRange(int32, int32, int32, string)
0x1725d  ldarg.1
0x1725e  callvirt instance class Microsoft.Crm.Query.TopExpression Microsoft.Crm.Query.EntityExpression::get_Top()
0x17263  ldarg.0
0x17264  ldfld    int32 Microsoft.Crm.Query.DeserializeFetchVisitor::topCount
0x17269  callvirt instance void Microsoft.Crm.Query.TopExpression::set_Count(int32 value)
0x1726e  ldarg.0
0x1726f  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x17274  ldstr    aNoLock// "no-lock"
0x17279  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x1727e  stloc.s  4
0x17280  ldloc.s  4
0x17282  brfalse.s loc_1729D
0x17284  ldarg.1
0x17285  ldarg.0
0x17286  ldloc.s  4
0x17288  ldarg.0
0x17289  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x1728e  ldc.i4   0x80041118
0x17293  call     instance bool Microsoft.Crm.Query.DeserializeFetchVisitor::ParseFetchBool(string boolString, class [System.Xml.Linq]System.Xml.Linq.XElement node, int32 errorCode)
0x17298  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_NoLock(bool value)
0x1729d  ldarg.0
0x1729e  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x172a3  ldstr    aMinActiveRowVe// "min-active-row-version"
0x172a8  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x172ad  stloc.s  5
0x172af  ldloc.s  5
0x172b1  brfalse.s loc_172CC
0x172b3  ldarg.1
0x172b4  ldarg.0
0x172b5  ldloc.s  5
0x172b7  ldarg.0
0x172b8  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x172bd  ldc.i4   0x8004111B
0x172c2  call     instance bool Microsoft.Crm.Query.DeserializeFetchVisitor::ParseFetchBool(string boolString, class [System.Xml.Linq]System.Xml.Linq.XElement node, int32 errorCode)
0x172c7  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_MinActiveRowVersion(bool value)
0x172cc  ldstr    aEnablenowtesth// "EnableNowTestHook"
0x172d1  ldc.i4.0
0x172d2  box      [mscorlib]System.Int32
0x172d7  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x172dc  unbox.any [mscorlib]System.Int32
0x172e1  ldc.i4.1
0x172e2  bne.un.s loc_17302
0x172e4  ldarg.0
0x172e5  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x172ea  ldstr    aNow// "now"
0x172ef  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x172f4  stloc.s  8
0x172f6  ldloc.s  8
0x172f8  brfalse.s loc_17302
0x172fa  ldarg.1
0x172fb  ldloc.s  8
0x172fd  callvirt instance void Microsoft.Crm.Query.EntityExpression::set_Now(string value)
0x17302  ldarg.0
0x17303  ldarg.1
0x17304  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x17309  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::entity
0x1730e  ldarg.0
0x1730f  ldarg.0
0x17310  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::entity
0x17315  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.DeserializeFetchVisitor::currentEntity
0x1731a  ldarg.0
0x1731b  ldarg.1
0x1731c  stfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x17321  ldc.i4.0
0x17322  stloc.s  6
0x17324  ldarg.1
0x17325  callvirt instance class Microsoft.Crm.Query.PagingInfo Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x1732a  ldarg.0
0x1732b  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::topElement
0x17330  callvirt instance void Microsoft.Crm.Query.PagingInfo::Deserialize(class [System.Xml.Linq]System.Xml.Linq.XElement element)
0x17335  ldarg.1
0x17336  callvirt instance bool Microsoft.Crm.Query.EntityExpression::get_HasAggregates()
0x1733b  brfalse.s loc_173BC
0x1733d  ldarg.0
0x1733e  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x17343  callvirt instance class Microsoft.Crm.Query.TopExpression Microsoft.Crm.Query.EntityExpression::get_Top()
0x17348  callvirt instance bool Microsoft.Crm.Query.TopExpression::get_CountIsSet()
0x1734d  brtrue.s loc_173BC
0x1734f  ldarg.0
0x17350  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x17355  callvirt instance class Microsoft.Crm.Query.PagingInfo Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x1735a  callvirt instance int32 Microsoft.Crm.Query.PagingInfo::get_DefaultMaxRowsPerPage()
0x1735f  stloc.s  9
0x17361  ldarg.0
0x17362  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x17367  callvirt instance class Microsoft.Crm.Query.PagingInfo Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x1736c  callvirt instance int32 Microsoft.Crm.Query.PagingInfo::get_Count()
0x17371  ldc.i4.0
0x17372  ble.s    loc_173AA
0x17374  ldarg.0
0x17375  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x1737a  callvirt instance class Microsoft.Crm.Query.PagingInfo Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x1737f  callvirt instance int32 Microsoft.Crm.Query.PagingInfo::get_Count()
0x17384  ldloc.s  9
0x17386  bgt.s    loc_173AA
0x17388  ldarg.0
0x17389  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x1738e  callvirt instance class Microsoft.Crm.Query.TopExpression Microsoft.Crm.Query.EntityExpression::get_Top()
0x17393  ldarg.0
0x17394  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x17399  callvirt instance class Microsoft.Crm.Query.PagingInfo Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x1739e  callvirt instance int32 Microsoft.Crm.Query.PagingInfo::get_Count()
0x173a3  callvirt instance void Microsoft.Crm.Query.TopExpression::set_Count(int32 value)
0x173a8  br.s     loc_173BC
0x173aa  ldarg.0
0x173ab  ldfld    class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.DeserializeFetchVisitor::entityExpression
0x173b0  callvirt instance class Microsoft.Crm.Query.TopExpression Microsoft.Crm.Query.EntityExpression::get_Top()
0x173b5  ldloc.s  9
0x173b7  callvirt instance void Microsoft.Crm.Query.TopExpression::set_Count(int32 value)
0x173bc  ldarg.0
0x173bd  ldarg.0
0x173be  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::topElement
0x173c3  ldstr    aFetchEntity// "/fetch/entity"
0x173c8  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElement(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x173cd  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x173d2  ldarg.1
0x173d3  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x173d8  ldarg.0
0x173d9  callvirt instance void Microsoft.Crm.Query.Expression::Deserialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x173de  ldarg.0
0x173df  ldarg.0
0x173e0  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::topElement
0x173e5  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x173ea  ldarg.0
0x173eb  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x173f0  ldstr    aEntity_0// "entity"
0x173f5  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x173fa  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x173ff  stloc.s  7
0x17401  ldloc.s  7
0x17403  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements()
0x17408  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x1740d  stloc.s  0xA
0x1740f  br.s     loc_17481
0x17411  ldloc.s  0xA
0x17413  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x17418  isinst   [System.Xml.Linq]System.Xml.Linq.XElement
0x1741d  stloc.s  0xB
0x1741f  ldloc.s  0xB
0x17421  brfalse.s loc_17481
0x17423  ldarg.0
0x17424  ldloc.s  0xB
0x17426  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Query.DeserializeFetchVisitor::currentElement
0x1742b  ldloc.s  0xB
0x1742d  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x17432  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XName::get_LocalName()
0x17437  ldstr    aLinkEntity// "link-entity"
0x1743c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17441  brfalse.s loc_17481
0x17443  ldarg.1
0x17444  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Query.Expression::get_Cache()
0x17449  ldarg.1
0x1744a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext Microsoft.Crm.Query.Expression::get_UserAndOrganizationContext()
0x1744f  newobj   instance void Microsoft.Crm.Query.LinkEntityExpression::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x17454  stloc.s  0xC
0x17456  ldloc.s  0xC
0x17458  ldarg.1
0x17459  callvirt instance void Microsoft.Crm.Query.LinkEntityExpression::set_ParentEntity(class Microsoft.Crm.Query.EntityExpression value)
0x1745e  ldarg.0
0x1745f  ldc.i4.1
0x17460  stfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::_processingLinkEntity
0x17465  ldloc.s  0xC
0x17467  ldarg.0
0x17468  callvirt instance void Microsoft.Crm.Query.Expression::Deserialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x1746d  ldarg.0
0x1746e  ldc.i4.0
0x1746f  stfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::_processingLinkEntity
0x17474  ldarg.1
0x17475  callvirt instance class Microsoft.Crm.Query.LinkEntityExpressionCollection Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x1747a  ldloc.s  0xC
0x1747c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.LinkEntityExpression>::Add(var<u1>)
0x17481  ldloc.s  0xA
0x17483  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17488  brtrue.s loc_17411
0x1748a  leave.s  loc_17498
0x1748c  ldloc.s  0xA
0x1748e  brfalse.s loc_17497
0x17490  ldloc.s  0xA
0x17492  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17497  endfinally
0x17498  ldloc.s  7
0x1749a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements()
0x1749f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x174a4  stloc.s  0xA
0x174a6  br       loc_175B6
0x174ab  ldloc.s  0xA
0x174ad  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x174b2  stloc.s  0xD
0x174b4  ldloc.s  0xD
0x174b6  isinst   [System.Xml.Linq]System.Xml.Linq.XElement
0x174bb  stloc.s  0xE
  ... truncated ...
```
