# Microsoft.Crm.Controls.ReadFormCommandBarButton::GetCommandBarButtonTemplate

- ea: `0x10990`
- end: `0x10f55`
- name: `Microsoft.Crm.Controls.ReadFormCommandBarButton::GetCommandBarButtonTemplate`
- size: `1477`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x111d0`
- `0x11270`

## callees

- `0x106b0`
- `0x10760`
- `0x10930`
- `0x10990`
- `0x116d0`
- `0x11710`
- `0x11740`
- `0x11800`
- `0x142c0`
- `0x1a3c0`
- `0x1a410`
- `0x224d0`
- `0x23c20`
- `0x24210`

## string_xrefs

- `0x10bfd`: `accessKey`
- `0x10ec9`: `CommandBar.MenuDown.AltTag`
- `0x10bf0`: `AccessKey`

## pseudocode

```c

```

## disassembly

```asm
0x10990  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10995  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x1099a  stloc.0
0x1099b  ldloc.0
0x1099c  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x109a1  stloc.1
0x109a2  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x109a7  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x109ac  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x109b1  stloc.2
0x109b2  ldloc.1
0x109b3  ldstr    aLi_0// "LI"
0x109b8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x109bd  ldloc.1
0x109be  ldstr    aTabindex_0// "tabIndex"
0x109c3  ldstr    a1_0// "-1"
0x109c8  ldc.i4.0
0x109c9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x109ce  ldarg.0
0x109cf  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0x109d4  brtrue.s loc_109E7
0x109d6  ldloc.1
0x109d7  ldstr    aStyle_0// "style"
0x109dc  ldstr    aDisplayNone// "display:none"
0x109e1  ldc.i4.0
0x109e2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x109e7  ldarg.0
0x109e8  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x109ed  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x109f2  brtrue.s loc_10A30
0x109f4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x109f9  ldstr    aHtmlCrmencoded// "{{{{html CrmEncodeDecode.{0}(Mscrm.Util"...
0x109fe  ldc.i4.3
0x109ff  newarr   [mscorlib]System.Object
0x10a04  dup
0x10a05  ldc.i4.0
0x10a06  ldstr    aCrmhtmlattribu// "CrmHtmlAttributeEncode"
0x10a0b  stelem.ref
0x10a0c  dup
0x10a0d  ldc.i4.1
0x10a0e  ldarg.0
0x10a0f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10a14  stelem.ref
0x10a15  dup
0x10a16  ldc.i4.2
0x10a17  ldstr    aTooltip_0// "ToolTip"
0x10a1c  stelem.ref
0x10a1d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10a22  stloc.3
0x10a23  ldloc.1
0x10a24  ldstr    aTitle_2// "title"
0x10a29  ldloc.3
0x10a2a  ldc.i4.0
0x10a2b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10a30  ldarg.0
0x10a31  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x10a36  brfalse.s loc_10A75
0x10a38  ldloc.1
0x10a39  ldstr    aDisabled// "disabled"
0x10a3e  ldstr    aDisabled// "disabled"
0x10a43  ldc.i4.0
0x10a44  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10a49  ldloc.1
0x10a4a  ldstr    aClass_1// "class"
0x10a4f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10a54  ldstr    a0MsCrmMenuDisa// "{0} ms-crm-Menu-disabled"
0x10a59  ldc.i4.1
0x10a5a  newarr   [mscorlib]System.Object
0x10a5f  dup
0x10a60  ldc.i4.0
0x10a61  ldarg.0
0x10a62  ldfld    string Microsoft.Crm.Controls.ReadFormCommandBarButton::_cssClass
0x10a67  stelem.ref
0x10a68  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10a6d  ldc.i4.0
0x10a6e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10a73  br.s     loc_10A87
0x10a75  ldloc.1
0x10a76  ldstr    aClass_1// "class"
0x10a7b  ldarg.0
0x10a7c  ldfld    string Microsoft.Crm.Controls.ReadFormCommandBarButton::_cssClass
0x10a81  ldc.i4.0
0x10a82  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10a87  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10a8c  ldstr    aHtmlCrmencoded// "{{{{html CrmEncodeDecode.{0}(Mscrm.Util"...
0x10a91  ldc.i4.3
0x10a92  newarr   [mscorlib]System.Object
0x10a97  dup
0x10a98  ldc.i4.0
0x10a99  ldstr    aCrmhtmlattribu// "CrmHtmlAttributeEncode"
0x10a9e  stelem.ref
0x10a9f  dup
0x10aa0  ldc.i4.1
0x10aa1  ldarg.0
0x10aa2  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10aa7  stelem.ref
0x10aa8  dup
0x10aa9  ldc.i4.2
0x10aaa  ldstr    aVisibilityrule// "VisibilityRules"
0x10aaf  stelem.ref
0x10ab0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10ab5  stloc.s  4
0x10ab7  ldloc.1
0x10ab8  ldstr    aDataVisibility// "data-VisibilityRules"
0x10abd  ldloc.s  4
0x10abf  ldc.i4.0
0x10ac0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10ac5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10aca  ldstr    aHtmlCrmencoded// "{{{{html CrmEncodeDecode.{0}(Mscrm.Util"...
0x10acf  ldc.i4.3
0x10ad0  newarr   [mscorlib]System.Object
0x10ad5  dup
0x10ad6  ldc.i4.0
0x10ad7  ldstr    aCrmhtmlattribu// "CrmHtmlAttributeEncode"
0x10adc  stelem.ref
0x10add  dup
0x10ade  ldc.i4.1
0x10adf  ldarg.0
0x10ae0  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10ae5  stelem.ref
0x10ae6  dup
0x10ae7  ldc.i4.2
0x10ae8  ldstr    aIstrimmed// "IsTrimmed"
0x10aed  stelem.ref
0x10aee  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10af3  stloc.s  5
0x10af5  ldloc.1
0x10af6  ldstr    aDataIstrimmed// "data-IsTrimmed"
0x10afb  ldloc.s  5
0x10afd  ldc.i4.0
0x10afe  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10b03  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10b08  ldstr    aHtmlCrmencoded// "{{{{html CrmEncodeDecode.{0}(Mscrm.Util"...
0x10b0d  ldc.i4.3
0x10b0e  newarr   [mscorlib]System.Object
0x10b13  dup
0x10b14  ldc.i4.0
0x10b15  ldstr    aCrmhtmlattribu// "CrmHtmlAttributeEncode"
0x10b1a  stelem.ref
0x10b1b  dup
0x10b1c  ldc.i4.1
0x10b1d  ldarg.0
0x10b1e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10b23  stelem.ref
0x10b24  dup
0x10b25  ldc.i4.2
0x10b26  ldstr    aAction_0// "Action"
0x10b2b  stelem.ref
0x10b2c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10b31  stloc.s  6
0x10b33  ldloc.1
0x10b34  ldstr    aOnclick_0// "onclick"
0x10b39  ldloc.s  6
0x10b3b  ldc.i4.0
0x10b3c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10b41  ldarg.0
0x10b42  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10b47  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10b4c  brtrue.s loc_10B5F
0x10b4e  ldstr    aId// "id"
0x10b53  ldarg.0
0x10b54  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10b59  ldloc.1
0x10b5a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10b5f  ldarg.0
0x10b60  ldfld    bool Microsoft.Crm.Controls.ReadFormCommandBarButton::_unSelectable
0x10b65  brfalse.s loc_10B78
0x10b67  ldloc.1
0x10b68  ldstr    aUnselectable// "unselectable"
0x10b6d  ldstr    aOn// "on"
0x10b72  ldc.i4.0
0x10b73  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10b78  ldloc.1
0x10b79  ldc.i4.s 0x3E
0x10b7b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10b80  ldloc.1
0x10b81  ldstr    aSpan_0// "SPAN"
0x10b86  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10b8b  ldloc.1
0x10b8c  ldstr    aTabindex_0// "tabIndex"
0x10b91  ldstr    a1_0// "-1"
0x10b96  ldc.i4.0
0x10b97  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10b9c  ldloc.1
0x10b9d  ldstr    aClass_1// "class"
0x10ba2  ldstr    aMsCrmMenuLabel// "ms-crm-Menu-Label"
0x10ba7  ldc.i4.0
0x10ba8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10bad  ldloc.1
0x10bae  ldc.i4.s 0x3E
0x10bb0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10bb5  ldloc.1
0x10bb6  ldstr    aA_1// "A"
0x10bbb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10bc0  ldarg.0
0x10bc1  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x10bc6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10bcb  brtrue.s loc_10C09
0x10bcd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10bd2  ldstr    aHtmlCrmencoded// "{{{{html CrmEncodeDecode.{0}(Mscrm.Util"...
0x10bd7  ldc.i4.3
0x10bd8  newarr   [mscorlib]System.Object
0x10bdd  dup
0x10bde  ldc.i4.0
0x10bdf  ldstr    aCrmhtmlattribu// "CrmHtmlAttributeEncode"
0x10be4  stelem.ref
0x10be5  dup
0x10be6  ldc.i4.1
0x10be7  ldarg.0
0x10be8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10bed  stelem.ref
0x10bee  dup
0x10bef  ldc.i4.2
0x10bf0  ldstr    aAccesskey_0// "AccessKey"
0x10bf5  stelem.ref
0x10bf6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10bfb  stloc.3
0x10bfc  ldloc.1
0x10bfd  ldstr    aAccesskey// "accessKey"
0x10c02  ldloc.3
0x10c03  ldc.i4.0
0x10c04  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c09  ldarg.0
0x10c0a  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x10c0f  brfalse.s loc_10C24
0x10c11  ldloc.1
0x10c12  ldstr    aClass_1// "class"
0x10c17  ldstr    aMsCrmMenuLabel_0// "ms-crm-Menu-Label ms-crm-Menu-disabled"
0x10c1c  ldc.i4.0
0x10c1d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c22  br.s     loc_10C35
0x10c24  ldloc.1
0x10c25  ldstr    aClass_1// "class"
0x10c2a  ldstr    aMsCrmMenuLabel// "ms-crm-Menu-Label"
0x10c2f  ldc.i4.0
0x10c30  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c35  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10c3a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10c3f  brfalse.s loc_10C4E
0x10c41  ldarg.0
0x10c42  call     instance int32 Microsoft.Crm.Controls.ReadFormCommandBarButton::get_ActionId()
0x10c47  ldc.i4   0xCA
0x10c4c  beq.s    loc_10C81
0x10c4e  ldloc.1
0x10c4f  ldstr    aOnclick_0// "onclick"
0x10c54  ldstr    aReturnFalse// "return false;"
0x10c59  ldc.i4.0
0x10c5a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c5f  ldloc.1
0x10c60  ldstr    aHref// "href"
0x10c65  ldstr    aJavascriptOncl// "javascript:onclick();"
0x10c6a  ldc.i4.0
0x10c6b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c70  ldloc.1
0x10c71  ldstr    aTarget// "target"
0x10c76  ldstr    aSelf// "_self"
0x10c7b  ldc.i4.0
0x10c7c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c81  ldloc.1
0x10c82  ldstr    aTabindex_0// "tabIndex"
0x10c87  ldstr    a0// "0"
0x10c8c  ldc.i4.0
0x10c8d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10c92  ldloc.1
0x10c93  ldc.i4.s 0x3E
0x10c95  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10c9a  ldarg.0
0x10c9b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0x10ca0  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x10ca5  brtrue   loc_10D85
0x10caa  ldloc.1
0x10cab  ldstr    aImg// "IMG"
0x10cb0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x10cb5  ldloc.1
0x10cb6  ldstr    aTabindex_0// "tabIndex"
0x10cbb  ldstr    a1_0// "-1"
0x10cc0  ldc.i4.0
0x10cc1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10cc6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10ccb  ldstr    aHtmlCrmencoded// "{{{{html CrmEncodeDecode.{0}(Mscrm.Util"...
0x10cd0  ldc.i4.3
0x10cd1  newarr   [mscorlib]System.Object
0x10cd6  dup
0x10cd7  ldc.i4.0
0x10cd8  ldstr    aCrmhtmlattribu// "CrmHtmlAttributeEncode"
0x10cdd  stelem.ref
0x10cde  dup
0x10cdf  ldc.i4.1
0x10ce0  ldarg.0
0x10ce1  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10ce6  stelem.ref
0x10ce7  dup
0x10ce8  ldc.i4.2
0x10ce9  ldstr    aImagecssclass// "ImageCssClass"
0x10cee  stelem.ref
0x10cef  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10cf4  stloc.3
0x10cf5  ldloc.1
0x10cf6  ldstr    aClass_1// "class"
0x10cfb  ldloc.3
  ... truncated ...
```
