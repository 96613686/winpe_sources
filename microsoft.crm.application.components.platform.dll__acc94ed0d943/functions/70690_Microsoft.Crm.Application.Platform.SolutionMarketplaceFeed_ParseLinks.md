# Microsoft.Crm.Application.Platform.SolutionMarketplaceFeed::ParseLinks

- ea: `0x70690`
- end: `0x7086d`
- name: `Microsoft.Crm.Application.Platform.SolutionMarketplaceFeed::ParseLinks`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x70530`

## callees

- `0x70690`
- `0x70870`
- `0x708f0`
- `0x70980`
- `0x70a00`
- `0x70a20`
- `0x70a80`

## string_xrefs

- `0x706e0`: `http://schemas.microsoft.com/ado/2007/08/dataservices`
- `0x7076e`: `http://schemas.microsoft.com/ado/2007/08/dataservices`
- `0x707a4`: `http://schemas.microsoft.com/ado/2007/08/dataservices`
- `0x707d7`: `http://schemas.microsoft.com/ado/2007/08/dataservices`
- `0x7081f`: `http://schemas.microsoft.com/ado/2007/08/dataservices`
- `0x70720`: `LINKS:PINPOINTPRODUCTPAGE`
- `0x7072d`: `LINKS:PINPOINTPARTNERREVIEWPAGE`
- `0x7073a`: `LINKS:PINPOINTPRODUCTREVIEWPAGE`
- `0x70747`: `LINKS:PARTNERLOGO`
- `0x70754`: `LINKS:PARTNERWEBSITE`

## pseudocode

```c

```

## disassembly

