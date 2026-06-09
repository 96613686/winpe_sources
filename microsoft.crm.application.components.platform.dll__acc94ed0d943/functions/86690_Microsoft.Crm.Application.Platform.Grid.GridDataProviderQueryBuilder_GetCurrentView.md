# Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::GetCurrentView

- ea: `0x86690`
- end: `0x86827`
- name: `Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::GetCurrentView`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5320`
- `0x5520`
- `0x5610`
- `0x56d0`
- `0x15a00`
- `0x84e00`
- `0x86690`

## string_xrefs

- `0x866e2`: `layoutXml`
- `0x86710`: `layoutXml`
- `0x8672e`: `fetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x86690  ldloca.s 0
0x86692  ldarg.0
0x86693  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86698  ldstr    aViewid// "viewid"
0x8669d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x866a2  call     instance void [mscorlib]System.Guid::.ctor(string)
0x866a7  ldloc.0
0x866a8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x866ad  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x866b2  brfalse.s loc_866D6
0x866b4  ldloc.0
0x866b5  ldarg.0
0x866b6  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x866bb  ldstr    aViewtype// "viewtype"
0x866c0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x866c5  ldc.i4.7
0x866c6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x866cb  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x866d0  call     class Microsoft.Crm.View Microsoft.Crm.Caching.ViewLoader::GetView(valuetype [mscorlib]System.Guid viewId, valuetype Microsoft.Crm.ViewType viewType)
0x866d5  ret
0x866d6  newobj   instance void Microsoft.Crm.ViewDetails::.ctor()
0x866db  stloc.1
0x866dc  ldarg.0
0x866dd  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x866e2  ldstr    aLayoutxml_0// "layoutXml"
0x866e7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x866ec  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x866f1  stloc.2
0x866f2  ldloc.1
0x866f3  ldarg.0
0x866f4  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x866f9  ldstr    aViewid_1// "viewId"
0x866fe  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x86703  stfld    string Microsoft.Crm.ViewDetails::ViewId
0x86708  ldloc.1
0x86709  ldloc.1
0x8670a  ldarg.0
0x8670b  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86710  ldstr    aLayoutxml_0// "layoutXml"
0x86715  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8671a  dup
0x8671b  stloc.3
0x8671c  stfld    string Microsoft.Crm.ViewDetails::HeaderXml
0x86721  ldloc.3
0x86722  stfld    string Microsoft.Crm.ViewDetails::ColumnXml
0x86727  ldloc.1
0x86728  ldarg.0
0x86729  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x8672e  ldstr    aFetchxml_0// "fetchXml"
0x86733  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x86738  stfld    string Microsoft.Crm.ViewDetails::FetchXml
0x8673d  ldloc.1
0x8673e  ldarg.0
0x8673f  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86744  ldstr    aObjecttype// "ObjectType"
0x86749  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8674e  stfld    string Microsoft.Crm.ViewDetails::ObjectTypeCode
0x86753  ldloc.1
0x86754  ldstr    asc_A9652// ""
0x86759  stfld    string Microsoft.Crm.ViewDetails::QueryApi
0x8675e  ldloc.1
0x8675f  ldloc.2
0x86760  ldstr    aGrid// "grid"
0x86765  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8676a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8676f  ldstr    aIcon// "icon"
0x86774  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x86779  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8677e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86783  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x86788  ldc.i4.1
0x86789  ceq
0x8678b  stfld    bool Microsoft.Crm.ViewDetails::EnableIcon
0x86790  ldloc.1
0x86791  ldloc.2
0x86792  ldstr    aGrid// "grid"
0x86797  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8679c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x867a1  ldstr    aPreview// "preview"
0x867a6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x867ab  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x867b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x867b5  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x867ba  ldc.i4.1
0x867bb  ceq
0x867bd  stfld    bool Microsoft.Crm.ViewDetails::EnablePreview
0x867c2  ldloc.1
0x867c3  ldstr    asc_A9652// ""
0x867c8  stfld    string Microsoft.Crm.ViewDetails::MultiObjectTypeCodeColumnName
0x867cd  ldloc.1
0x867ce  ldc.i4.0
0x867cf  stfld    int32 Microsoft.Crm.ViewDetails::QueryType
0x867d4  ldloc.1
0x867d5  ldloc.2
0x867d6  ldstr    aGridRow// "grid/row"
0x867db  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x867e0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x867e5  ldstr    aId// "id"
0x867ea  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x867ef  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x867f4  stfld    string Microsoft.Crm.ViewDetails::IdColumnName
0x867f9  ldloc.1
0x867fa  ldfld    string Microsoft.Crm.ViewDetails::FetchXml
0x867ff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x86804  brtrue.s loc_86814
0x86806  ldloc.1
0x86807  ldloc.1
0x86808  ldfld    string Microsoft.Crm.ViewDetails::FetchXml
0x8680d  callvirt instance void Microsoft.Crm.ViewDetails::AddDefaultOrderFromFetchXml(string fetchXml)
0x86812  br.s     loc_86820
0x86814  ldloc.1
0x86815  ldloc.1
0x86816  ldfld    string Microsoft.Crm.ViewDetails::ColumnXml
0x8681b  callvirt instance void Microsoft.Crm.ViewDetails::AddDefaultOrderFromColumnXml(string columnXml)
0x86820  ldloc.1
0x86821  newobj   instance void Microsoft.Crm.View::.ctor(class Microsoft.Crm.ViewDetails defaultDetails)
0x86826  ret
```
