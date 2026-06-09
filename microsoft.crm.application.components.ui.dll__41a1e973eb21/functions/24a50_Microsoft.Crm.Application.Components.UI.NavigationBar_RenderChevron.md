# Microsoft.Crm.Application.Components.UI.NavigationBar::RenderChevron

- ea: `0x24a50`
- end: `0x24c1c`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBar::RenderChevron`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x24a00`

## callees

- `0x142c0`
- `0x1a0a0`
- `0x1a0d0`
- `0x1a350`
- `0x1a390`
- `0x24a50`
- `0x24c20`
- `0x24c30`

## pseudocode

```c

```

## disassembly

```asm
0x24a50  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x24a55  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x24a5a  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x24a5f  stloc.0
0x24a60  ldarg.3
0x24a61  ldstr    aSpan_1// "span"
0x24a66  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x24a6b  ldarg.3
0x24a6c  ldstr    aId// "id"
0x24a71  ldarg.2
0x24a72  ldc.i4.0
0x24a73  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x24a78  ldarg.3
0x24a79  ldc.i4.s 0x3E
0x24a7b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x24a80  ldarg.3
0x24a81  ldstr    aA_2// "a"
0x24a86  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x24a8b  ldstr    aId// "id"
0x24a90  ldarg.2
0x24a91  ldstr    aAnchor// "_anchor"
0x24a96  call     string [mscorlib]System.String::Concat(string, string)
0x24a9b  ldarg.3
0x24a9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x24aa1  ldarg.0
0x24aa2  ldarg.3
0x24aa3  callvirt instance void Microsoft.Crm.Application.Components.UI.NavigationBar::ModifyChevronAnchorAttributes(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x24aa8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24aad  ldarg.0
0x24aae  call     instance string Microsoft.Crm.Application.Components.UI.NavigationBar::get_NavigationOnClickAction()
0x24ab3  ldc.i4.1
0x24ab4  newarr   [mscorlib]System.Object
0x24ab9  dup
0x24aba  ldc.i4.0
0x24abb  ldarg.1
0x24abc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x24ac1  stelem.ref
0x24ac2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24ac7  stloc.1
0x24ac8  ldstr    aOnclick_0// "onclick"
0x24acd  ldloc.1
0x24ace  ldarg.3
0x24acf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x24ad4  ldarg.3
0x24ad5  ldstr    aHref// "href"
0x24ada  ldstr    asc_3B9B4// "#"
0x24adf  ldc.i4.0
0x24ae0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x24ae5  ldarg.3
0x24ae6  ldc.i4.s 0x3E
0x24ae8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x24aed  ldarg.3
0x24aee  ldstr    aImg_0// "img"
0x24af3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x24af8  ldstr    aId// "id"
0x24afd  ldarg.2
0x24afe  ldstr    aImage_0// "_image"
0x24b03  call     string [mscorlib]System.String::Concat(string, string)
0x24b08  ldarg.3
0x24b09  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x24b0e  ldloc.0
0x24b0f  brfalse.s loc_24B4E
0x24b11  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x24b16  ldc.i4.1
0x24b17  newarr   [mscorlib]System.Char
0x24b1c  dup
0x24b1d  ldc.i4.0
0x24b1e  ldc.i4.s 0x2F
0x24b20  stelem.i2
0x24b21  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x24b26  ldstr    aImgsNavrightPn// "/_imgs/navright.png"
0x24b2b  call     string [mscorlib]System.String::Concat(string, string)
0x24b30  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24b35  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24b3a  stloc.2
0x24b3b  ldarg.3
0x24b3c  ldstr    aImgbase// "imgBase"
0x24b41  ldstr    aImgsNavright// "/_imgs/navRight"
0x24b46  ldc.i4.0
0x24b47  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x24b4c  br.s     loc_24B89
0x24b4e  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x24b53  ldc.i4.1
0x24b54  newarr   [mscorlib]System.Char
0x24b59  dup
0x24b5a  ldc.i4.0
0x24b5b  ldc.i4.s 0x2F
0x24b5d  stelem.i2
0x24b5e  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x24b63  ldstr    aImgsNavleftPng// "/_imgs/navleft.png"
0x24b68  call     string [mscorlib]System.String::Concat(string, string)
0x24b6d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24b72  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24b77  stloc.2
0x24b78  ldarg.3
0x24b79  ldstr    aImgbase// "imgBase"
0x24b7e  ldstr    aImgsNavleft// "/_imgs/navLeft"
0x24b83  ldc.i4.0
0x24b84  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x24b89  call     class Microsoft.Crm.Application.Components.UI.ImageStrip Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x24b8e  ldloc.2
0x24b8f  callvirt instance class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri imagePath)
0x24b94  stloc.3
0x24b95  ldstr    aSrc_0// "src"
0x24b9a  ldloc.3
0x24b9b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x24ba0  callvirt instance string [mscorlib]System.Object::ToString()
0x24ba5  ldarg.3
0x24ba6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x24bab  ldstr    aClass_1// "class"
0x24bb0  ldstr    aHeading// "Heading "
0x24bb5  ldloc.3
0x24bb6  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x24bbb  call     string [mscorlib]System.String::Concat(string, string)
0x24bc0  ldarg.3
0x24bc1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x24bc6  ldstr    aTitle_2// "title"
0x24bcb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24bd0  ldstr    aNavbarExpanded// "NavBar_Expanded_ToolTip"
0x24bd5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24bda  ldarg.3
0x24bdb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x24be0  ldstr    aAlt// "alt"
0x24be5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24bea  ldstr    aNavbarExpanded// "NavBar_Expanded_ToolTip"
0x24bef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24bf4  ldarg.3
0x24bf5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x24bfa  ldarg.3
0x24bfb  ldstr    asc_4886A// " />"
0x24c00  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x24c05  ldarg.3
0x24c06  ldstr    aA_2// "a"
0x24c0b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x24c10  ldarg.3
0x24c11  ldstr    aSpan_1// "span"
0x24c16  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x24c1b  ret
```
