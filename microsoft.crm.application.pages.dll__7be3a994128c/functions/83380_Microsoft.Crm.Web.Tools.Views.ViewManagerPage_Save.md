# Microsoft.Crm.Web.Tools.Views.ViewManagerPage::Save

- ea: `0x83380`
- end: `0x83822`
- name: `Microsoft.Crm.Web.Tools.Views.ViewManagerPage::Save`
- size: `1186`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x83380`
- `0x83830`
- `0x838d0`
- `0x83b60`
- `0x83d30`

## string_xrefs

- `0x83386`: `layoutxml`
- `0x83419`: `layoutxml`
- `0x8373d`: `layoutxml`
- `0x834b4`: `crmFormSubmitFetchXml`
- `0x835ac`: `<columnsetxml></columnsetxml>`
- `0x83755`: `<columnsetxml></columnsetxml>`
- `0x835d6`: `<columnsetxml>`
- `0x835ec`: `</columnsetxml>`
- `0x8360e`: `<fetchxml>`
- `0x8361a`: `</fetchxml>`
- `0x8363d`: `crmFormSubmitHiddenColumnsXml`

## pseudocode

```c

```

## disassembly

```asm
0x83380  ldarg.2
0x83381  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x83386  ldstr    aLayoutxml_1// "layoutxml"
0x8338b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x83390  isinst   [mscorlib]System.String
0x83395  stloc.0
0x83396  ldarg.0
0x83397  ldloc.0
0x83398  brfalse.s loc_8339D
0x8339a  ldloc.0
0x8339b  br.s     loc_833A2
0x8339d  ldsfld   string [mscorlib]System.String::Empty
0x833a2  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x833a7  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_gridXmlDoc
0x833ac  ldarg.0
0x833ad  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_gridXmlDoc
0x833b2  ldstr    aGridRowCellLab// "/grid/row/cell[@LabelId]"
0x833b7  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x833bc  stloc.s  6
0x833be  ldloc.s  6
0x833c0  brfalse.s loc_8342E
0x833c2  ldloc.s  6
0x833c4  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x833c9  stloc.s  7
0x833cb  br.s     loc_833E9
0x833cd  ldloc.s  7
0x833cf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x833d4  castclass [System.Xml]System.Xml.XmlNode
0x833d9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x833de  ldstr    aLabel// "label"
0x833e3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::RemoveNamedItem(string)
0x833e8  pop
0x833e9  ldloc.s  7
0x833eb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x833f0  brtrue.s loc_833CD
0x833f2  leave.s  loc_83409
0x833f4  ldloc.s  7
0x833f6  isinst   [mscorlib]System.IDisposable
0x833fb  stloc.s  8
0x833fd  ldloc.s  8
0x833ff  brfalse.s loc_83408
0x83401  ldloc.s  8
0x83403  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x83408  endfinally
0x83409  ldloc.s  6
0x8340b  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x83410  ldc.i4.0
0x83411  ble.s    loc_8342E
0x83413  ldarg.2
0x83414  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x83419  ldstr    aLayoutxml_1// "layoutxml"
0x8341e  ldarg.0
0x8341f  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_gridXmlDoc
0x83424  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x83429  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x8342e  leave.s  loc_8343C
0x83430  ldloc.s  6
0x83432  brfalse.s loc_8343B
0x83434  ldloc.s  6
0x83436  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8343b  endfinally
0x8343c  ldarg.0
0x8343d  ldarg.0
0x8343e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x83443  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x83448  ldstr    aCrmformsubmito// "crmFormSubmitObjectTypeCode"
0x8344d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x83452  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x83457  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x8345c  stfld    int32 Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_viewObjectType
0x83461  ldarg.0
0x83462  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x83467  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x8346c  ldstr    aCrmformsubmitq// "crmFormSubmitQueryType"
0x83471  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x83476  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8347b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x83480  stloc.1
0x83481  ldarg.0
0x83482  call     instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::GetForm()
0x83487  ldarg.2
0x83488  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x8348d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x83492  stloc.2
0x83493  ldarg.2
0x83494  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x83499  ldstr    aQueryapi// "queryapi"
0x8349e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x834a3  isinst   [mscorlib]System.String
0x834a8  stloc.3
0x834a9  ldarg.0
0x834aa  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x834af  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x834b4  ldstr    aCrmformsubmitf// "crmFormSubmitFetchXml"
0x834b9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x834be  stloc.s  4
0x834c0  ldsfld   string [mscorlib]System.String::Empty
0x834c5  stloc.s  5
0x834c7  ldloc.3
0x834c8  brtrue.s loc_834D0
0x834ca  ldsfld   string [mscorlib]System.String::Empty
0x834cf  stloc.3
0x834d0  ldloc.1
0x834d1  ldc.i4.s 0x40
0x834d3  beq      loc_8360C
0x834d8  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x834dd  stloc.s  9
0x834df  ldarg.0
0x834e0  ldloc.s  4
0x834e2  ldloca.s 9
0x834e4  call     instance string Microsoft.Crm.Web.Tools.Views.ViewManagerPage::ValidateFetchXmlColumns(string fetchXml, class [mscorlib]System.Collections.Hashtable& validColumns)
0x834e9  stloc.s  4
0x834eb  ldloc.3
0x834ec  brfalse  loc_8359F
0x834f1  ldloc.3
0x834f2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x834f7  brfalse  loc_8359F
0x834fc  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewDetails::.ctor()
0x83501  stloc.s  0xA
0x83503  ldloc.s  0xA
0x83505  ldloc.s  4
0x83507  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewDetails::AddDefaultOrderFromFetchXml(string)
0x8350c  ldloc.s  0xA
0x8350e  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewDetails::get_DefaultSortColumns()
0x83513  brfalse  loc_8359F
0x83518  ldloc.s  0xA
0x8351a  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewDetails::get_DefaultSortColumns()
0x8351f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::get_Count()
0x83524  ldc.i4.0
0x83525  ble.s    loc_8359F
0x83527  ldc.i4.0
0x83528  stloc.s  0xB
0x8352a  br.s     loc_8358F
0x8352c  ldloc.s  0xA
0x8352e  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewDetails::get_SortDir()
0x83533  ldloc.s  0xB
0x83535  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::get_Item(!!T0)
0x8353a  stloc.s  0xC
0x8353c  ldc.i4.8
0x8353d  newarr   [mscorlib]System.String
0x83542  dup
0x83543  ldc.i4.0
0x83544  ldloc.s  5
0x83546  stelem.ref
0x83547  dup
0x83548  ldc.i4.1
0x83549  ldstr    asc_121D9A// "<"
0x8354e  stelem.ref
0x8354f  dup
0x83550  ldc.i4.2
0x83551  ldloc.s  0xC
0x83553  stelem.ref
0x83554  dup
0x83555  ldc.i4.3
0x83556  ldstr    asc_121FAC// ">"
0x8355b  stelem.ref
0x8355c  dup
0x8355d  ldc.i4.4
0x8355e  ldloc.s  0xA
0x83560  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewDetails::get_DefaultSortColumns()
0x83565  ldloc.s  0xB
0x83567  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::get_Item(!!T0)
0x8356c  stelem.ref
0x8356d  dup
0x8356e  ldc.i4.5
0x8356f  ldstr    asc_121DB4// "</"
0x83574  stelem.ref
0x83575  dup
0x83576  ldc.i4.6
0x83577  ldloc.s  0xC
0x83579  stelem.ref
0x8357a  dup
0x8357b  ldc.i4.7
0x8357c  ldstr    asc_121FAC// ">"
0x83581  stelem.ref
0x83582  call     string [mscorlib]System.String::Concat(string[])
0x83587  stloc.s  5
0x83589  ldloc.s  0xB
0x8358b  ldc.i4.1
0x8358c  add
0x8358d  stloc.s  0xB
0x8358f  ldloc.s  0xB
0x83591  ldloc.s  0xA
0x83593  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewDetails::get_DefaultSortColumns()
0x83598  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::get_Count()
0x8359d  blt.s    loc_8352C
0x8359f  ldloc.3
0x835a0  brfalse.s loc_835AA
0x835a2  ldloc.3
0x835a3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x835a8  brtrue.s loc_835B8
0x835aa  ldloca.s 2
0x835ac  ldstr    aColumnsetxmlCo// "<columnsetxml></columnsetxml>"
0x835b1  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendInnerXml(string&, string)
0x835b6  br.s     loc_835FB
0x835b8  ldarg.0
0x835b9  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_gridXmlDoc
0x835be  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x835c3  ldstr    aRow_1// "row"
0x835c8  ldstr    aId// "id"
0x835cd  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAttrValue(string, string, string)
0x835d2  stloc.s  0xD
0x835d4  ldloca.s 2
0x835d6  ldstr    aColumnsetxml_0// "<columnsetxml>"
0x835db  ldarg.0
0x835dc  ldloc.s  9
0x835de  ldloc.s  5
0x835e0  ldloc.s  0xD
0x835e2  call     instance string Microsoft.Crm.Web.Tools.Views.ViewManagerPage::GenerateColumnsXml(class [mscorlib]System.Collections.Hashtable validColumns, string apiSortTag, string idColumnName)
0x835e7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x835ec  ldstr    aColumnsetxml_1// "</columnsetxml>"
0x835f1  call     string [mscorlib]System.String::Concat(string, string, string)
0x835f6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendInnerXml(string&, string)
0x835fb  ldloc.2
0x835fc  ldstr    aMultiobjectidf// "multiobjectidfield&#x3D;&#x22;&#x22;"
0x83601  ldstr    asc_11EF2A// ""
0x83606  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8360b  stloc.2
0x8360c  ldloca.s 2
0x8360e  ldstr    aFetchxml_3// "<fetchxml>"
0x83613  ldloc.s  4
0x83615  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x8361a  ldstr    aFetchxml_4// "</fetchxml>"
0x8361f  call     string [mscorlib]System.String::Concat(string, string, string)
0x83624  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendInnerXml(string&, string)
0x83629  ldloc.1
0x8362a  ldc.i4.s 0x40
0x8362c  bne.un   loc_8375F
0x83631  ldarg.0
0x83632  ldarg.0
0x83633  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x83638  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x8363d  ldstr    aCrmformsubmith// "crmFormSubmitHiddenColumnsXml"
0x83642  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x83647  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlDecode(string)
0x8364c  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x83651  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_hiddenColumnsXmlDoc
0x83656  ldarg.0
0x83657  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_hiddenColumnsXmlDoc
0x8365c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x83661  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x83666  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x8366b  stloc.s  7
0x8366d  br       loc_83719
0x83672  ldloc.s  7
0x83674  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x83679  castclass [System.Xml]System.Xml.XmlNode
0x8367e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x83683  stloc.s  0xE
0x83685  ldarg.0
0x83686  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_gridXmlDoc
0x8368b  ldstr    aGridRow// "/grid/row"
0x83690  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x83695  stloc.s  0xF
0x83697  ldloc.s  0xF
0x83699  ldstr    aCellName// "cell[@name = '"
0x8369e  ldloc.s  0xE
0x836a0  ldstr    asc_12DA3A// "']"
0x836a5  call     string [mscorlib]System.String::Concat(string, string, string)
0x836aa  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x836af  castclass [System.Xml]System.Xml.XmlElement
0x836b4  stloc.s  0x10
0x836b6  ldloc.s  0x10
0x836b8  brtrue.s loc_83708
0x836ba  ldarg.0
0x836bb  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_gridXmlDoc
0x836c0  ldstr    aCell_0// "cell"
0x836c5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x836ca  stloc.s  0x10
0x836cc  ldloc.s  0x10
0x836ce  ldstr    aName// "name"
0x836d3  ldloc.s  0xE
0x836d5  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x836da  ldloc.s  0x10
0x836dc  ldstr    aIshidden_0// "ishidden"
0x836e1  ldstr    a1// "1"
0x836e6  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x836eb  ldloc.s  0x10
0x836ed  ldstr    aWidth_0// "width"
0x836f2  ldstr    a100_0// "100"
0x836f7  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x836fc  ldloc.s  0xF
0x836fe  ldloc.s  0x10
0x83700  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x83705  pop
0x83706  br.s     loc_83719
0x83708  ldloc.s  0x10
0x8370a  ldstr    aIshidden_0// "ishidden"
0x8370f  ldstr    a0_1// "0"
0x83714  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x83719  ldloc.s  7
0x8371b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x83720  brtrue   loc_83672
0x83725  leave.s  loc_8373C
0x83727  ldloc.s  7
0x83729  isinst   [mscorlib]System.IDisposable
0x8372e  stloc.s  8
0x83730  ldloc.s  8
0x83732  brfalse.s loc_8373B
0x83734  ldloc.s  8
  ... truncated ...
```
