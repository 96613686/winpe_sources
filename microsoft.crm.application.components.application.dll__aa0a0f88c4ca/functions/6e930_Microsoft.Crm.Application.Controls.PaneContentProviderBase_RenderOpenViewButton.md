# Microsoft.Crm.Application.Controls.PaneContentProviderBase::RenderOpenViewButton

- ea: `0x6e930`
- end: `0x6eb41`
- name: `Microsoft.Crm.Application.Controls.PaneContentProviderBase::RenderOpenViewButton`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x6e3d0`

## callees

- `0x6cfc0`
- `0x6e930`

## string_xrefs

- `0x6e96f`: `Web.Open_View_Alt_Text`
- `0x6e9f2`: `Web.Open_View_Alt_Text`
- `0x6eab7`: `Web.Open_View_Alt_Text`
- `0x6ead1`: `Web.Open_View_Alt_Text`
- `0x6e99a`: `).openView(new Sys.UI.DomEvent(event));return false;`
- `0x6e9d8`: `).openView(new Sys.UI.DomEvent(event));return false;`
- `0x6ea63`: `/_imgs/openview.png`
- `0x6eb08`: `/_imgs/openview.png`
- `0x6ea6a`: `/_imgs/openview_visualrefresh.png`
- `0x6eb0f`: `/_imgs/openview_visualrefresh.png`

## pseudocode

```c

```

## disassembly

```asm
0x6e930  ldarg.2
0x6e931  ldstr    aSpan_1// "span"
0x6e936  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x6e93b  ldarg.2
0x6e93c  ldstr    aId_1// "id"
0x6e941  ldarg.1
0x6e942  ldc.i4.0
0x6e943  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6e948  ldarg.2
0x6e949  ldstr    aClass_0// "class"
0x6e94e  ldstr    aMsCrmVisualiza_7// "ms-crm-visualizationpane-toolbar-button"...
0x6e953  ldc.i4.0
0x6e954  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6e959  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6e95e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6e963  brfalse.s loc_6E9AA
0x6e965  ldstr    aTitle// "title"
0x6e96a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6e96f  ldstr    aWebOpenViewAlt// "Web.Open_View_Alt_Text"
0x6e974  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e979  ldarg.2
0x6e97a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x6e97f  ldarg.2
0x6e980  ldstr    aOnclick// "onclick"
0x6e985  ldstr    aFind_1// "$find("
0x6e98a  ldarg.0
0x6e98b  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6e990  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x6e995  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x6e99a  ldstr    aOpenviewNewSys// ").openView(new Sys.UI.DomEvent(event));"...
0x6e99f  call     string [mscorlib]System.String::Concat(string, string, string)
0x6e9a4  ldc.i4.0
0x6e9a5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6e9aa  ldarg.2
0x6e9ab  ldc.i4.s 0x3E
0x6e9ad  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x6e9b2  ldarg.2
0x6e9b3  ldstr    aA_0// "a"
0x6e9b8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x6e9bd  ldarg.2
0x6e9be  ldstr    aOnclick// "onclick"
0x6e9c3  ldstr    aFind_1// "$find("
0x6e9c8  ldarg.0
0x6e9c9  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6e9ce  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x6e9d3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x6e9d8  ldstr    aOpenviewNewSys// ").openView(new Sys.UI.DomEvent(event));"...
0x6e9dd  call     string [mscorlib]System.String::Concat(string, string, string)
0x6e9e2  ldc.i4.0
0x6e9e3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6e9e8  ldstr    aAriaLabel_0// "aria-label"
0x6e9ed  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6e9f2  ldstr    aWebOpenViewAlt// "Web.Open_View_Alt_Text"
0x6e9f7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6e9fc  ldarg.2
0x6e9fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x6ea02  ldarg.2
0x6ea03  ldstr    aHref// "href"
0x6ea08  ldstr    aJavascript// "javascript:;"
0x6ea0d  ldc.i4.0
0x6ea0e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6ea13  ldarg.2
0x6ea14  ldc.i4.s 0x3E
0x6ea16  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x6ea1b  ldarg.2
0x6ea1c  ldstr    aImg_0// "img"
0x6ea21  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x6ea26  ldarg.2
0x6ea27  ldstr    aId_1// "id"
0x6ea2c  ldarg.1
0x6ea2d  ldstr    aImage_3// "_image"
0x6ea32  call     string [mscorlib]System.String::Concat(string, string)
0x6ea37  ldc.i4.0
0x6ea38  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6ea3d  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x6ea42  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x6ea47  ldc.i4.1
0x6ea48  newarr   [mscorlib]System.Char
0x6ea4d  dup
0x6ea4e  ldc.i4.0
0x6ea4f  ldc.i4.s 0x2F
0x6ea51  stelem.i2
0x6ea52  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x6ea57  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6ea5c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6ea61  brtrue.s loc_6EA6A
0x6ea63  ldstr    aImgsOpenviewPn// "/_imgs/openview.png"
0x6ea68  br.s     loc_6EA6F
0x6ea6a  ldstr    aImgsOpenviewVi// "/_imgs/openview_visualrefresh.png"
0x6ea6f  call     string [mscorlib]System.String::Concat(string, string)
0x6ea74  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6ea79  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6ea7e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x6ea83  stloc.0
0x6ea84  ldarg.2
0x6ea85  ldstr    aSrc// "src"
0x6ea8a  ldloc.0
0x6ea8b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x6ea90  callvirt instance string [mscorlib]System.Object::ToString()
0x6ea95  ldc.i4.0
0x6ea96  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6ea9b  ldarg.2
0x6ea9c  ldstr    aClass_0// "class"
0x6eaa1  ldloc.0
0x6eaa2  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x6eaa7  ldc.i4.0
0x6eaa8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6eaad  ldstr    aAlt// "alt"
0x6eab2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6eab7  ldstr    aWebOpenViewAlt// "Web.Open_View_Alt_Text"
0x6eabc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6eac1  ldarg.2
0x6eac2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x6eac7  ldstr    aTitle// "title"
0x6eacc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6ead1  ldstr    aWebOpenViewAlt// "Web.Open_View_Alt_Text"
0x6ead6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6eadb  ldarg.2
0x6eadc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x6eae1  ldarg.2
0x6eae2  ldstr    aImgbase// "imgBase"
0x6eae7  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x6eaec  ldc.i4.1
0x6eaed  newarr   [mscorlib]System.Char
0x6eaf2  dup
0x6eaf3  ldc.i4.0
0x6eaf4  ldc.i4.s 0x2F
0x6eaf6  stelem.i2
0x6eaf7  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x6eafc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6eb01  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6eb06  brtrue.s loc_6EB0F
0x6eb08  ldstr    aImgsOpenviewPn// "/_imgs/openview.png"
0x6eb0d  br.s     loc_6EB14
0x6eb0f  ldstr    aImgsOpenviewVi// "/_imgs/openview_visualrefresh.png"
0x6eb14  call     string [mscorlib]System.String::Concat(string, string)
0x6eb19  ldc.i4.0
0x6eb1a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x6eb1f  ldarg.2
0x6eb20  ldstr    asc_1234C6// " />"
0x6eb25  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6eb2a  ldarg.2
0x6eb2b  ldstr    aA_0// "a"
0x6eb30  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6eb35  ldarg.2
0x6eb36  ldstr    aSpan_1// "span"
0x6eb3b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x6eb40  ret
```
