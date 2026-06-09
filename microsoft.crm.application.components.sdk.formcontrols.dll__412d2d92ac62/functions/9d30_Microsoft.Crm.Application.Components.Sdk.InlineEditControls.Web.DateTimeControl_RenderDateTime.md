# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.DateTimeControl::RenderDateTime

- ea: `0x9d30`
- end: `0xa361`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.DateTimeControl::RenderDateTime`
- size: `1585`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x98a0`
- `0x12b90`

## callees

- `0x9d30`
- `0xa380`

## pseudocode

```c

```

## disassembly

```asm
0x9d30  ldarg.1
0x9d31  ldstr    aTd_0// "td"
0x9d36  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9d3b  ldarg.1
0x9d3c  ldstr    aClass// "class"
0x9d41  ldstr    aMsCrmInlinedat// "ms-crm-InlineDateTime-HiddenCell"
0x9d46  ldc.i4.0
0x9d47  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9d4c  ldarg.1
0x9d4d  ldc.i4.s 0x3E
0x9d4f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9d54  ldarg.1
0x9d55  ldstr    aTd_0// "td"
0x9d5a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9d5f  ldarg.1
0x9d60  ldstr    aTd_0// "td"
0x9d65  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9d6a  ldarg.1
0x9d6b  ldstr    aClass// "class"
0x9d70  ldstr    aMsCrmInlinedat_1// "ms-crm-InlineDateTime-TimeCell ms-crm-D"...
0x9d75  ldc.i4.0
0x9d76  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9d7b  ldarg.1
0x9d7c  ldc.i4.s 0x3E
0x9d7e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9d83  ldarg.1
0x9d84  ldstr    aDiv// "div"
0x9d89  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9d8e  ldarg.1
0x9d8f  ldc.i4.s 0x3E
0x9d91  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9d96  ldarg.1
0x9d97  ldstr    aLabel_0// "label"
0x9d9c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9da1  ldarg.1
0x9da2  ldstr    aFor// "for"
0x9da7  ldstr    aTime// "time"
0x9dac  ldc.i4.0
0x9dad  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9db2  ldarg.1
0x9db3  ldstr    aClass// "class"
0x9db8  ldstr    aMsCrmHidden// "ms-crm-Hidden"
0x9dbd  ldc.i4.0
0x9dbe  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9dc3  ldarg.1
0x9dc4  ldc.i4.s 0x3E
0x9dc6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9dcb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9dd0  ldstr    aWebFormsStyles// "Web._forms.styles.IMG.dtm.htc_27_0"
0x9dd5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9dda  ldarg.1
0x9ddb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x9de0  ldarg.1
0x9de1  ldstr    aLabel_0// "label"
0x9de6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9deb  ldarg.1
0x9dec  ldstr    aSpan// "span"
0x9df1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9df6  ldstr    aId// "id"
0x9dfb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e00  ldstr    a0Itime// "{0}_iTime"
0x9e05  ldc.i4.1
0x9e06  newarr   [mscorlib]System.Object
0x9e0b  dup
0x9e0c  ldc.i4.0
0x9e0d  ldarg.0
0x9e0e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9e13  stelem.ref
0x9e14  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9e19  ldarg.1
0x9e1a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x9e1f  ldstr    aName// "name"
0x9e24  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e29  ldstr    a0Itimeinput// "{0}_iTimeInput"
0x9e2e  ldc.i4.1
0x9e2f  newarr   [mscorlib]System.Object
0x9e34  dup
0x9e35  ldc.i4.0
0x9e36  ldarg.0
0x9e37  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9e3c  stelem.ref
0x9e3d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9e42  ldarg.1
0x9e43  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x9e48  ldarg.1
0x9e49  ldstr    aButtontitle// "buttontitle"
0x9e4e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9e53  ldstr    aGeneralTimeBut// "General.Time.ButtonLabel"
0x9e58  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e5d  ldc.i4.0
0x9e5e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9e63  ldarg.1
0x9e64  ldstr    aDefaultimemode// "defaultimemode"
0x9e69  ldstr    aAuto// "auto"
0x9e6e  ldc.i4.0
0x9e6f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9e74  ldarg.1
0x9e75  ldstr    aAllowvalueedit// "allowvalueedit"
0x9e7a  ldstr    aTrue// "true"
0x9e7f  ldc.i4.0
0x9e80  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9e85  ldarg.1
0x9e86  ldstr    aSetdisabled// "setdisabled"
0x9e8b  ldstr    aTrue// "true"
0x9e90  ldc.i4.0
0x9e91  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9e96  ldarg.1
0x9e97  ldstr    aValue// "value"
0x9e9c  ldstr    asc_38C0C// " "
0x9ea1  ldc.i4.0
0x9ea2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9ea7  ldarg.1
0x9ea8  ldstr    aClass// "class"
0x9ead  ldstr    aMsCrmSelectbox// "ms-crm-SelectBox"
0x9eb2  ldc.i4.0
0x9eb3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9eb8  ldarg.1
0x9eb9  ldc.i4.s 0x3E
0x9ebb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9ec0  ldarg.1
0x9ec1  ldstr    aTable// "table"
0x9ec6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9ecb  ldarg.1
0x9ecc  ldstr    aId// "id"
0x9ed1  ldstr    aSelecttableDat// "selectTable_Date"
0x9ed6  ldc.i4.0
0x9ed7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9edc  ldarg.1
0x9edd  ldstr    aCellspacing// "cellspacing"
0x9ee2  ldstr    a0// "0"
0x9ee7  ldc.i4.0
0x9ee8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9eed  ldarg.1
0x9eee  ldstr    aCellpadding// "cellpadding"
0x9ef3  ldstr    a0// "0"
0x9ef8  ldc.i4.0
0x9ef9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9efe  ldarg.1
0x9eff  ldstr    aClass// "class"
0x9f04  ldstr    aMsCrmInlinedur// "ms-crm-InlineDuration-InputTable"
0x9f09  ldc.i4.0
0x9f0a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9f0f  ldarg.1
0x9f10  ldc.i4.s 0x3E
0x9f12  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9f17  ldarg.1
0x9f18  ldstr    aColgroup// "colgroup"
0x9f1d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9f22  ldarg.1
0x9f23  ldc.i4.s 0x3E
0x9f25  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9f2a  ldarg.1
0x9f2b  ldstr    aCol// "col"
0x9f30  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9f35  ldarg.1
0x9f36  ldc.i4.s 0x3E
0x9f38  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9f3d  ldarg.1
0x9f3e  ldstr    aCol// "col"
0x9f43  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9f48  ldarg.1
0x9f49  ldstr    aCol// "col"
0x9f4e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9f53  ldarg.1
0x9f54  ldstr    aWidth// "width"
0x9f59  ldstr    a21// "21"
0x9f5e  ldc.i4.0
0x9f5f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9f64  ldarg.1
0x9f65  ldc.i4.s 0x3E
0x9f67  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9f6c  ldarg.1
0x9f6d  ldstr    aCol// "col"
0x9f72  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9f77  ldarg.1
0x9f78  ldstr    aColgroup// "colgroup"
0x9f7d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x9f82  ldarg.1
0x9f83  ldstr    aTr_0// "tr"
0x9f88  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9f8d  ldarg.1
0x9f8e  ldc.i4.s 0x3E
0x9f90  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9f95  ldarg.1
0x9f96  ldstr    aTd_0// "td"
0x9f9b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9fa0  ldarg.1
0x9fa1  ldstr    aClass// "class"
0x9fa6  ldstr    aMsCrmSelectInp// "ms-crm-Select-Input-Container"
0x9fab  ldc.i4.0
0x9fac  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9fb1  ldarg.1
0x9fb2  ldc.i4.s 0x3E
0x9fb4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x9fb9  ldarg.1
0x9fba  ldstr    aInput// "input"
0x9fbf  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x9fc4  ldstr    aId// "id"
0x9fc9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9fce  ldstr    a0Itimeinput// "{0}_iTimeInput"
0x9fd3  ldc.i4.1
0x9fd4  newarr   [mscorlib]System.Object
0x9fd9  dup
0x9fda  ldc.i4.0
0x9fdb  ldarg.0
0x9fdc  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9fe1  stelem.ref
0x9fe2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9fe7  ldarg.1
0x9fe8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x9fed  ldarg.1
0x9fee  ldstr    aCrmtype// "crmtype"
0x9ff3  ldstr    aSel// "sel"
0x9ff8  ldc.i4.0
0x9ff9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x9ffe  ldarg.1
0x9fff  ldstr    aStyle// "style"
0xa004  ldstr    aImeModeInactiv// "ime-mode: inactive"
0xa009  ldc.i4.0
0xa00a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa00f  ldarg.1
0xa010  ldstr    aClass// "class"
0xa015  ldstr    aMsCrmSelectbox// "ms-crm-SelectBox"
0xa01a  ldc.i4.0
0xa01b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa020  ldarg.1
0xa021  ldstr    aRownum// "rownum"
0xa026  ldstr    a6// "6"
0xa02b  ldc.i4.0
0xa02c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa031  ldarg.1
0xa032  ldstr    aReq// "req"
0xa037  ldstr    a0// "0"
0xa03c  ldc.i4.0
0xa03d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa042  ldarg.1
0xa043  ldstr    aTimecontrol// "timecontrol"
0xa048  ldstr    aTrue// "true"
0xa04d  ldc.i4.0
0xa04e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa053  ldarg.1
0xa054  ldc.i4.s 0x3E
0xa056  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa05b  ldarg.1
0xa05c  ldstr    aInput// "input"
0xa061  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0xa066  ldarg.1
0xa067  ldstr    aTd_0// "td"
0xa06c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0xa071  ldarg.1
0xa072  ldstr    aTd_0// "td"
0xa077  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa07c  ldarg.1
0xa07d  ldstr    aClass// "class"
0xa082  ldstr    aMsCrmInlinedur_0// "ms-crm-InlineDuration-IconCell"
0xa087  ldc.i4.0
0xa088  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa08d  ldarg.1
0xa08e  ldc.i4.s 0x3E
0xa090  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xa095  ldarg.1
0xa096  ldstr    aImg// "img"
0xa09b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xa0a0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xa0a5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0xa0aa  brtrue.s loc_A0D0
0xa0ac  ldarg.1
0xa0ad  ldstr    aSrc// "src"
0xa0b2  ldstr    aImgsInlineedit_3// "/_imgs/inlineedit/time_icon.png"
0xa0b7  ldc.i4.0
0xa0b8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa0bd  ldarg.1
0xa0be  ldstr    aClass// "class"
0xa0c3  ldstr    aMsCrmInlinedur_1// "ms-crm-InlineDuration-Icon"
0xa0c8  ldc.i4.0
0xa0c9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa0ce  br.s     loc_A0F2
0xa0d0  ldarg.1
0xa0d1  ldstr    aSrc// "src"
0xa0d6  ldstr    aImgsImagestrip// "/_imgs/imagestrips/transparent_spacer.g"...
0xa0db  ldc.i4.0
0xa0dc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa0e1  ldarg.1
0xa0e2  ldstr    aClass// "class"
0xa0e7  ldstr    aMsCrmImagestri_2// "ms-crm-ImageStrip-inlineedit_time_icon "...
0xa0ec  ldc.i4.0
0xa0ed  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa0f2  ldarg.1
0xa0f3  ldstr    aAlt// "alt"
0xa0f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa0fd  ldstr    aGeneralTimeBut// "General.Time.ButtonLabel"
0xa102  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa107  ldc.i4.0
0xa108  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xa10d  ldstr    aId// "id"
0xa112  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa117  ldstr    a0Ipicklistimg// "{0}_ipicklistimg"
0xa11c  ldc.i4.1
0xa11d  newarr   [mscorlib]System.Object
0xa122  dup
  ... truncated ...
```
