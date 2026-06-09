# Microsoft.Crm.Application.Forms.FormCell::RenderLabel

- ea: `0x357c0`
- end: `0x35bdf`
- name: `Microsoft.Crm.Application.Forms.FormCell::RenderLabel`
- size: `1055`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x33870`
- `0x33880`

## callees

- `0x2f6c0`
- `0x332b0`
- `0x332d0`
- `0x33380`
- `0x33400`
- `0x335d0`
- `0x337a0`
- `0x337d0`
- `0x33830`
- `0x33850`
- `0x33860`
- `0x34130`
- `0x357c0`
- `0x35be0`
- `0x35d70`
- `0x36030`
- `0x36050`
- `0x36060`

## string_xrefs

- `0x3594e`: `ms-crm-Field-Recommended`
- `0x359a2`: `createdon`
- `0x35ab9`: `Forms.Recommended.AltTag`
- `0x35ae3`: `/_imgs/frm_recommended.gif`

## pseudocode

```c

```

## disassembly

```asm
0x357c0  ldarg.0
0x357c1  call     instance bool Microsoft.Crm.Application.Forms.FormCell::get_IsLabelControlHost()
0x357c6  brtrue.s loc_357D0
0x357c8  ldarg.0
0x357c9  call     instance bool Microsoft.Crm.Application.Forms.FormCell::get_IsButtonControlHost()
0x357ce  brfalse.s loc_357D1
0x357d0  ret
0x357d1  ldarg.0
0x357d2  call     instance bool Microsoft.Crm.Application.Forms.CompositeControl::get_Hidden()
0x357d7  brfalse.s loc_357E0
0x357d9  ldarg.0
0x357da  ldc.i4.0
0x357db  call     instance void Microsoft.Crm.Application.Forms.FormControlWithLabel::set_ShowLabel(bool value)
0x357e0  ldarg.1
0x357e1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x357e6  stloc.0
0x357e7  ldarg.0
0x357e8  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Application.Forms.FormCell::get_FirstChild()
0x357ed  stloc.1
0x357ee  ldarg.0
0x357ef  call     instance bool Microsoft.Crm.Application.Forms.FormCell::get_IsLabelInSeparateCell()
0x357f4  brtrue.s loc_357FD
0x357f6  ldstr    aDiv_3// "div"
0x357fb  br.s     loc_35802
0x357fd  ldstr    aTd_0// "td"
0x35802  stloc.2
0x35803  ldarg.1
0x35804  ldloc.2
0x35805  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x3580a  ldarg.0
0x3580b  call     instance bool Microsoft.Crm.Application.Forms.FormControlWithLabel::get_ShowLabel()
0x35810  brfalse.s loc_3581A
0x35812  ldarg.0
0x35813  ldfld    bool Microsoft.Crm.Application.Forms.FormCell::_renderAsVisible
0x35818  brtrue.s loc_3582B
0x3581a  ldarg.1
0x3581b  ldstr    aStyle_0// "style"
0x35820  ldstr    aDisplayNone// "display:none"
0x35825  ldc.i4.0
0x35826  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x3582b  ldarg.0
0x3582c  call     instance bool Microsoft.Crm.Application.Forms.FormControlWithLabel::get_ShowLabel()
0x35831  brtrue.s loc_35844
0x35833  ldarg.1
0x35834  ldstr    aSl// "sl"
0x35839  ldstr    aFalse// "false"
0x3583e  ldc.i4.0
0x3583f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x35844  ldarg.0
0x35845  ldarg.1
0x35846  ldstr    a0C// "{0}_c"
0x3584b  call     instance void Microsoft.Crm.Application.Forms.FormCell::RenderContainerIdAttribute(class [System.Web]System.Web.UI.HtmlTextWriter output, string format)
0x35850  ldarg.0
0x35851  call     instance int32 Microsoft.Crm.Application.Forms.FormCell::get_RowSpan()
0x35856  ldc.i4.1
0x35857  ble.s    loc_3588A
0x35859  ldloc.2
0x3585a  ldstr    aTd_0// "td"
0x3585f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x35864  brfalse.s loc_3588A
0x35866  ldstr    aRowspan// "rowspan"
0x3586b  ldarg.0
0x3586c  call     instance int32 Microsoft.Crm.Application.Forms.FormCell::get_RowSpan()
0x35871  stloc.s  4
0x35873  ldloca.s 4
0x35875  ldstr    aD// "D"
0x3587a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3587f  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x35884  ldarg.1
0x35885  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3588a  ldloc.1
0x3588b  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x35890  stloc.3
0x35891  ldarg.0
0x35892  ldarg.1
0x35893  ldloc.3
0x35894  call     instance bool Microsoft.Crm.Application.Forms.FormCell::RenderAttributeDescriptionTooltip(class [System.Web]System.Web.UI.HtmlTextWriter output, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl dataControl)
0x35899  brtrue.s loc_358BC
0x3589b  ldarg.0
0x3589c  call     instance bool Microsoft.Crm.Application.Forms.FormCell::get_IsRadioControlHost()
0x358a1  brfalse.s loc_358BC
0x358a3  ldarg.0
0x358a4  call     instance bool Microsoft.Crm.Application.Forms.FormCell::get_IsLabelInSeparateCell()
0x358a9  brfalse.s loc_358BC
0x358ab  ldstr    aTitle// "title"
0x358b0  ldarg.0
0x358b1  callvirt instance string Microsoft.Crm.Application.Forms.FormControlWithLabel::get_Label()
0x358b6  ldarg.1
0x358b7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x358bc  ldloc.0
0x358bd  ldstr    aClass_1// " class=\""
0x358c2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x358c7  ldarg.1
0x358c8  ldarg.0
0x358c9  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellLabelAlignment Microsoft.Crm.Application.Forms.FormCell::get_LabelAlignment()
0x358ce  call     string Microsoft.Crm.Application.Forms.FormCell::GetLabelAlignmentCssClass(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellLabelAlignment labelAlignment)
0x358d3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x358d8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x358dd  ldloc.0
0x358de  ldstr    asc_F74F4// " "
0x358e3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x358e8  ldarg.0
0x358e9  call     instance bool Microsoft.Crm.Application.Forms.FormCell::get_IsLabelInSeparateCell()
0x358ee  brfalse.s loc_35919
0x358f0  ldarg.0
0x358f1  call     instance string Microsoft.Crm.Application.Forms.FormCell::get_AdditionalCssClass()
0x358f6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x358fb  brtrue.s loc_35919
0x358fd  ldloc.0
0x358fe  ldarg.0
0x358ff  call     instance string Microsoft.Crm.Application.Forms.FormCell::get_AdditionalCssClass()
0x35904  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x35909  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3590e  ldloc.0
0x3590f  ldstr    asc_F74F4// " "
0x35914  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35919  ldarg.0
0x3591a  call     instance bool Microsoft.Crm.Application.Forms.FormCell::get_DenoteRequiredLevel()
0x3591f  brfalse.s loc_35965
0x35921  ldarg.0
0x35922  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel Microsoft.Crm.Application.Forms.FormCell::get_RequiredLevel()
0x35927  stloc.s  5
0x35929  ldloc.s  5
0x3592b  ldc.i4.1
0x3592c  sub
0x3592d  switch   loc_35940, loc_35940, loc_3594D
0x3593e  br.s     loc_3595A
0x35940  ldloc.0
0x35941  ldstr    aMsCrmFieldRequ// "ms-crm-Field-Required"
0x35946  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3594b  br.s     loc_35965
0x3594d  ldloc.0
0x3594e  ldstr    aMsCrmFieldReco// "ms-crm-Field-Recommended"
0x35953  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35958  br.s     loc_35965
0x3595a  ldloc.0
0x3595b  ldstr    aMsCrmFieldNorm// "ms-crm-Field-Normal"
0x35960  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35965  ldloc.0
0x35966  ldstr    asc_F5D2A// "\">"
0x3596b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35970  ldloc.0
0x35971  ldstr    aLabel_4// "<label "
0x35976  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3597b  ldloc.1
0x3597c  brfalse.s loc_359CB
0x3597e  ldloc.1
0x3597f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x35984  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35989  brtrue.s loc_359CB
0x3598b  ldstr    aFor// "for"
0x35990  ldloc.1
0x35991  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x35996  ldarg.1
0x35997  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3599c  ldloc.1
0x3599d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x359a2  ldstr    aCreatedon// "createdon"
0x359a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x359ac  brtrue.s loc_359C0
0x359ae  ldloc.1
0x359af  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x359b4  ldstr    aModifiedon// "modifiedon"
0x359b9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x359be  brfalse.s loc_359CB
0x359c0  ldloc.0
0x359c1  ldstr    aTabindex0// " tabindex =\"0\""
0x359c6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x359cb  ldloc.0
0x359cc  ldstr    asc_111CB6// ">"
0x359d1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x359d6  ldloc.0
0x359d7  ldarg.0
0x359d8  callvirt instance string Microsoft.Crm.Application.Forms.FormControlWithLabel::get_Label()
0x359dd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x359e2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x359e7  ldarg.0
0x359e8  call     instance bool Microsoft.Crm.Application.Forms.FormCell::get_DenoteRequiredLevel()
0x359ed  brfalse  loc_35AFE
0x359f2  ldarg.0
0x359f3  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel Microsoft.Crm.Application.Forms.FormCell::get_RequiredLevel()
0x359f8  stloc.s  5
0x359fa  ldloc.s  5
0x359fc  ldc.i4.1
0x359fd  sub
0x359fe  switch   loc_35A14, loc_35A14, loc_35AA4
0x35a0f  br       loc_35AFE
0x35a14  ldloc.0
0x35a15  ldstr    aImg// "<img "
0x35a1a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35a1f  ldstr    aAlt// "alt"
0x35a24  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x35a29  ldstr    aFormsRequiredA// "Forms.Required.AltTag"
0x35a2e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35a33  ldarg.1
0x35a34  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x35a39  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x35a3e  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x35a43  ldc.i4.1
0x35a44  newarr   [mscorlib]System.Char
0x35a49  dup
0x35a4a  ldc.i4.0
0x35a4b  ldc.i4.s 0x2F
0x35a4d  stelem.i2
0x35a4e  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x35a53  ldstr    aImgsFrmRequire// "/_imgs/frm_required.gif"
0x35a58  call     string [mscorlib]System.String::Concat(string, string)
0x35a5d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x35a62  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x35a67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x35a6c  stloc.s  6
0x35a6e  ldstr    aSrc// "src"
0x35a73  ldloc.s  6
0x35a75  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x35a7a  callvirt instance string [mscorlib]System.Object::ToString()
0x35a7f  ldarg.1
0x35a80  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x35a85  ldstr    aClass_0// "class"
0x35a8a  ldloc.s  6
0x35a8c  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x35a91  ldarg.1
0x35a92  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x35a97  ldloc.0
0x35a98  ldstr    asc_111DE8// "/>"
0x35a9d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35aa2  br.s     loc_35AFE
0x35aa4  ldloc.0
0x35aa5  ldstr    aImg// "<img "
0x35aaa  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35aaf  ldstr    aAlt// "alt"
0x35ab4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x35ab9  ldstr    aFormsRecommend// "Forms.Recommended.AltTag"
0x35abe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35ac3  ldarg.1
0x35ac4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x35ac9  ldstr    aSrc// "src"
0x35ace  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x35ad3  ldc.i4.1
0x35ad4  newarr   [mscorlib]System.Char
0x35ad9  dup
0x35ada  ldc.i4.0
0x35adb  ldc.i4.s 0x2F
0x35add  stelem.i2
0x35ade  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x35ae3  ldstr    aImgsFrmRecomme// "/_imgs/frm_recommended.gif"
0x35ae8  call     string [mscorlib]System.String::Concat(string, string)
0x35aed  ldarg.1
0x35aee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x35af3  ldloc.0
0x35af4  ldstr    asc_111DE8// "/>"
0x35af9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35afe  ldloc.3
0x35aff  brfalse  loc_35BCC
0x35b04  ldloc.3
0x35b05  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x35b0a  brfalse  loc_35BCC
0x35b0f  ldloc.3
0x35b10  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x35b15  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x35b1a  brtrue.s loc_35B62
0x35b1c  ldloc.3
0x35b1d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x35b22  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_YomiOf()
0x35b27  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35b2c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x35b31  brfalse  loc_35BCC
0x35b36  ldloc.3
0x35b37  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x35b3c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x35b41  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesById()
0x35b46  ldloc.3
0x35b47  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x35b4c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_YomiOf()
0x35b51  box      [mscorlib]System.Guid
0x35b56  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x35b5b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x35b60  brfalse.s loc_35BCC
0x35b62  ldloc.0
0x35b63  ldstr    aImg// "<img "
0x35b68  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x35b6d  ldstr    aAlt// "alt"
0x35b72  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x35b77  ldstr    aFormsSecuredAl// "Forms.Secured.AltTag"
0x35b7c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35b81  ldarg.1
0x35b82  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x35b87  ldstr    aSrc// "src"
0x35b8c  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x35b91  ldc.i4.1
0x35b92  newarr   [mscorlib]System.Char
0x35b97  dup
0x35b98  ldc.i4.0
0x35b99  ldc.i4.s 0x2F
0x35b9b  stelem.i2
0x35b9c  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x35ba1  ldstr    aImgsPermission// "/_imgs/permission_key.png"
0x35ba6  call     string [mscorlib]System.String::Concat(string, string)
0x35bab  ldarg.1
0x35bac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x35bb1  ldstr    aStyle_0// "style"
  ... truncated ...
```
