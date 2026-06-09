# Microsoft.Crm.Application.Forms.FormTab::RenderHeaderForRead

- ea: `0x39540`
- end: `0x39a07`
- name: `Microsoft.Crm.Application.Forms.FormTab::RenderHeaderForRead`
- size: `1223`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x390d0`

## callees

- `0x2f7d0`
- `0x36030`
- `0x36070`
- `0x392c0`
- `0x39540`
- `0x39a10`

## string_xrefs

- `0x3968c`: `dataImagePath`
- `0x3979d`: `dataImagePath`
- `0x39741`: `dataClassId`
- `0x397d4`: `dataClassId`

## pseudocode

```c

```

## disassembly

```asm
0x39540  ldarg.1
0x39541  ldstr    aDivClassMsCrmI_5// "<div class=\"ms-crm-InlineTabHeader ms-"...
0x39546  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3954b  ldstr    aId_1// "id"
0x39550  ldarg.0
0x39551  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x39556  ldstr    aHeader_0// "_Header"
0x3955b  call     string [mscorlib]System.String::Concat(string, string)
0x39560  ldarg.1
0x39561  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x39566  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x3956b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x39570  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsInternetExplorer(class [System.Web]System.Web.HttpRequest)
0x39575  brfalse.s loc_395BE
0x39577  ldstr    aTitle// "title"
0x3957c  ldarg.0
0x3957d  callvirt instance string Microsoft.Crm.Application.Forms.FormControlWithLabel::get_Label()
0x39582  ldarg.1
0x39583  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x39588  ldstr    aAriaLabelledby// "aria-labelledby"
0x3958d  ldarg.0
0x3958e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x39593  ldstr    aExpander// "_Expander"
0x39598  call     string [mscorlib]System.String::Concat(string, string)
0x3959d  ldarg.1
0x3959e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x395a3  ldstr    aAriaDescribedb// "aria-describedby"
0x395a8  ldarg.0
0x395a9  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x395ae  ldstr    aExpander// "_Expander"
0x395b3  call     string [mscorlib]System.String::Concat(string, string)
0x395b8  ldarg.1
0x395b9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x395be  ldarg.0
0x395bf  call     instance bool Microsoft.Crm.Application.Forms.FormTab::get_IsCollapsed()
0x395c4  brfalse.s loc_395D8
0x395c6  ldstr    aAriaExpanded// "aria-expanded"
0x395cb  ldstr    aFalse// "false"
0x395d0  ldarg.1
0x395d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x395d6  br.s     loc_395E8
0x395d8  ldstr    aAriaExpanded// "aria-expanded"
0x395dd  ldstr    aTrue// "true"
0x395e2  ldarg.1
0x395e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x395e8  ldstr    aRole// "role"
0x395ed  ldstr    aLink// "link"
0x395f2  ldarg.1
0x395f3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x395f8  ldarg.1
0x395f9  ldstr    aTabindex// "tabindex"
0x395fe  ldarg.0
0x395ff  callvirt instance int32 Microsoft.Crm.Application.Forms.CompositeControl::get_TabIndex()
0x39604  stloc.2
0x39605  ldloca.s 2
0x39607  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3960c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x39611  ldc.i4.0
0x39612  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x39617  ldarg.1
0x39618  ldc.i4.s 0x3E
0x3961a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x3961f  ldarg.1
0x39620  ldstr    aDivClassMsCrmI_6// "<div class=\"ms-crm-InlineTabHeaderExpa"...
0x39625  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3962a  ldstr    aId_1// "id"
0x3962f  ldarg.0
0x39630  callvirt instance string Microsoft.Crm.Application.Forms.FormControlWithLabel::get_Name()
0x39635  ldstr    aHeaderImageDiv// "_header_image_div"
0x3963a  call     string [mscorlib]System.String::Concat(string, string)
0x3963f  ldarg.1
0x39640  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x39645  ldarg.1
0x39646  ldc.i4.s 0x3E
0x39648  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x3964d  ldarg.1
0x3964e  ldstr    aA_1// "<a "
0x39653  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x39658  ldstr    aOnclick// "onclick"
0x3965d  ldstr    aReturnFalse_1// "return false;"
0x39662  ldarg.1
0x39663  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x39668  ldarg.1
0x39669  ldstr    aTabindex// "tabindex"
0x3966e  ldstr    a1// "-1"
0x39673  ldc.i4.0
0x39674  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x39679  ldarg.0
0x3967a  ldarg.0
0x3967b  call     instance bool Microsoft.Crm.Application.Forms.FormTab::get_IsCollapsed()
0x39680  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Forms.FormTab::FillAttributeValues(bool IsTabCollapsed)
0x39685  stloc.0
0x39686  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x3968b  ldloc.0
0x3968c  ldstr    aDataimagepath// "dataImagePath"
0x39691  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x39696  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3969b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x396a0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x396a5  stloc.1
0x396a6  ldarg.1
0x396a7  ldstr    aImgSrc0ClassMs// "><img src=\"{0}\" class=\"ms-crm-Inline"...
0x396ac  ldloc.1
0x396ad  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x396b2  callvirt instance string [mscorlib]System.Object::ToString()
0x396b7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x396bc  ldloc.1
0x396bd  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x396c2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x396c7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x396cc  ldstr    aId_1// "id"
0x396d1  ldarg.0
0x396d2  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x396d7  ldstr    aExpander// "_Expander"
0x396dc  call     string [mscorlib]System.String::Concat(string, string)
0x396e1  ldarg.1
0x396e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x396e7  ldstr    aAlt// "alt"
0x396ec  ldloc.0
0x396ed  ldstr    aDataimagealt// "dataImageAlt"
0x396f2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x396f7  ldarg.1
0x396f8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x396fd  ldstr    aTitle// "title"
0x39702  ldloc.0
0x39703  ldstr    aDataimagealt// "dataImageAlt"
0x39708  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x3970d  ldarg.1
0x3970e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x39713  ldarg.1
0x39714  ldstr    aTabindex// "tabindex"
0x39719  ldstr    a1// "-1"
0x3971e  ldc.i4.0
0x3971f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x39724  ldloc.0
0x39725  ldstr    aDataaltid// "dataAltId"
0x3972a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x3972f  ldloc.0
0x39730  ldstr    aDataimagealt// "dataImageAlt"
0x39735  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x3973a  ldarg.1
0x3973b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x39740  ldloc.0
0x39741  ldstr    aDataclassid// "dataClassId"
0x39746  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x3974b  ldstr    aMsCrmInlinetab_2// "ms-crm-InlineTabExpander {0}"
0x39750  ldloc.1
0x39751  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x39756  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x3975b  call     string [mscorlib]System.String::Format(string, object)
0x39760  ldarg.1
0x39761  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x39766  ldloc.0
0x39767  ldstr    aDataimagesrcid// "dataImageSrcId"
0x3976c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x39771  ldloc.1
0x39772  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x39777  callvirt instance string [mscorlib]System.Object::ToString()
0x3977c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x39781  ldarg.1
0x39782  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x39787  ldarg.0
0x39788  ldarg.0
0x39789  call     instance bool Microsoft.Crm.Application.Forms.FormTab::get_IsCollapsed()
0x3978e  ldc.i4.0
0x3978f  ceq
0x39791  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Forms.FormTab::FillAttributeValues(bool IsTabCollapsed)
0x39796  stloc.0
0x39797  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x3979c  ldloc.0
0x3979d  ldstr    aDataimagepath// "dataImagePath"
0x397a2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x397a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x397ac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x397b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x397b6  stloc.1
0x397b7  ldloc.0
0x397b8  ldstr    aDataaltid// "dataAltId"
0x397bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x397c2  ldloc.0
0x397c3  ldstr    aDataimagealt// "dataImageAlt"
0x397c8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x397cd  ldarg.1
0x397ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x397d3  ldloc.0
0x397d4  ldstr    aDataclassid// "dataClassId"
0x397d9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x397de  ldstr    aMsCrmInlinetab_2// "ms-crm-InlineTabExpander {0}"
0x397e3  ldloc.1
0x397e4  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x397e9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x397ee  call     string [mscorlib]System.String::Format(string, object)
0x397f3  ldarg.1
0x397f4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x397f9  ldloc.0
0x397fa  ldstr    aDataimagesrcid// "dataImageSrcId"
0x397ff  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x39804  ldloc.1
0x39805  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x3980a  callvirt instance string [mscorlib]System.Object::ToString()
0x3980f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x39814  ldarg.1
0x39815  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3981a  ldarg.1
0x3981b  ldstr    aADiv// "/></a></div>"
0x39820  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x39825  ldarg.1
0x39826  ldstr    aDivClassMsCrmI_7// "<div class=\"ms-crm-InlineTabHeaderText"...
0x3982b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x39830  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x39835  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3983a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSafari(class [System.Web]System.Web.HttpRequest)
0x3983f  brtrue.s loc_39852
0x39841  ldarg.1
0x39842  ldstr    aTabindex// "tabindex"
0x39847  ldstr    a1// "-1"
0x3984c  ldc.i4.0
0x3984d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x39852  ldarg.1
0x39853  ldstr    aAClassMsCrmInl// "><a class=\"ms-crm-InlineTabHeaderText"...
0x39858  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3985d  ldstr    aOnclick// "onclick"
0x39862  ldstr    aReturnFalse_1// "return false;"
0x39867  ldarg.1
0x39868  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3986d  ldstr    aName// "name"
0x39872  ldarg.0
0x39873  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x39878  ldarg.1
0x39879  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3987e  ldstr    aId_1// "id"
0x39883  ldarg.0
0x39884  callvirt instance string Microsoft.Crm.Application.Forms.FormControlWithLabel::get_Name()
0x39889  ldstr    aHeadertextAnch// "_headerText_anchor"
0x3988e  call     string [mscorlib]System.String::Concat(string, string)
0x39893  ldarg.1
0x39894  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x39899  ldarg.1
0x3989a  ldstr    aTabindex// "tabindex"
0x3989f  ldstr    a1// "-1"
0x398a4  ldc.i4.0
0x398a5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x398aa  ldstr    aTitle// "title"
0x398af  ldarg.0
0x398b0  call     instance bool Microsoft.Crm.Application.Forms.FormTab::get_IsCollapsed()
0x398b5  brtrue.s loc_398C8
0x398b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x398bc  ldstr    aFormtabTabhead_0// "FormTab.TabHeader.CollapseToolTip"
0x398c1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x398c6  br.s     loc_398D7
0x398c8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x398cd  ldstr    aFormtabTabhead// "FormTab.TabHeader.ExpandToolTip"
0x398d2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x398d7  ldarg.1
0x398d8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x398dd  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x398e2  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x398e7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSafari(class [System.Web]System.Web.HttpRequest)
0x398ec  brfalse.s loc_3990F
0x398ee  ldarg.1
0x398ef  ldstr    aTabindex// "tabindex"
0x398f4  ldarg.0
0x398f5  callvirt instance int32 Microsoft.Crm.Application.Forms.CompositeControl::get_TabIndex()
0x398fa  stloc.2
0x398fb  ldloca.s 2
0x398fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39902  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x39907  ldc.i4.0
0x39908  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x3990d  br.s     loc_39920
0x3990f  ldarg.1
0x39910  ldstr    aTabindex// "tabindex"
0x39915  ldstr    a1// "-1"
0x3991a  ldc.i4.0
0x3991b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x39920  ldarg.1
0x39921  ldstr    asc_111CB6// ">"
0x39926  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3992b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x39930  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x39935  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSafari(class [System.Web]System.Web.HttpRequest)
0x3993a  brfalse.s loc_399A2
0x3993c  ldarg.1
0x3993d  ldstr    aSpanClassMsCrm_4// "<span class=\"ms-crm-Form\">"
0x39942  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x39947  ldarg.1
0x39948  ldstr    aH2ClassMsCrmFo_0// "<h2 class=\"ms-crm-Form\""
0x3994d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x39952  ldstr    aId_1// "id"
0x39957  ldarg.0
0x39958  callvirt instance string Microsoft.Crm.Application.Forms.FormControlWithLabel::get_Name()
0x3995d  ldstr    aHeaderH2// "_header_h2"
0x39962  call     string [mscorlib]System.String::Concat(string, string)
0x39967  ldarg.1
0x39968  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3996d  ldarg.1
0x3996e  ldstr    aTabindex// "tabindex"
0x39973  ldstr    a1// "-1"
0x39978  ldc.i4.0
0x39979  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
  ... truncated ...
```
