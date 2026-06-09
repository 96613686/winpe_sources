# Microsoft.Crm.Controls.CommandBarButton::RenderForCrmMenuBar

- ea: `0x101a0`
- end: `0x105ee`
- name: `Microsoft.Crm.Controls.CommandBarButton::RenderForCrmMenuBar`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0xff40`

## callees

- `0xfea0`
- `0xff00`
- `0xffb0`
- `0x101a0`
- `0x116d0`
- `0x116f0`
- `0x11710`
- `0x11740`
- `0x11800`
- `0x119e0`
- `0x142c0`
- `0x1a3b0`
- `0x1a3f0`
- `0x1a400`
- `0x1a410`
- `0x1a610`
- `0x224d0`
- `0x23c20`
- `0x241c0`
- `0x24210`

## string_xrefs

- `0x10202`: `accessKey`
- `0x10239`: ` ms-crm-Menu-Read`
- `0x10588`: `CommandBar.MenuDown.AltTag`

## pseudocode

```c

```

## disassembly

```asm
0x101a0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x101a5  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x101aa  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x101af  stloc.0
0x101b0  ldarg.0
0x101b1  ldstr    aMb// "_MB"
0x101b6  call     instance void Microsoft.Crm.Controls.CommandBarControl::SetTestIdFromAction(string prefix)
0x101bb  ldarg.1
0x101bc  ldstr    aLi_0// "LI"
0x101c1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x101c6  ldarg.1
0x101c7  ldstr    aTabindex_0// "tabIndex"
0x101cc  ldstr    a1_0// "-1"
0x101d1  ldc.i4.0
0x101d2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x101d7  ldarg.0
0x101d8  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x101dd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x101e2  brtrue.s loc_101F5
0x101e4  ldstr    aTitle_2// "title"
0x101e9  ldarg.0
0x101ea  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x101ef  ldarg.1
0x101f0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x101f5  ldarg.0
0x101f6  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x101fb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10200  brtrue.s loc_10213
0x10202  ldstr    aAccesskey// "accessKey"
0x10207  ldarg.0
0x10208  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x1020d  ldarg.1
0x1020e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10213  ldarg.0
0x10214  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x10219  brfalse.s loc_1022E
0x1021b  ldarg.1
0x1021c  ldstr    aClass_1// "class"
0x10221  ldstr    aMsCrmMenuMsCrm// "ms-crm-Menu ms-crm-Menu-disabled"
0x10226  ldc.i4.0
0x10227  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1022c  br.s     loc_1026B
0x1022e  ldstr    aClass_1// "class"
0x10233  ldarg.0
0x10234  ldfld    string Microsoft.Crm.Controls.CommandBarButton::_cssClass
0x10239  ldstr    aMsCrmMenuRead// " ms-crm-Menu-Read"
0x1023e  call     string [mscorlib]System.String::Concat(string, string)
0x10243  ldarg.1
0x10244  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10249  ldstr    aAction// "action"
0x1024e  ldarg.0
0x1024f  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Action()
0x10254  ldarg.1
0x10255  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1025a  ldarg.1
0x1025b  ldstr    aOnclick_0// "onclick"
0x10260  ldstr    aEvalThisGetatt// "eval(this.getAttribute('action'))"
0x10265  ldc.i4.0
0x10266  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1026b  ldarg.0
0x1026c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10271  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10276  brtrue.s loc_10289
0x10278  ldstr    aId// "id"
0x1027d  ldarg.0
0x1027e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10283  ldarg.1
0x10284  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x10289  ldarg.0
0x1028a  ldfld    bool Microsoft.Crm.Controls.CommandBarButton::_unSelectable
0x1028f  brfalse.s loc_102A2
0x10291  ldarg.1
0x10292  ldstr    aUnselectable// "unselectable"
0x10297  ldstr    aOn// "on"
0x1029c  ldc.i4.0
0x1029d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x102a2  ldarg.1
0x102a3  ldc.i4.s 0x3E
0x102a5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x102aa  ldarg.1
0x102ab  ldstr    aSpan_0// "SPAN"
0x102b0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x102b5  ldarg.1
0x102b6  ldstr    aClass_1// "class"
0x102bb  ldstr    aMsCrmMenuLabel// "ms-crm-Menu-Label"
0x102c0  ldc.i4.0
0x102c1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x102c6  ldarg.1
0x102c7  ldstr    aTabindex_0// "tabIndex"
0x102cc  ldstr    a1_0// "-1"
0x102d1  ldc.i4.0
0x102d2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x102d7  ldarg.1
0x102d8  ldc.i4.s 0x3E
0x102da  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x102df  ldarg.1
0x102e0  ldstr    aA_1// "A"
0x102e5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x102ea  ldarg.0
0x102eb  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x102f0  brfalse.s loc_10305
0x102f2  ldarg.1
0x102f3  ldstr    aClass_1// "class"
0x102f8  ldstr    aMsCrmMenuLabel_0// "ms-crm-Menu-Label ms-crm-Menu-disabled"
0x102fd  ldc.i4.0
0x102fe  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10303  br.s     loc_10338
0x10305  ldarg.1
0x10306  ldstr    aOnclick_0// "onclick"
0x1030b  ldstr    aReturnFalse// "return false;"
0x10310  ldc.i4.0
0x10311  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10316  ldarg.1
0x10317  ldstr    aHref// "href"
0x1031c  ldstr    aJavascriptOncl// "javascript:onclick();"
0x10321  ldc.i4.0
0x10322  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10327  ldarg.1
0x10328  ldstr    aClass_1// "class"
0x1032d  ldstr    aMsCrmMenuLabel// "ms-crm-Menu-Label"
0x10332  ldc.i4.0
0x10333  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10338  ldarg.1
0x10339  ldstr    aTarget// "target"
0x1033e  ldstr    aSelf// "_self"
0x10343  ldc.i4.0
0x10344  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10349  ldarg.1
0x1034a  ldstr    aTabindex_0// "tabIndex"
0x1034f  ldstr    a0// "0"
0x10354  ldc.i4.0
0x10355  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1035a  ldarg.1
0x1035b  ldc.i4.s 0x3E
0x1035d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x10362  ldstr    asc_3280A// ""
0x10367  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1036c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10371  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri source)
0x10376  stloc.1
0x10377  ldarg.0
0x10378  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0x1037d  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x10382  brtrue   loc_10464
0x10387  ldstr    aFirst// "First"
0x1038c  stloc.2
0x1038d  ldarg.0
0x1038e  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x10393  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10398  brfalse.s loc_103B3
0x1039a  ldarg.0
0x1039b  call     instance bool Microsoft.Crm.Controls.CommandBarButton::get_DownArrow()
0x103a0  brfalse.s loc_103B3
0x103a2  ldloc.0
0x103a3  brfalse.s loc_103AD
0x103a5  ldstr    aRtl_0// "RTL"
0x103aa  stloc.2
0x103ab  br.s     loc_103B3
0x103ad  ldstr    aLtr_0// "LTR"
0x103b2  stloc.2
0x103b3  ldloc.1
0x103b4  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ClearExpando()
0x103b9  ldloc.1
0x103ba  ldarg.0
0x103bb  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0x103c0  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_Source(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri value)
0x103c5  ldloc.1
0x103c6  ldstr    aAriaHidden// "aria-hidden"
0x103cb  ldstr    aTrue// "true"
0x103d0  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x103d5  ldloc.1
0x103d6  ldstr    aAlt// "alt"
0x103db  ldarg.0
0x103dc  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x103e1  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x103e6  ldloc.1
0x103e7  ldstr    aTabindex_0// "tabIndex"
0x103ec  ldstr    a1_0// "-1"
0x103f1  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x103f6  ldarg.0
0x103f7  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x103fc  brfalse.s loc_10411
0x103fe  ldloc.1
0x103ff  ldstr    aMsCrmMenuButto_1// "ms-crm-Menu-Button-disabled ms-crm-Menu"...
0x10404  ldloc.2
0x10405  call     string [mscorlib]System.String::Concat(string, string)
0x1040a  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x1040f  br.s     loc_10422
0x10411  ldloc.1
0x10412  ldstr    aMsCrmMenuButto_0// "ms-crm-Menu-Button"
0x10417  ldloc.2
0x10418  call     string [mscorlib]System.String::Concat(string, string)
0x1041d  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x10422  ldarg.0
0x10423  call     instance bool Microsoft.Crm.Controls.CommandBarButton::get_FlipImageInRightToLeft()
0x10428  brfalse.s loc_10440
0x1042a  ldloc.1
0x1042b  dup
0x1042c  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_CssClass()
0x10431  ldstr    aMsCrmRtlFlip// " ms-crm-RTL-Flip"
0x10436  call     string [mscorlib]System.String::Concat(string, string)
0x1043b  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x10440  ldarg.0
0x10441  ldfld    bool Microsoft.Crm.Controls.CommandBarButton::_unSelectable
0x10446  brfalse.s loc_10458
0x10448  ldloc.1
0x10449  ldstr    aUnselectable// "unselectable"
0x1044e  ldstr    aOn// "on"
0x10453  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x10458  ldarg.1
0x10459  ldloc.1
0x1045a  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_OuterHtml()
0x1045f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x10464  ldarg.1
0x10465  ldstr    aSpan_0// "SPAN"
0x1046a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1046f  ldarg.1
0x10470  ldstr    aTabindex_0// "tabIndex"
0x10475  ldstr    a1_0// "-1"
0x1047a  ldc.i4.0
0x1047b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10480  ldarg.0
0x10481  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x10486  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1048b  brtrue   loc_10511
0x10490  ldstr    aClass_1// "class"
0x10495  ldstr    aMsCrmMenuitemT// "ms-crm-MenuItem-Text"
0x1049a  ldarg.0
0x1049b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0x104a0  callvirt instance string [mscorlib]System.Object::ToString()
0x104a5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x104aa  ldc.i4.0
0x104ab  ceq
0x104ad  ldarg.0
0x104ae  call     instance bool Microsoft.Crm.Controls.CommandBarButton::get_DownArrow()
0x104b3  call     string Microsoft.Crm.Controls.CommandBarButton::GetTextClassVariant(bool isIcon, bool isDownArrow)
0x104b8  call     string [mscorlib]System.String::Concat(string, string)
0x104bd  ldarg.1
0x104be  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x104c3  ldarg.0
0x104c4  ldfld    bool Microsoft.Crm.Controls.CommandBarButton::_unSelectable
0x104c9  brfalse.s loc_104DC
0x104cb  ldarg.1
0x104cc  ldstr    aUnselectable// "unselectable"
0x104d1  ldstr    aOn// "on"
0x104d6  ldc.i4.0
0x104d7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x104dc  ldarg.1
0x104dd  ldc.i4.s 0x3E
0x104df  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x104e4  ldarg.1
0x104e5  ldarg.0
0x104e6  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x104eb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x104f0  ldarg.0
0x104f1  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x104f6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x104fb  ldstr    aU// "<u>"
0x10500  ldstr    aU_0// "</u>"
0x10505  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::StringInjector(string, string, string, string)
0x1050a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1050f  br.s     loc_1053B
0x10511  ldarg.1
0x10512  ldstr    aStyle_0// "style"
0x10517  ldstr    aDisplayNone// "display:none"
0x1051c  ldc.i4.0
0x1051d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x10522  ldarg.1
0x10523  ldc.i4.s 0x3E
0x10525  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1052a  ldarg.1
0x1052b  ldarg.0
0x1052c  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x10531  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x10536  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1053b  ldarg.1
0x1053c  ldstr    aSpan_0// "SPAN"
0x10541  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x10546  ldarg.0
0x10547  call     instance bool Microsoft.Crm.Controls.CommandBarButton::get_DownArrow()
0x1054c  brfalse.s loc_105CC
0x1054e  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x10553  ldc.i4.1
0x10554  newarr   [mscorlib]System.Char
0x10559  dup
0x1055a  ldc.i4.0
0x1055b  ldc.i4.s 0x2F
0x1055d  stelem.i2
0x1055e  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x10563  ldstr    aImgsMnudownGif// "/_imgs/mnudown.gif"
0x10568  call     string [mscorlib]System.String::Concat(string, string)
0x1056d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10572  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10577  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri source)
0x1057c  stloc.3
0x1057d  ldloc.3
0x1057e  ldstr    aAlt// "alt"
0x10583  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x10588  ldstr    aCommandbarMenu// "CommandBar.MenuDown.AltTag"
0x1058d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
  ... truncated ...
```
