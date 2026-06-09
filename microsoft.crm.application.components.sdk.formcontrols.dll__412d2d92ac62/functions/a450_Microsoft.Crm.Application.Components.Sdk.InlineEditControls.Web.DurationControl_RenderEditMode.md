# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.DurationControl::RenderEditMode

- ea: `0xa450`
- end: `0xab78`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.DurationControl::RenderEditMode`
- size: `1832`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0xa450`
- `0xab90`
- `0xaf80`

## pseudocode

```c

```

## disassembly

```asm
0xa450  ldarg.1
0xa451  ldstr    aDiv// "div"
0xa456  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa45b  ldarg.1
0xa45c  ldstr    aClass// "class"
0xa461  ldstr    aMsCrmInlineEdi_1// "ms-crm-Inline-Edit"
0xa466  ldc.i4.0
0xa467  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa46c  ldarg.1
0xa46d  ldstr    aStyle// "style"
0xa472  ldstr    aDisplayNone_0// "display: none;"
0xa477  ldc.i4.0
0xa478  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa47d  ldarg.1
0xa47e  ldc.i4.s 0x3E
0xa480  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa485  ldarg.1
0xa486  ldstr    aTable// "table"
0xa48b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa490  ldarg.1
0xa491  ldstr    aCellspacing// "cellspacing"
0xa496  ldstr    a0// "0"
0xa49b  ldc.i4.0
0xa49c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa4a1  ldarg.1
0xa4a2  ldstr    aCellpadding// "cellpadding"
0xa4a7  ldstr    a0// "0"
0xa4ac  ldc.i4.0
0xa4ad  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa4b2  ldstr    aId// "id"
0xa4b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4bc  ldstr    a0I// "{0}_i"
0xa4c1  ldc.i4.1
0xa4c2  newarr   [mscorlib]System.Object
0xa4c7  dup
0xa4c8  ldc.i4.0
0xa4c9  ldarg.0
0xa4ca  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa4cf  stelem.ref
0xa4d0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa4d5  ldarg.1
0xa4d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa4db  ldstr    aAttrname// "attrname"
0xa4e0  ldarg.0
0xa4e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xa4e6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xa4eb  ldarg.1
0xa4ec  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa4f1  ldarg.1
0xa4f2  ldstr    aClass// "class"
0xa4f7  ldstr    aMsCrmDurationM// "ms-crm-Duration ms-crm-InlineDuration"
0xa4fc  ldc.i4.0
0xa4fd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa502  ldstr    aAriaLabelledby// "aria-labelledby"
0xa507  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa50c  ldstr    a0C0W// "{0}_c {0}_w"
0xa511  ldc.i4.1
0xa512  newarr   [mscorlib]System.Object
0xa517  dup
0xa518  ldc.i4.0
0xa519  ldarg.0
0xa51a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa51f  stelem.ref
0xa520  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa525  ldarg.1
0xa526  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa52b  ldarg.1
0xa52c  ldstr    aControlmode_0// "controlmode"
0xa531  ldstr    aNormal// "normal"
0xa536  ldc.i4.0
0xa537  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa53c  ldarg.1
0xa53d  ldstr    aStyle// "style"
0xa542  ldstr    aWidth100TableL// "width: 100%; table-layout: fixed;"
0xa547  ldc.i4.0
0xa548  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa54d  ldarg.1
0xa54e  ldc.i4.s 0x3E
0xa550  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa555  ldarg.1
0xa556  ldstr    aTbody// "tbody"
0xa55b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa560  ldarg.1
0xa561  ldc.i4.s 0x3E
0xa563  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa568  ldarg.1
0xa569  ldstr    aTr_0// "tr"
0xa56e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa573  ldarg.1
0xa574  ldc.i4.s 0x3E
0xa576  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa57b  ldarg.1
0xa57c  ldstr    aTd_0// "td"
0xa581  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa586  ldarg.1
0xa587  ldc.i4.s 0x3E
0xa589  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa58e  ldarg.1
0xa58f  ldstr    aDiv// "div"
0xa594  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa599  ldarg.1
0xa59a  ldc.i4.s 0x3E
0xa59c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa5a1  ldarg.1
0xa5a2  ldstr    aLabel_0// "label"
0xa5a7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa5ac  ldstr    aFor// "for"
0xa5b1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa5b6  ldstr    a0_1// "{0}"
0xa5bb  ldc.i4.1
0xa5bc  newarr   [mscorlib]System.Object
0xa5c1  dup
0xa5c2  ldc.i4.0
0xa5c3  ldarg.0
0xa5c4  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa5c9  stelem.ref
0xa5ca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa5cf  ldarg.1
0xa5d0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa5d5  ldarg.1
0xa5d6  ldstr    aClass// "class"
0xa5db  ldstr    aMsCrmHidden// "ms-crm-Hidden"
0xa5e0  ldc.i4.0
0xa5e1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa5e6  ldarg.1
0xa5e7  ldc.i4.s 0x3E
0xa5e9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa5ee  ldarg.1
0xa5ef  ldstr    aLabel_0// "label"
0xa5f4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0xa5f9  ldarg.1
0xa5fa  ldstr    aSpan// "span"
0xa5ff  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa604  ldstr    aId// "id"
0xa609  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa60e  ldstr    a0Iselect// "{0}_iSelect"
0xa613  ldc.i4.1
0xa614  newarr   [mscorlib]System.Object
0xa619  dup
0xa61a  ldc.i4.0
0xa61b  ldarg.0
0xa61c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa621  stelem.ref
0xa622  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa627  ldarg.1
0xa628  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa62d  ldstr    aName// "name"
0xa632  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa637  ldstr    a0Iselectinput// "{0}_iSelectInput"
0xa63c  ldc.i4.1
0xa63d  newarr   [mscorlib]System.Object
0xa642  dup
0xa643  ldc.i4.0
0xa644  ldarg.0
0xa645  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa64a  stelem.ref
0xa64b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa650  ldarg.1
0xa651  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa656  ldarg.1
0xa657  ldstr    aButtontitle// "buttontitle"
0xa65c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa661  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0xa666  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa66b  ldc.i4.0
0xa66c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa671  ldarg.1
0xa672  ldstr    aDefaultimemode// "defaultimemode"
0xa677  ldstr    aAuto// "auto"
0xa67c  ldc.i4.0
0xa67d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa682  ldarg.1
0xa683  ldstr    aAllowvalueedit// "allowvalueedit"
0xa688  ldstr    aTrue// "true"
0xa68d  ldc.i4.0
0xa68e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa693  ldarg.1
0xa694  ldstr    aClass// "class"
0xa699  ldstr    aMsCrmSelectbox// "ms-crm-SelectBox"
0xa69e  ldc.i4.0
0xa69f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa6a4  ldarg.1
0xa6a5  ldc.i4.s 0x3E
0xa6a7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa6ac  ldarg.1
0xa6ad  ldstr    aTable// "table"
0xa6b2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa6b7  ldarg.1
0xa6b8  ldstr    aCellspacing// "cellspacing"
0xa6bd  ldstr    a0// "0"
0xa6c2  ldc.i4.0
0xa6c3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa6c8  ldarg.1
0xa6c9  ldstr    aCellpadding// "cellpadding"
0xa6ce  ldstr    a0// "0"
0xa6d3  ldc.i4.0
0xa6d4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa6d9  ldarg.1
0xa6da  ldstr    aId// "id"
0xa6df  ldstr    aSelecttable// "selectTable"
0xa6e4  ldc.i4.0
0xa6e5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa6ea  ldarg.1
0xa6eb  ldstr    aClass// "class"
0xa6f0  ldstr    aMsCrmInlinedur// "ms-crm-InlineDuration-InputTable"
0xa6f5  ldc.i4.0
0xa6f6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa6fb  ldarg.1
0xa6fc  ldc.i4.s 0x3E
0xa6fe  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa703  ldarg.1
0xa704  ldstr    aColgroup// "colgroup"
0xa709  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa70e  ldarg.1
0xa70f  ldc.i4.s 0x3E
0xa711  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa716  ldarg.1
0xa717  ldstr    aCol// "col"
0xa71c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa721  ldarg.1
0xa722  ldc.i4.s 0x3E
0xa724  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa729  ldarg.1
0xa72a  ldstr    aCol// "col"
0xa72f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa734  ldarg.1
0xa735  ldstr    aWidth// "width"
0xa73a  ldstr    a21// "21"
0xa73f  ldc.i4.0
0xa740  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa745  ldarg.1
0xa746  ldc.i4.s 0x3E
0xa748  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa74d  ldarg.1
0xa74e  ldstr    aColgroup// "colgroup"
0xa753  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0xa758  ldarg.1
0xa759  ldstr    aTbody// "tbody"
0xa75e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa763  ldarg.1
0xa764  ldc.i4.s 0x3E
0xa766  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa76b  ldarg.1
0xa76c  ldstr    aTr_0// "tr"
0xa771  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa776  ldarg.1
0xa777  ldc.i4.s 0x3E
0xa779  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa77e  ldarg.1
0xa77f  ldstr    aTd_0// "td"
0xa784  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa789  ldarg.1
0xa78a  ldstr    aClass// "class"
0xa78f  ldstr    aMsCrmSelectInp// "ms-crm-Select-Input-Container"
0xa794  ldc.i4.0
0xa795  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa79a  ldarg.1
0xa79b  ldc.i4.s 0x3E
0xa79d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa7a2  ldarg.1
0xa7a3  ldstr    aInput// "input"
0xa7a8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa7ad  ldstr    aId// "id"
0xa7b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa7b7  ldstr    a0Iselectinput// "{0}_iSelectInput"
0xa7bc  ldc.i4.1
0xa7bd  newarr   [mscorlib]System.Object
0xa7c2  dup
0xa7c3  ldc.i4.0
0xa7c4  ldarg.0
0xa7c5  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa7ca  stelem.ref
0xa7cb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa7d0  ldarg.1
0xa7d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa7d6  ldarg.1
0xa7d7  ldstr    aTitle// "title"
0xa7dc  ldstr    asc_30804// ""
0xa7e1  ldc.i4.0
0xa7e2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa7e7  ldarg.1
0xa7e8  ldstr    aCrmtype// "crmtype"
0xa7ed  ldstr    aSel// "sel"
0xa7f2  ldc.i4.0
0xa7f3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa7f8  ldarg.1
0xa7f9  ldstr    aStyle// "style"
0xa7fe  ldstr    aImeModeInactiv// "ime-mode: inactive"
0xa803  ldc.i4.0
0xa804  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa809  ldarg.1
0xa80a  ldstr    aClass// "class"
0xa80f  ldstr    aMsCrmSelectbox// "ms-crm-SelectBox"
0xa814  ldc.i4.0
0xa815  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa81a  ldarg.1
0xa81b  ldc.i4.s 0x3E
0xa81d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa822  ldarg.1
0xa823  ldstr    aTd_0// "td"
  ... truncated ...
```