```asm
0x70690  ldarg.2
0x70691  ldstr    aEntry// "entry"
0x70696  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2005/Atom"
0x7069b  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::SelectChildren(string, string)
0x706a0  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XPath.XPathNodeIterator::GetEnumerator()
0x706a5  stloc.0
0x706a6  br       loc_7084A
0x706ab  ldloc.0
0x706ac  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x706b1  castclass [System.Xml]System.Xml.XPath.XPathNavigator
0x706b6  stloc.1
0x706b7  ldloc.1
0x706b8  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::get_HasChildren()
0x706bd  brfalse  loc_7084A
0x706c2  ldloc.1
0x706c3  ldstr    aContent// "content"
0x706c8  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2005/Atom"
0x706cd  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToChild(string, string)
0x706d2  pop
0x706d3  ldloc.1
0x706d4  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0x706d9  pop
0x706da  ldloc.1
0x706db  ldstr    aType_0// "Type"
0x706e0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/ado/2007/0"...
0x706e5  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToChild(string, string)
0x706ea  pop
0x706eb  ldloc.1
0x706ec  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x706f1  callvirt instance string [mscorlib]System.Object::ToString()
0x706f6  callvirt instance string [mscorlib]System.String::Trim()
0x706fb  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x70700  stloc.2
0x70701  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x70706  ldstr    a01_10// "{0}:{1}"
0x7070b  ldc.i4.2
0x7070c  newarr   [mscorlib]System.Object
0x70711  dup
0x70712  ldc.i4.0
0x70713  ldarg.0
0x70714  stelem.ref
0x70715  dup
0x70716  ldc.i4.1
0x70717  ldloc.2
0x70718  stelem.ref
0x70719  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7071e  stloc.2
0x7071f  ldloc.2
0x70720  ldstr    aLinksPinpointp// "LINKS:PINPOINTPRODUCTPAGE"
0x70725  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7072a  brtrue.s loc_70768
0x7072c  ldloc.2
0x7072d  ldstr    aLinksPinpointp_0// "LINKS:PINPOINTPARTNERREVIEWPAGE"
0x70732  call     bool [mscorlib]System.String::op_Equality(string, string)
0x70737  brtrue.s loc_7079E
0x70739  ldloc.2
0x7073a  ldstr    aLinksPinpointp_1// "LINKS:PINPOINTPRODUCTREVIEWPAGE"
0x7073f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x70744  brtrue.s loc_7079E
0x70746  ldloc.2
0x70747  ldstr    aLinksPartnerlo// "LINKS:PARTNERLOGO"
0x7074c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x70751  brtrue.s loc_707D1
0x70753  ldloc.2
0x70754  ldstr    aLinksPartnerwe// "LINKS:PARTNERWEBSITE"
0x70759  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7075e  brtrue   loc_70819
0x70763  br       loc_7084A
0x70768  ldloc.1
0x70769  ldstr    aUrl// "Url"
0x7076e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/ado/2007/0"...
0x70773  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext(string, string)
0x70778  pop
0x70779  ldarg.1
0x7077a  ldloc.1
0x7077b  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x70780  callvirt instance string [mscorlib]System.Object::ToString()
0x70785  callvirt instance string [mscorlib]System.String::Trim()
0x7078a  call     string Microsoft.Crm.Application.Platform.SolutionMarketplaceFeed::TempFixLink(string link)
0x7078f  newobj   instance void [System]System.Uri::.ctor(string)
0x70794  callvirt instance void Microsoft.Crm.Application.Platform.FeedItem::set_ProductUrl(class [System]System.Uri value)
0x70799  br       loc_7084A
0x7079e  ldloc.1
0x7079f  ldstr    aUrl// "Url"
0x707a4  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/ado/2007/0"...
0x707a9  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext(string, string)
0x707ae  pop
0x707af  ldarg.1
0x707b0  ldloc.1
0x707b1  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x707b6  callvirt instance string [mscorlib]System.Object::ToString()
0x707bb  callvirt instance string [mscorlib]System.String::Trim()
0x707c0  call     string Microsoft.Crm.Application.Platform.SolutionMarketplaceFeed::TempFixLink(string link)
0x707c5  newobj   instance void [System]System.Uri::.ctor(string)
0x707ca  callvirt instance void Microsoft.Crm.Application.Platform.FeedItem::set_ReviewsUrl(class [System]System.Uri value)
0x707cf  br.s     loc_7084A
0x707d1  ldloc.1
0x707d2  ldstr    aUrl// "Url"
0x707d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/ado/2007/0"...
0x707dc  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext(string, string)
0x707e1  pop
0x707e2  ldnull
0x707e3  stloc.3
0x707e4  ldloc.1
0x707e5  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x707ea  callvirt instance string [mscorlib]System.Object::ToString()
0x707ef  callvirt instance string [mscorlib]System.String::Trim()
0x707f4  call     string Microsoft.Crm.Application.Platform.SolutionMarketplaceFeed::TempFixLink(string link)
0x707f9  ldc.i4.1
0x707fa  ldloca.s 3
0x707fc  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x70801  pop
0x70802  ldloc.3
0x70803  ldnull
0x70804  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x70809  brfalse.s loc_7084A
0x7080b  ldarg.1
0x7080c  ldloc.3
0x7080d  call     class [System]System.Uri Microsoft.Crm.Application.Platform.SolutionMarketplaceFeed::RetrieveImageUrlIfSecure(class [System]System.Uri logoUrl)
0x70812  callvirt instance void Microsoft.Crm.Application.Platform.FeedItem::set_LogoUrl(class [System]System.Uri value)
0x70817  br.s     loc_7084A
0x70819  ldloc.1
0x7081a  ldstr    aUrl// "Url"
0x7081f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/ado/2007/0"...
0x70824  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext(string, string)
0x70829  pop
0x7082a  ldarg.1
0x7082b  ldloc.1
0x7082c  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x70831  callvirt instance string [mscorlib]System.Object::ToString()
0x70836  callvirt instance string [mscorlib]System.String::Trim()
0x7083b  call     string Microsoft.Crm.Application.Platform.SolutionMarketplaceFeed::TempFixLink(string link)
0x70840  newobj   instance void [System]System.Uri::.ctor(string)
0x70845  callvirt instance void Microsoft.Crm.Application.Platform.FeedItem::set_PartnerWebsite(class [System]System.Uri value)
0x7084a  ldloc.0
0x7084b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x70850  brtrue   loc_706AB
0x70855  leave.s  loc_7086B
0x70857  ldloc.0
0x70858  isinst   [mscorlib]System.IDisposable
0x7085d  stloc.s  4
0x7085f  ldloc.s  4
0x70861  brfalse.s loc_7086A
0x70863  ldloc.s  4
0x70865  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7086a  endfinally
0x7086b  ldarg.1
0x7086c  ret
```
