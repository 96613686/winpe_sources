# Microsoft.Crm.Application.Controls.DesignerContentProvider::GetCategoryRowTemplate

- ea: `0x6bad0`
- end: `0x6bcae`
- name: `Microsoft.Crm.Application.Controls.DesignerContentProvider::GetCategoryRowTemplate`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x6bcb0`

## callees

- `0x6b380`
- `0x6bad0`
- `0x6cfd0`

## string_xrefs

- `0x6bb82`: `/_imgs/visualization/designer/deletechart.png`
- `0x6bbc8`: `removeXBtn_0`
- `0x6bc11`: `Web.Visualization.Designer.DeleteCategoryButton`
- `0x6bc31`: `Web.Visualization.Designer.DeleteCategoryButton`
- `0x6bc75`: `<a href="javascript:;" id="removeXBtnLink_0">`

## pseudocode

```c

```

## disassembly

```asm
0x6bad0  ldnull
0x6bad1  stloc.0
0x6bad2  ldnull
0x6bad3  stloc.1
0x6bad4  ldarg.0
0x6bad5  ldloca.s 0
0x6bad7  ldloca.s 1
0x6bad9  ldarg.2
0x6bada  ldarg.3
0x6badb  ldarg.s  4
0x6badd  ldarg.s  5
0x6badf  call     instance void Microsoft.Crm.Application.Controls.DesignerContentProvider::AddXSelector([out] class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select& xAttrSelect, [out] class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select& xDateSelect, string paneId, string categorySelectorToolTip, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup viewAtrributes, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup entityAttributes)
0x6bae4  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x6bae9  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x6baee  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x6baf3  brtrue.s loc_6BAFC
0x6baf5  ldstr    aMarginLeft_0// "margin-left"
0x6bafa  br.s     loc_6BB01
0x6bafc  ldstr    aMarginRight_0// "margin-right"
0x6bb01  stloc.2
0x6bb02  ldarg.1
0x6bb03  ldstr    aDivIdTdxattrib// "<div id=\"tdxAttributeSelector\" class="...
0x6bb08  ldloc.2
0x6bb09  ldstr    a20pxNobr// ": 20px;\"><nobr>"
0x6bb0e  call     string [mscorlib]System.String::Concat(string, string, string)
0x6bb13  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6bb18  ldarg.1
0x6bb19  ldstr    aSpan_0// "<span>"
0x6bb1e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6bb23  ldloc.0
0x6bb24  ldarg.1
0x6bb25  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x6bb2a  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x6bb2f  ldarg.1
0x6bb30  ldstr    aSpan// "</span>"
0x6bb35  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6bb3a  ldarg.1
0x6bb3b  ldstr    aSpanStyle// "<span style=\""
0x6bb40  ldloc.2
0x6bb41  ldstr    a3px// ": 3px;\">"
0x6bb46  call     string [mscorlib]System.String::Concat(string, string, string)
0x6bb4b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6bb50  ldloc.1
0x6bb51  ldarg.1
0x6bb52  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x6bb57  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x6bb5c  ldarg.1
0x6bb5d  ldstr    aSpan// "</span>"
0x6bb62  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6bb67  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x6bb6c  stloc.3
0x6bb6d  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x6bb72  ldc.i4.1
0x6bb73  newarr   [mscorlib]System.Char
0x6bb78  dup
0x6bb79  ldc.i4.0
0x6bb7a  ldc.i4.s 0x2F
0x6bb7c  stelem.i2
0x6bb7d  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x6bb82  ldstr    aImgsVisualizat_13// "/_imgs/visualization/designer/deletecha"...
0x6bb87  call     string [mscorlib]System.String::Concat(string, string)
0x6bb8c  stloc.s  4
0x6bb8e  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x6bb93  ldloc.s  4
0x6bb95  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6bb9a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6bb9f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x6bba4  stloc.s  5
0x6bba6  ldloc.3
0x6bba7  ldloc.s  5
0x6bba9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x6bbae  callvirt instance string [mscorlib]System.Object::ToString()
0x6bbb3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x6bbb8  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x6bbbd  ldloc.3
0x6bbbe  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6bbc3  ldstr    aId_1// "id"
0x6bbc8  ldstr    aRemovexbtn0// "removeXBtn_0"
0x6bbcd  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6bbd2  ldloc.3
0x6bbd3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6bbd8  ldstr    aClass_0// "class"
0x6bbdd  ldloc.s  5
0x6bbdf  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x6bbe4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x6bbe9  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6bbee  ldloc.3
0x6bbef  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6bbf4  ldstr    aImgbase// "imgBase"
0x6bbf9  ldloc.s  4
0x6bbfb  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6bc00  ldloc.3
0x6bc01  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6bc06  ldstr    aAlt// "alt"
0x6bc0b  ldarg.0
0x6bc0c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_ResourceManager()
0x6bc11  ldstr    aWebVisualizati_46// "Web.Visualization.Designer.DeleteCatego"...
0x6bc16  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6bc1b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6bc20  ldloc.3
0x6bc21  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6bc26  ldstr    aTitle// "title"
0x6bc2b  ldarg.0
0x6bc2c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_ResourceManager()
0x6bc31  ldstr    aWebVisualizati_46// "Web.Visualization.Designer.DeleteCatego"...
0x6bc36  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6bc3b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6bc40  ldloc.3
0x6bc41  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6bc46  ldstr    aStyle_0// "style"
0x6bc4b  ldstr    aVerticalAlignB_1// "vertical-align:bottom"
0x6bc50  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6bc55  ldarg.0
0x6bc56  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isEditMode
0x6bc5b  brfalse.s loc_6BC69
0x6bc5d  ldloc.3
0x6bc5e  ldarg.0
0x6bc5f  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isComplexChart
0x6bc64  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0x6bc69  ldarg.1
0x6bc6a  ldstr    aSpanOnmouseove_0// "<span onmouseover=\"Mscrm.Visualization"...
0x6bc6f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6bc74  ldarg.1
0x6bc75  ldstr    aAHrefJavascrip_0// "<a href=\"javascript:;\" id=\"removeXBt"...
0x6bc7a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6bc7f  ldloc.3
0x6bc80  ldarg.1
0x6bc81  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x6bc86  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x6bc8b  ldarg.1
0x6bc8c  ldstr    aASpan// "</a></span>"
0x6bc91  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6bc96  leave.s  loc_6BCA2
0x6bc98  ldloc.3
0x6bc99  brfalse.s loc_6BCA1
0x6bc9b  ldloc.3
0x6bc9c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6bca1  endfinally
0x6bca2  ldarg.1
0x6bca3  ldstr    aNobrDiv// "</nobr></div>"
0x6bca8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6bcad  ret
```
