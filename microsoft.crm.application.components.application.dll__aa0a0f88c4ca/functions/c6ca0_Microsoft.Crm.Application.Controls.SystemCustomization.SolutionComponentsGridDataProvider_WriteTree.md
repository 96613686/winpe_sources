# Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::WriteTree

- ea: `0xc6ca0`
- end: `0xc6e0d`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::WriteTree`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xc6980`

## callees

- `0x46e30`
- `0xc6ca0`
- `0xc6ee0`
- `0xc7240`
- `0xc7320`
- `0xc85c0`

## string_xrefs

- `0xc6d23`: `areaSolutionComponent`
- `0xc6dc7`: `areaSolutionComponent`
- `0xc6d69`: `solutioncomponenttype`

## pseudocode

```c

```

## disassembly

```asm
0xc6ca0  ldnull
0xc6ca1  stloc.0
0xc6ca2  ldarg.s  5
0xc6ca4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc6ca9  brtrue.s loc_C6CB5
0xc6cab  ldarg.0
0xc6cac  ldarg.s  5
0xc6cae  ldarg.2
0xc6caf  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>> Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetSolutionComponentsRows(string solutionId, int32 componentType)
0xc6cb4  stloc.0
0xc6cb5  ldarg.1
0xc6cb6  ldstr    aNode// "node"
0xc6cbb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xc6cc0  ldarg.0
0xc6cc1  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc6cc6  ldstr    aDefCategory// "def_category"
0xc6ccb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc6cd0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc6cd5  brtrue.s loc_C6D0C
0xc6cd7  ldarg.0
0xc6cd8  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc6cdd  ldstr    aDefCategory// "def_category"
0xc6ce2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc6ce7  ldarga.s 3
0xc6ce9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6cee  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6cf3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc6cf8  brfalse.s loc_C6D0C
0xc6cfa  ldarg.1
0xc6cfb  ldstr    aExpanded// "expanded"
0xc6d00  ldstr    aTrue// "true"
0xc6d05  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6d0a  br.s     loc_C6D1C
0xc6d0c  ldarg.1
0xc6d0d  ldstr    aExpanded// "expanded"
0xc6d12  ldstr    aFalse// "false"
0xc6d17  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6d1c  ldarg.1
0xc6d1d  ldstr    aAction// "action"
0xc6d22  ldarg.0
0xc6d23  ldstr    aAreasolutionco// "areaSolutionComponent"
0xc6d28  ldarg.2
0xc6d29  ldc.i4.0
0xc6d2a  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetGroupAction(string tabset, int32 solutionComponentType, [opt] bool isMetadataDrivenDialog)
0xc6d2f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6d34  ldarg.1
0xc6d35  ldstr    aType// "type"
0xc6d3a  ldc.i4   0x1BBF
0xc6d3f  stloc.1
0xc6d40  ldloca.s 1
0xc6d42  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6d47  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6d4c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6d51  ldarg.1
0xc6d52  ldstr    aCode// "code"
0xc6d57  ldarga.s 3
0xc6d59  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6d5e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6d63  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6d68  ldarg.1
0xc6d69  ldstr    aSolutioncompon_2// "solutioncomponenttype"
0xc6d6e  ldarga.s 2
0xc6d70  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6d75  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6d7a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6d7f  ldarg.1
0xc6d80  ldstr    aDisplayname// "displayname"
0xc6d85  ldarg.3
0xc6d86  ldc.i4.2
0xc6d87  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0xc6d8c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6d91  ldarg.1
0xc6d92  ldstr    aId_1// "id"
0xc6d97  ldarg.0
0xc6d98  ldarg.3
0xc6d99  ldnull
0xc6d9a  ldnull
0xc6d9b  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetNodeId(int32 category, string name, string element)
0xc6da0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6da5  ldarg.1
0xc6da6  ldstr    aIcon_0// "icon"
0xc6dab  ldarg.3
0xc6dac  ldc.i4.0
0xc6dad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6db2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6db7  callvirt instance string [mscorlib]System.Object::ToString()
0xc6dbc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6dc1  ldarg.1
0xc6dc2  ldstr    aTabset_0// "tabset"
0xc6dc7  ldstr    aAreasolutionco// "areaSolutionComponent"
0xc6dcc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6dd1  ldloc.0
0xc6dd2  brfalse.s loc_C6E0C
0xc6dd4  ldloc.0
0xc6dd5  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::get_Count()
0xc6dda  ldc.i4.0
0xc6ddb  ble.s    loc_C6E0C
0xc6ddd  ldloc.0
0xc6dde  ldarg.3
0xc6ddf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::get_Item(void)
0xc6de4  castclass class [mscorlib]System.Collections.Generic.List`1<class Row>
0xc6de9  ldnull
0xc6dea  ldftn    int32 Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::CompareByDisplayName(class Row x, class Row y)
0xc6df0  newobj   instance void class [mscorlib]System.Comparison`1<class Row>::.ctor(object, native int)
0xc6df5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Row>::Sort(class [mscorlib]System.Comparison`1<var<u1>>)
0xc6dfa  ldarg.0
0xc6dfb  ldarg.1
0xc6dfc  ldloc.0
0xc6dfd  ldarg.3
0xc6dfe  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::get_Item(void)
0xc6e03  ldarg.s  4
0xc6e05  ldc.i4.1
0xc6e06  add
0xc6e07  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::WriteComponent(class [System.Xml]System.Xml.XmlWriter writer, class [mscorlib]System.Collections.Generic.IList`1<class Row> rows, int32 level)
0xc6e0c  ret
```
