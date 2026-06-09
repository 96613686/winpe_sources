# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundDurationControl::RenderEditMode

- ea: `0x131a0`
- end: `0x138c3`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundDurationControl::RenderEditMode`
- size: `1827`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xab90`
- `0xaf80`
- `0x131a0`

## pseudocode

```c

```

## disassembly

```asm
0x131a0  ldarg.1
0x131a1  ldstr    aDiv// "div"
0x131a6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x131ab  ldarg.1
0x131ac  ldstr    aClass// "class"
0x131b1  ldstr    aMsCrmInlineEdi_1// "ms-crm-Inline-Edit"
0x131b6  ldc.i4.0
0x131b7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x131bc  ldarg.1
0x131bd  ldstr    aStyle// "style"
0x131c2  ldstr    aDisplayNone_0// "display: none;"
0x131c7  ldc.i4.0
0x131c8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x131cd  ldarg.1
0x131ce  ldc.i4.s 0x3E
0x131d0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x131d5  ldarg.1
0x131d6  ldstr    aTable// "table"
0x131db  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x131e0  ldarg.1
0x131e1  ldstr    aCellspacing// "cellspacing"
0x131e6  ldstr    a0// "0"
0x131eb  ldc.i4.0
0x131ec  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x131f1  ldarg.1
0x131f2  ldstr    aCellpadding// "cellpadding"
0x131f7  ldstr    a0// "0"
0x131fc  ldc.i4.0
0x131fd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13202  ldstr    aId// "id"
0x13207  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1320c  ldstr    a0I// "{0}_i"
0x13211  ldc.i4.1
0x13212  newarr   [mscorlib]System.Object
0x13217  dup
0x13218  ldc.i4.0
0x13219  ldarg.0
0x1321a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1321f  stelem.ref
0x13220  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13225  ldarg.1
0x13226  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1322b  ldstr    aAttrname// "attrname"
0x13230  ldarg.0
0x13231  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x13236  ldarg.1
0x13237  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1323c  ldarg.1
0x1323d  ldstr    aClass// "class"
0x13242  ldstr    aMsCrmDurationM// "ms-crm-Duration ms-crm-InlineDuration"
0x13247  ldc.i4.0
0x13248  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1324d  ldstr    aAriaLabelledby// "aria-labelledby"
0x13252  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13257  ldstr    a0C0W// "{0}_c {0}_w"
0x1325c  ldc.i4.1
0x1325d  newarr   [mscorlib]System.Object
0x13262  dup
0x13263  ldc.i4.0
0x13264  ldarg.0
0x13265  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1326a  stelem.ref
0x1326b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13270  ldarg.1
0x13271  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x13276  ldarg.1
0x13277  ldstr    aControlmode_0// "controlmode"
0x1327c  ldstr    aNormal// "normal"
0x13281  ldc.i4.0
0x13282  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13287  ldarg.1
0x13288  ldstr    aStyle// "style"
0x1328d  ldstr    aWidth100TableL// "width: 100%; table-layout: fixed;"
0x13292  ldc.i4.0
0x13293  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13298  ldarg.1
0x13299  ldc.i4.s 0x3E
0x1329b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x132a0  ldarg.1
0x132a1  ldstr    aTbody// "tbody"
0x132a6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x132ab  ldarg.1
0x132ac  ldc.i4.s 0x3E
0x132ae  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x132b3  ldarg.1
0x132b4  ldstr    aTr_0// "tr"
0x132b9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x132be  ldarg.1
0x132bf  ldc.i4.s 0x3E
0x132c1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x132c6  ldarg.1
0x132c7  ldstr    aTd_0// "td"
0x132cc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x132d1  ldarg.1
0x132d2  ldc.i4.s 0x3E
0x132d4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x132d9  ldarg.1
0x132da  ldstr    aDiv// "div"
0x132df  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x132e4  ldarg.1
0x132e5  ldc.i4.s 0x3E
0x132e7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x132ec  ldarg.1
0x132ed  ldstr    aLabel_0// "label"
0x132f2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x132f7  ldstr    aFor// "for"
0x132fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13301  ldstr    a0_1// "{0}"
0x13306  ldc.i4.1
0x13307  newarr   [mscorlib]System.Object
0x1330c  dup
0x1330d  ldc.i4.0
0x1330e  ldarg.0
0x1330f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x13314  stelem.ref
0x13315  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1331a  ldarg.1
0x1331b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x13320  ldarg.1
0x13321  ldstr    aClass// "class"
0x13326  ldstr    aMsCrmHidden// "ms-crm-Hidden"
0x1332b  ldc.i4.0
0x1332c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13331  ldarg.1
0x13332  ldc.i4.s 0x3E
0x13334  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x13339  ldarg.1
0x1333a  ldstr    aLabel_0// "label"
0x1333f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x13344  ldarg.1
0x13345  ldstr    aSpan// "span"
0x1334a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1334f  ldstr    aId// "id"
0x13354  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13359  ldstr    a0Iselect// "{0}_iSelect"
0x1335e  ldc.i4.1
0x1335f  newarr   [mscorlib]System.Object
0x13364  dup
0x13365  ldc.i4.0
0x13366  ldarg.0
0x13367  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1336c  stelem.ref
0x1336d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13372  ldarg.1
0x13373  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x13378  ldstr    aName// "name"
0x1337d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13382  ldstr    a0Iselectinput// "{0}_iSelectInput"
0x13387  ldc.i4.1
0x13388  newarr   [mscorlib]System.Object
0x1338d  dup
0x1338e  ldc.i4.0
0x1338f  ldarg.0
0x13390  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x13395  stelem.ref
0x13396  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1339b  ldarg.1
0x1339c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x133a1  ldarg.1
0x133a2  ldstr    aButtontitle// "buttontitle"
0x133a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x133ac  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x133b1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x133b6  ldc.i4.0
0x133b7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x133bc  ldarg.1
0x133bd  ldstr    aDefaultimemode// "defaultimemode"
0x133c2  ldstr    aAuto// "auto"
0x133c7  ldc.i4.0
0x133c8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x133cd  ldarg.1
0x133ce  ldstr    aAllowvalueedit// "allowvalueedit"
0x133d3  ldstr    aTrue// "true"
0x133d8  ldc.i4.0
0x133d9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x133de  ldarg.1
0x133df  ldstr    aClass// "class"
0x133e4  ldstr    aMsCrmSelectbox// "ms-crm-SelectBox"
0x133e9  ldc.i4.0
0x133ea  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x133ef  ldarg.1
0x133f0  ldc.i4.s 0x3E
0x133f2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x133f7  ldarg.1
0x133f8  ldstr    aTable// "table"
0x133fd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x13402  ldarg.1
0x13403  ldstr    aCellspacing// "cellspacing"
0x13408  ldstr    a0// "0"
0x1340d  ldc.i4.0
0x1340e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13413  ldarg.1
0x13414  ldstr    aCellpadding// "cellpadding"
0x13419  ldstr    a0// "0"
0x1341e  ldc.i4.0
0x1341f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13424  ldarg.1
0x13425  ldstr    aId// "id"
0x1342a  ldstr    aSelecttable// "selectTable"
0x1342f  ldc.i4.0
0x13430  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13435  ldarg.1
0x13436  ldstr    aClass// "class"
0x1343b  ldstr    aMsCrmInlinedur// "ms-crm-InlineDuration-InputTable"
0x13440  ldc.i4.0
0x13441  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13446  ldarg.1
0x13447  ldc.i4.s 0x3E
0x13449  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1344e  ldarg.1
0x1344f  ldstr    aColgroup// "colgroup"
0x13454  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x13459  ldarg.1
0x1345a  ldc.i4.s 0x3E
0x1345c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x13461  ldarg.1
0x13462  ldstr    aCol// "col"
0x13467  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1346c  ldarg.1
0x1346d  ldc.i4.s 0x3E
0x1346f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x13474  ldarg.1
0x13475  ldstr    aCol// "col"
0x1347a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1347f  ldarg.1
0x13480  ldstr    aWidth// "width"
0x13485  ldstr    a21// "21"
0x1348a  ldc.i4.0
0x1348b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13490  ldarg.1
0x13491  ldc.i4.s 0x3E
0x13493  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x13498  ldarg.1
0x13499  ldstr    aColgroup// "colgroup"
0x1349e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x134a3  ldarg.1
0x134a4  ldstr    aTbody// "tbody"
0x134a9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x134ae  ldarg.1
0x134af  ldc.i4.s 0x3E
0x134b1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x134b6  ldarg.1
0x134b7  ldstr    aTr_0// "tr"
0x134bc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x134c1  ldarg.1
0x134c2  ldc.i4.s 0x3E
0x134c4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x134c9  ldarg.1
0x134ca  ldstr    aTd_0// "td"
0x134cf  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x134d4  ldarg.1
0x134d5  ldstr    aClass// "class"
0x134da  ldstr    aMsCrmSelectInp// "ms-crm-Select-Input-Container"
0x134df  ldc.i4.0
0x134e0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x134e5  ldarg.1
0x134e6  ldc.i4.s 0x3E
0x134e8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x134ed  ldarg.1
0x134ee  ldstr    aInput// "input"
0x134f3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x134f8  ldstr    aId// "id"
0x134fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13502  ldstr    a0Iselectinput// "{0}_iSelectInput"
0x13507  ldc.i4.1
0x13508  newarr   [mscorlib]System.Object
0x1350d  dup
0x1350e  ldc.i4.0
0x1350f  ldarg.0
0x13510  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x13515  stelem.ref
0x13516  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1351b  ldarg.1
0x1351c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x13521  ldarg.1
0x13522  ldstr    aTitle// "title"
0x13527  ldstr    asc_30804// ""
0x1352c  ldc.i4.0
0x1352d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13532  ldarg.1
0x13533  ldstr    aCrmtype// "crmtype"
0x13538  ldstr    aSel// "sel"
0x1353d  ldc.i4.0
0x1353e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13543  ldarg.1
0x13544  ldstr    aStyle// "style"
0x13549  ldstr    aImeModeInactiv// "ime-mode: inactive"
0x1354e  ldc.i4.0
0x1354f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13554  ldarg.1
0x13555  ldstr    aClass// "class"
0x1355a  ldstr    aMsCrmSelectbox// "ms-crm-SelectBox"
0x1355f  ldc.i4.0
0x13560  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13565  ldarg.1
0x13566  ldc.i4.s 0x3E
0x13568  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1356d  ldarg.1
0x1356e  ldstr    aTd_0// "td"
0x13573  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
  ... truncated ...
```
