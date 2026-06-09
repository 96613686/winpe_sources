# Microsoft.Crm.Application.Components.UI.DateTimeUI::RenderDateControl

- ea: `0x16260`
- end: `0x16582`
- name: `Microsoft.Crm.Application.Components.UI.DateTimeUI::RenderDateControl`
- size: `802`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x15ff0`

## callees

- `0x142c0`
- `0x16260`
- `0x167f0`
- `0x1a0a0`
- `0x1a0d0`
- `0x1a350`
- `0x1a390`
- `0x23c20`
- `0x241d0`
- `0x241f0`
- `0x24280`
- `0x242c0`

## string_xrefs

- `0x162e8`: `Recommended_Fields_Background_Color`
- `0x163bb`: ` contentEditable="false" class="ms-crm-ReadOnlyDateTime"`

## pseudocode

```c

```

## disassembly

```asm
0x16260  ldarg.1
0x16261  ldstr    aTdClassDatetim// "<td class=\"DateTimeUI_RenderDateContro"...
0x16266  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1626b  ldstr    aImeMode// "ime-mode:"
0x16270  stloc.0
0x16271  ldloc.0
0x16272  ldarg.0
0x16273  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ImeMode()
0x16278  stloc.2
0x16279  ldloca.s 2
0x1627b  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode
0x16281  callvirt instance string [mscorlib]System.Object::ToString()
0x16286  ldstr    asc_43B56// ";"
0x1628b  call     string [mscorlib]System.String::Concat(string, string, string)
0x16290  stloc.0
0x16291  ldarg.0
0x16292  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Required()
0x16297  stloc.3
0x16298  ldloc.3
0x16299  switch   loc_16314, loc_16314, loc_162B0, loc_162E3
0x162ae  br.s     loc_16314
0x162b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x162b5  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x162ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x162bf  stloc.s  4
0x162c1  ldloc.s  4
0x162c3  brfalse.s loc_16314
0x162c5  ldloc.s  4
0x162c7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x162cc  brfalse.s loc_16314
0x162ce  ldloc.0
0x162cf  ldstr    aBackgroundColo// "background-color:"
0x162d4  ldloc.s  4
0x162d6  ldstr    asc_43B56// ";"
0x162db  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x162e0  stloc.0
0x162e1  br.s     loc_16314
0x162e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x162e8  ldstr    aRecommendedFie// "Recommended_Fields_Background_Color"
0x162ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x162f2  stloc.s  5
0x162f4  ldloc.s  5
0x162f6  brfalse.s loc_16314
0x162f8  ldloc.s  5
0x162fa  callvirt instance int32 [mscorlib]System.String::get_Length()
0x162ff  brfalse.s loc_16314
0x16301  ldloc.0
0x16302  ldstr    aBackgroundColo// "background-color:"
0x16307  ldloc.s  5
0x16309  ldstr    asc_43B56// ";"
0x1630e  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x16313  stloc.0
0x16314  ldloc.0
0x16315  ldarg.1
0x16316  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x1631b  ldarg.1
0x1631c  ldstr    aValue_1// "\" value=\""
0x16321  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16326  ldarg.0
0x16327  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_Value()
0x1632c  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x16331  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x16336  brfalse.s loc_16358
0x16338  ldarg.1
0x16339  ldarg.0
0x1633a  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_Value()
0x1633f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x16344  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x16349  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1634e  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatDate(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16353  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16358  ldarg.1
0x16359  ldc.i4.s 0x22
0x1635b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x16360  ldarg.1
0x16361  ldstr    aId_3// "ID"
0x16366  ldstr    aDateinput// "DateInput"
0x1636b  ldc.i4.0
0x1636c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16371  ldarg.0
0x16372  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x16377  brfalse.s loc_163AA
0x16379  ldarg.1
0x1637a  ldstr    aTabindex_3// " tabindex=\""
0x1637f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16384  ldarg.1
0x16385  ldarg.0
0x16386  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x1638b  stloc.3
0x1638c  ldloca.s 3
0x1638e  ldstr    aD_1// "D"
0x16393  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16398  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1639d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x163a2  ldarg.1
0x163a3  ldc.i4.s 0x22
0x163a5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x163aa  ldarg.0
0x163ab  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x163b0  brtrue.s loc_163BA
0x163b2  ldarg.0
0x163b3  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x163b8  brfalse.s loc_163C5
0x163ba  ldarg.1
0x163bb  ldstr    aContenteditabl_0// " contentEditable=\"false\" class=\"ms-c"...
0x163c0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x163c5  ldarg.0
0x163c6  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x163cb  brfalse.s loc_163D8
0x163cd  ldarg.1
0x163ce  ldstr    aDisabledTrue// " disabled=\"true\""
0x163d3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x163d8  ldarg.1
0x163d9  ldstr    aLabelForDatein// "><label for=\"DateInput\"/></td>"
0x163de  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x163e3  ldarg.1
0x163e4  ldstr    aTdTd// "<td></td>"
0x163e9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x163ee  ldarg.1
0x163ef  ldstr    aTd_0// "<td>"
0x163f4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x163f9  ldarg.1
0x163fa  ldstr    aImg_1// "<img "
0x163ff  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16404  ldstr    aId_4// " id"
0x16409  ldarg.0
0x1640a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1640f  ldstr    aImg_0// "img"
0x16414  call     string [mscorlib]System.String::Concat(string, string)
0x16419  ldarg.1
0x1641a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1641f  ldstr    aAlt// "alt"
0x16424  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16429  ldstr    aWebFormsStyles_2// "Web._forms.styles.IMG.dtm.htc_27_0"
0x1642e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16433  ldarg.1
0x16434  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x16439  ldstr    aTitle_2// "title"
0x1643e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16443  ldstr    aWebFormsStyles_2// "Web._forms.styles.IMG.dtm.htc_27_0"
0x16448  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1644d  ldarg.1
0x1644e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x16453  ldarg.0
0x16454  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x16459  brtrue.s loc_16463
0x1645b  ldarg.0
0x1645c  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x16461  brfalse.s loc_164AF
0x16463  call     class Microsoft.Crm.Application.Components.UI.ImageStrip Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x16468  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1646d  ldc.i4.1
0x1646e  newarr   [mscorlib]System.Char
0x16473  dup
0x16474  ldc.i4.0
0x16475  ldc.i4.s 0x2F
0x16477  stelem.i2
0x16478  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1647d  ldstr    aImgsBtnDisCalG// "/_imgs/btn_dis_cal.gif"
0x16482  call     string [mscorlib]System.String::Concat(string, string)
0x16487  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1648c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16491  callvirt instance class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri imagePath)
0x16496  stloc.1
0x16497  ldarg.1
0x16498  ldstr    aDisabledTrue_0// " disabled='true'"
0x1649d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x164a2  ldarg.1
0x164a3  ldstr    aTabindex1// " tabindex=\"-1\""
0x164a8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x164ad  br.s     loc_16514
0x164af  call     class Microsoft.Crm.Application.Components.UI.ImageStrip Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x164b4  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x164b9  ldc.i4.1
0x164ba  newarr   [mscorlib]System.Char
0x164bf  dup
0x164c0  ldc.i4.0
0x164c1  ldc.i4.s 0x2F
0x164c3  stelem.i2
0x164c4  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x164c9  ldstr    aImgsBtnOffCalG// "/_imgs/btn_off_cal.gif"
0x164ce  call     string [mscorlib]System.String::Concat(string, string)
0x164d3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x164d8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x164dd  callvirt instance class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri imagePath)
0x164e2  stloc.1
0x164e3  ldarg.1
0x164e4  ldstr    aTabindex_3// " tabindex=\""
0x164e9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x164ee  ldarg.1
0x164ef  ldarg.0
0x164f0  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x164f5  stloc.3
0x164f6  ldloca.s 3
0x164f8  ldstr    aD_1// "D"
0x164fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16502  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x16507  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1650c  ldarg.1
0x1650d  ldc.i4.s 0x22
0x1650f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x16514  ldarg.1
0x16515  ldstr    aSrc0ClassMsCrm// " src =\"{0}\" class=\"ms-crm-DateTime {"...
0x1651a  ldloc.1
0x1651b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x16520  callvirt instance string [mscorlib]System.Object::ToString()
0x16525  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1652a  ldloc.1
0x1652b  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x16530  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x16535  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x1653a  ldarg.1
0x1653b  ldstr    aDiv_5// "<div "
0x16540  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16545  ldstr    aId// "id"
0x1654a  ldarg.0
0x1654b  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x16550  ldstr    aCalcontainer// "CalContainer"
0x16555  call     string [mscorlib]System.String::Concat(string, string)
0x1655a  ldarg.1
0x1655b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x16560  ldarg.1
0x16561  ldstr    aStyleWidth0pxH// " style=\"width: 0px; height: 0px; posit"...
0x16566  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1656b  ldarg.1
0x1656c  ldstr    aTd// "</td>"
0x16571  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16576  ldarg.1
0x16577  ldstr    aTdTd// "<td></td>"
0x1657c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16581  ret
```
