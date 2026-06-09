# Microsoft.Crm.Controls.CommandBarPopup::RenderForCrmMenuBar

- ea: `0x11d80`
- end: `0x123ab`
- name: `Microsoft.Crm.Controls.CommandBarPopup::RenderForCrmMenuBar`
- size: `1579`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x11be0`

## callees

- `0xffb0`
- `0x116d0`
- `0x11710`
- `0x11740`
- `0x11800`
- `0x118b0`
- `0x119e0`
- `0x11ad0`
- `0x11af0`
- `0x11d80`
- `0x123b0`
- `0x142c0`
- `0x1a3b0`
- `0x1a400`
- `0x1a410`
- `0x224d0`
- `0x24210`

## string_xrefs

- `0x11ebc`: `accessKey`
- `0x120b7`: `accessKey`
- `0x1232e`: `CommandBar.MenuDown.AltTag`
- `0x12348`: `CommandBar.MenuDown.AltTag`
- `0x11e4b`: `menuxml`

## pseudocode

```c

```

## disassembly

```asm
0x11d80  ldstr    aMsCrmMenu// "ms-crm-Menu"
0x11d85  stloc.0
0x11d86  ldarg.0
0x11d87  call     instance valuetype Microsoft.Crm.Controls.CommandBarAlignment Microsoft.Crm.Controls.CommandBarControl::get_Alignment()
0x11d8c  ldc.i4.2
0x11d8d  bne.un.s loc_11D95
0x11d8f  ldstr    aMsCrmMenuRight// "ms-crm-Menu-Right"
0x11d94  stloc.0
0x11d95  ldarg.0
0x11d96  ldstr    aMb// "_MB"
0x11d9b  call     instance void Microsoft.Crm.Controls.CommandBarControl::SetTestIdFromAction(string prefix)
0x11da0  ldarg.1
0x11da1  ldstr    aLi_0// "LI"
0x11da6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x11dab  ldarg.0
0x11dac  call     instance bool Microsoft.Crm.Controls.CommandBarPopup::get_JewelMenu()
0x11db1  brfalse.s loc_11DCC
0x11db3  ldarg.1
0x11db4  ldstr    aClass_1// "class"
0x11db9  ldloc.0
0x11dba  ldstr    aMsCrmMenuJewel// " ms-crm-Menu-Jewel"
0x11dbf  call     string [mscorlib]System.String::Concat(string, string)
0x11dc4  ldc.i4.0
0x11dc5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11dca  br.s     loc_11DD9
0x11dcc  ldarg.1
0x11dcd  ldstr    aClass_1// "class"
0x11dd2  ldloc.0
0x11dd3  ldc.i4.0
0x11dd4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11dd9  ldarg.1
0x11dda  ldstr    aTabindex// "tabindex"
0x11ddf  ldstr    a1_0// "-1"
0x11de4  ldc.i4.0
0x11de5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11dea  ldstr    aMenu// "menu"
0x11def  ldstr    aMnu// "mnu"
0x11df4  ldarg.0
0x11df5  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11dfa  call     string [mscorlib]System.String::Concat(string, string)
0x11dff  ldarg.1
0x11e00  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11e05  ldarg.0
0x11e06  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11e0b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11e10  brtrue.s loc_11E2D
0x11e12  ldstr    aId// "id"
0x11e17  ldstr    aMnu// "mnu"
0x11e1c  ldarg.0
0x11e1d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11e22  call     string [mscorlib]System.String::Concat(string, string)
0x11e27  ldarg.1
0x11e28  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11e2d  ldarg.0
0x11e2e  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x11e33  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11e38  brtrue.s loc_11E4B
0x11e3a  ldstr    aTitle_2// "title"
0x11e3f  ldarg.0
0x11e40  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x11e45  ldarg.1
0x11e46  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11e4b  ldstr    aMenuxml// "menuxml"
0x11e50  ldarg.0
0x11e51  call     instance string Microsoft.Crm.Controls.CommandBarPopup::GetSerializedMenuXml()
0x11e56  ldarg.1
0x11e57  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11e5c  ldarg.1
0x11e5d  ldc.i4.s 0x3E
0x11e5f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11e64  ldarg.0
0x11e65  call     instance bool Microsoft.Crm.Controls.CommandBarPopup::get_JewelMenu()
0x11e6a  brfalse  loc_1206A
0x11e6f  ldarg.1
0x11e70  ldstr    aSpan_0// "SPAN"
0x11e75  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x11e7a  ldarg.1
0x11e7b  ldstr    aTabindex_0// "tabIndex"
0x11e80  ldstr    a1_0// "-1"
0x11e85  ldc.i4.0
0x11e86  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11e8b  ldarg.1
0x11e8c  ldstr    aClass_1// "class"
0x11e91  ldstr    aMsCrmMenuJewel_0// "ms-crm-Menu-JewelButton"
0x11e96  ldc.i4.0
0x11e97  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11e9c  ldarg.1
0x11e9d  ldc.i4.s 0x3E
0x11e9f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11ea4  ldarg.1
0x11ea5  ldstr    aA_1// "A"
0x11eaa  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x11eaf  ldarg.0
0x11eb0  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x11eb5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11eba  brtrue.s loc_11ECD
0x11ebc  ldstr    aAccesskey// "accessKey"
0x11ec1  ldarg.0
0x11ec2  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x11ec7  ldarg.1
0x11ec8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11ecd  ldstr    aOnclick_0// "onclick"
0x11ed2  ldstr    aReturnFalse// "return false;"
0x11ed7  ldarg.1
0x11ed8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11edd  ldstr    aHref// "href"
0x11ee2  ldstr    aJavascriptOncl// "javascript:onclick();"
0x11ee7  ldarg.1
0x11ee8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11eed  ldarg.1
0x11eee  ldstr    aTarget// "target"
0x11ef3  ldstr    aSelf// "_self"
0x11ef8  ldc.i4.0
0x11ef9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11efe  ldarg.1
0x11eff  ldstr    aTabindex_0// "tabIndex"
0x11f04  ldstr    a0// "0"
0x11f09  ldc.i4.0
0x11f0a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11f0f  ldarg.1
0x11f10  ldstr    aType// "type"
0x11f15  ldstr    aMenu// "menu"
0x11f1a  ldc.i4.0
0x11f1b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11f20  ldarg.1
0x11f21  ldstr    aClass_1// "class"
0x11f26  ldstr    aMsCrmMenuJewel_0// "ms-crm-Menu-JewelButton"
0x11f2b  ldc.i4.0
0x11f2c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11f31  ldarg.1
0x11f32  ldc.i4.s 0x3E
0x11f34  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11f39  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x11f3e  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x11f43  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x11f48  brfalse.s loc_11F58
0x11f4a  ldstr    aMsCrmMenuJewel_1// "ms-crm-Menu-JewelButton-first-span ms-c"...
0x11f4f  stloc.1
0x11f50  ldstr    aMsCrmMenuJewel_2// "ms-crm-Menu-JewelButton-third-span ms-c"...
0x11f55  stloc.2
0x11f56  br.s     loc_11F64
0x11f58  ldstr    aMsCrmMenuJewel_3// "ms-crm-Menu-JewelButton-first-span ms-c"...
0x11f5d  stloc.1
0x11f5e  ldstr    aMsCrmMenuJewel_4// "ms-crm-Menu-JewelButton-third-span ms-c"...
0x11f63  stloc.2
0x11f64  ldarg.1
0x11f65  ldstr    aSpan_0// "SPAN"
0x11f6a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x11f6f  ldarg.1
0x11f70  ldstr    aTabindex_0// "tabIndex"
0x11f75  ldstr    a1_0// "-1"
0x11f7a  ldc.i4.0
0x11f7b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11f80  ldarg.1
0x11f81  ldstr    aClass_1// "class"
0x11f86  ldloc.1
0x11f87  ldc.i4.0
0x11f88  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11f8d  ldarg.1
0x11f8e  ldc.i4.s 0x3E
0x11f90  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11f95  ldarg.1
0x11f96  ldstr    aSpan_0// "SPAN"
0x11f9b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x11fa0  ldarg.1
0x11fa1  ldstr    aSpan_0// "SPAN"
0x11fa6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x11fab  ldarg.1
0x11fac  ldstr    aTabindex_0// "tabIndex"
0x11fb1  ldstr    a1_0// "-1"
0x11fb6  ldc.i4.0
0x11fb7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11fbc  ldarg.1
0x11fbd  ldstr    aClass_1// "class"
0x11fc2  ldstr    aMsCrmMenuJewel_5// "ms-crm-Menu-JewelButton-second-span ms-"...
0x11fc7  ldc.i4.0
0x11fc8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11fcd  ldarg.1
0x11fce  ldc.i4.s 0x3E
0x11fd0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11fd5  ldarg.1
0x11fd6  ldstr    aSpan_0// "SPAN"
0x11fdb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x11fe0  ldarg.1
0x11fe1  ldstr    aClass_1// "class"
0x11fe6  ldstr    aMsCrmMenuJewel_6// "ms-crm-Menu-Jewel-label"
0x11feb  ldc.i4.0
0x11fec  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11ff1  ldarg.1
0x11ff2  ldc.i4.s 0x3E
0x11ff4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11ff9  ldarg.1
0x11ffa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x11fff  ldstr    aRibbonJewelTex// "Ribbon.Jewel.Text"
0x12004  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12009  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1200e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x12013  ldarg.1
0x12014  ldstr    aSpan_0// "SPAN"
0x12019  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x1201e  ldarg.1
0x1201f  ldstr    aSpan_0// "SPAN"
0x12024  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x12029  ldarg.1
0x1202a  ldstr    aSpan_0// "SPAN"
0x1202f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12034  ldarg.1
0x12035  ldstr    aTabindex_0// "tabIndex"
0x1203a  ldstr    a1_0// "-1"
0x1203f  ldc.i4.0
0x12040  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12045  ldarg.1
0x12046  ldstr    aClass_1// "class"
0x1204b  ldloc.2
0x1204c  ldc.i4.0
0x1204d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12052  ldarg.1
0x12053  ldc.i4.s 0x3E
0x12055  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1205a  ldarg.1
0x1205b  ldstr    aSpan_0// "SPAN"
0x12060  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x12065  br       loc_12389
0x1206a  ldarg.1
0x1206b  ldstr    aSpan_0// "SPAN"
0x12070  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x12075  ldarg.1
0x12076  ldstr    aClass_1// "class"
0x1207b  ldstr    aMsCrmMenuLabel// "ms-crm-Menu-Label"
0x12080  ldc.i4.0
0x12081  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12086  ldarg.1
0x12087  ldstr    aTabindex// "tabindex"
0x1208c  ldstr    a1_0// "-1"
0x12091  ldc.i4.0
0x12092  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x12097  ldarg.1
0x12098  ldc.i4.s 0x3E
0x1209a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1209f  ldarg.1
0x120a0  ldstr    aA_1// "A"
0x120a5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x120aa  ldarg.0
0x120ab  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x120b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x120b5  brtrue.s loc_120C8
0x120b7  ldstr    aAccesskey// "accessKey"
0x120bc  ldarg.0
0x120bd  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x120c2  ldarg.1
0x120c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x120c8  ldarg.1
0x120c9  ldstr    aClass_1// "class"
0x120ce  ldstr    aMsCrmMenuLabel// "ms-crm-Menu-Label"
0x120d3  ldc.i4.0
0x120d4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x120d9  ldarg.1
0x120da  ldstr    aTabindex_0// "tabIndex"
0x120df  ldstr    a0// "0"
0x120e4  ldc.i4.0
0x120e5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x120ea  ldarg.1
0x120eb  ldstr    aType// "type"
0x120f0  ldstr    aMenu// "menu"
0x120f5  ldc.i4.0
0x120f6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x120fb  ldarg.1
0x120fc  ldc.i4.s 0x3E
0x120fe  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x12103  ldarg.0
0x12104  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0x12109  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x1210e  brtrue   loc_12245
0x12113  ldstr    aFirst// "First"
0x12118  stloc.s  4
0x1211a  ldarg.0
0x1211b  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x12120  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12125  brfalse.s loc_12150
0x12127  ldarg.0
0x12128  call     instance bool Microsoft.Crm.Controls.CommandBarPopup::get_DownArrow()
0x1212d  brfalse.s loc_12150
0x1212f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x12134  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x12139  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x1213e  brfalse.s loc_12149
0x12140  ldstr    aRtl_0// "RTL"
0x12145  stloc.s  4
0x12147  br.s     loc_12150
0x12149  ldstr    aLtr_0// "LTR"
0x1214e  stloc.s  4
0x12150  ldarg.1
0x12151  ldstr    aImg// "IMG"
0x12156  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1215b  ldstr    aId// "id"
0x12160  ldstr    aIcon_0// "icon_"
0x12165  ldarg.0
0x12166  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1216b  call     string [mscorlib]System.String::Concat(string, string)
0x12170  ldarg.1
  ... truncated ...
```
