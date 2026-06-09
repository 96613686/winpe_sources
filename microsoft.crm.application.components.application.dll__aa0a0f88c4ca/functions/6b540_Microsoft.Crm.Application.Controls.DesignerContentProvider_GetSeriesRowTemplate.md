# Microsoft.Crm.Application.Controls.DesignerContentProvider::GetSeriesRowTemplate

- ea: `0x6b540`
- end: `0x6ba80`
- name: `Microsoft.Crm.Application.Controls.DesignerContentProvider::GetSeriesRowTemplate`
- size: `1344`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6bcb0`

## callees

- `0x6b220`
- `0x6b540`
- `0x6cfd0`

## string_xrefs

- `0x6b77c`: `tabIndex="-1" id="chartTypeImageLink_0">`
- `0x6b8e0`: `tabIndex="-1" id="topBottomImageLink_0">`
- `0x6b931`: `/_imgs/visualization/designer/deletechart.png`
- `0x6b979`: `removeSeriesBtn_0`
- `0x6b9b9`: `Web.Visualization.Designer.DeleteSeriesButton`
- `0x6ba2d`: `<span class="ms-crm-removeSeriesBtnSpan" onmouseover="Mscrm.VisualizationPane.hoverButton(new Sys.UI.DomEvent(event),true)" onmouseout="Mscrm.VisualizationPane.hoverButton(new Sys.UI.DomEvent(event),false)" onfocusin="Mscrm.VisualizationPane.hoverButton(new Sys.UI.DomEvent(event),true)" onfocusout="Mscrm.VisualizationPane.hoverButton(new Sys.UI.DomEvent(event),false)">`
- `0x6ba3f`: `id="removeSeriesBtnLink_0">`

## pseudocode

```c

```

## disassembly

```asm
0x6b540  ldnull
0x6b541  stloc.0
0x6b542  ldnull
0x6b543  stloc.1
0x6b544  ldarg.0
0x6b545  ldloca.s 0
0x6b547  ldloca.s 1
0x6b549  ldarg.2
0x6b54a  ldarg.3
0x6b54b  ldarg.s  4
0x6b54d  ldarg.s  5
0x6b54f  call     instance void Microsoft.Crm.Application.Controls.DesignerContentProvider::AddYSelector([out] class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select& yAttrSelect, [out] class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select& yAggrSelect, string paneId, string seriesSelectorToolTip, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup viewAtrributes, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup entityAttributes)
0x6b554  ldarg.1
0x6b555  ldstr    aDivClassMsCrmV_0// "<div class=\"ms-crm-VisualizationPaneDe"...
0x6b55a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b55f  ldarg.1
0x6b560  ldstr    aNobr// "<nobr>"
0x6b565  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b56a  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::.ctor()
0x6b56f  stloc.2
0x6b570  ldloc.2
0x6b571  ldc.i4.0
0x6b572  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0x6b577  ldarg.1
0x6b578  ldloc.2
0x6b579  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::get_ClientSideFormInputBehaviorClassName()
0x6b57e  ldloc.2
0x6b57f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x6b584  call     void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.SharedMethods::RenderClientControlRegistrationScript(class [mscorlib]System.IO.TextWriter, string, string)
0x6b589  ldloc.2
0x6b58a  ldarg.0
0x6b58b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_ResourceManager()
0x6b590  ldstr    aWebVisualizati_42// "Web.Visualization.Designer.SeriesCheckb"...
0x6b595  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6b59a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::set_Title(string)
0x6b59f  ldarg.0
0x6b5a0  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isEditMode
0x6b5a5  brfalse.s loc_6B5B3
0x6b5a7  ldloc.2
0x6b5a8  ldarg.0
0x6b5a9  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isComplexChart
0x6b5ae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x6b5b3  ldloc.2
0x6b5b4  ldstr    aYrowcheckbox0// "yRowCheckBox_0"
0x6b5b9  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x6b5be  ldarg.1
0x6b5bf  ldstr    aSpan_0// "<span>"
0x6b5c4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b5c9  ldloc.2
0x6b5ca  ldarg.1
0x6b5cb  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x6b5d0  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x6b5d5  ldarg.1
0x6b5d6  ldstr    aSpan// "</span>"
0x6b5db  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b5e0  leave.s  loc_6B5EC
0x6b5e2  ldloc.2
0x6b5e3  brfalse.s loc_6B5EB
0x6b5e5  ldloc.2
0x6b5e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b5eb  endfinally
0x6b5ec  ldarg.1
0x6b5ed  ldstr    aSpan_0// "<span>"
0x6b5f2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b5f7  ldloc.0
0x6b5f8  ldarg.1
0x6b5f9  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x6b5fe  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x6b603  ldarg.1
0x6b604  ldstr    aSpan// "</span>"
0x6b609  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b60e  ldarg.1
0x6b60f  ldstr    aSpan_0// "<span>"
0x6b614  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b619  ldloc.1
0x6b61a  ldarg.1
0x6b61b  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x6b620  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x6b625  ldarg.1
0x6b626  ldstr    aSpan// "</span>"
0x6b62b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b630  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x6b635  stloc.3
0x6b636  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x6b63b  ldc.i4.1
0x6b63c  newarr   [mscorlib]System.Char
0x6b641  dup
0x6b642  ldc.i4.0
0x6b643  ldc.i4.s 0x2F
0x6b645  stelem.i2
0x6b646  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x6b64b  ldstr    aImgsVisualizat_8// "/_imgs/visualization/designer/columncha"...
0x6b650  call     string [mscorlib]System.String::Concat(string, string)
0x6b655  stloc.s  4
0x6b657  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x6b65c  ldloc.s  4
0x6b65e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6b663  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6b668  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x6b66d  stloc.s  5
0x6b66f  ldloc.3
0x6b670  ldloc.s  5
0x6b672  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x6b677  callvirt instance string [mscorlib]System.Object::ToString()
0x6b67c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x6b681  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x6b686  ldloc.3
0x6b687  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b68c  ldstr    aId_1// "id"
0x6b691  ldstr    aCharttypeimage// "chartTypeImage_0"
0x6b696  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b69b  ldloc.3
0x6b69c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b6a1  ldstr    aClass_0// "class"
0x6b6a6  ldloc.s  5
0x6b6a8  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x6b6ad  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x6b6b2  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b6b7  ldloc.3
0x6b6b8  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b6bd  ldstr    aImgbase// "imgBase"
0x6b6c2  ldloc.s  4
0x6b6c4  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b6c9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6b6ce  ldarg.0
0x6b6cf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_ResourceManager()
0x6b6d4  ldstr    aWebVisualizati_43// "Web.Visualization.Designer.ChartIcon.To"...
0x6b6d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6b6de  ldc.i4.1
0x6b6df  newarr   [mscorlib]System.Object
0x6b6e4  dup
0x6b6e5  ldc.i4.0
0x6b6e6  ldarg.0
0x6b6e7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_ResourceManager()
0x6b6ec  ldstr    aRibbonVisualiz// "Ribbon.VisualizationTab.Charts.Column"
0x6b6f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6b6f6  stelem.ref
0x6b6f7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6b6fc  stloc.s  6
0x6b6fe  ldloc.3
0x6b6ff  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b704  ldstr    aAlt// "alt"
0x6b709  ldloc.s  6
0x6b70b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b710  ldloc.3
0x6b711  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b716  ldstr    aTitle// "title"
0x6b71b  ldloc.s  6
0x6b71d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b722  ldloc.3
0x6b723  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b728  ldstr    aStyle_0// "style"
0x6b72d  ldstr    aVerticalAlignB_1// "vertical-align:bottom"
0x6b732  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b737  ldarg.0
0x6b738  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isEditMode
0x6b73d  brfalse.s loc_6B74B
0x6b73f  ldloc.3
0x6b740  ldarg.0
0x6b741  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isComplexChart
0x6b746  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0x6b74b  ldarg.0
0x6b74c  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isEditMode
0x6b751  brfalse.s loc_6B75B
0x6b753  ldarg.0
0x6b754  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isComplexChart
0x6b759  brtrue.s loc_6B762
0x6b75b  ldsfld   string [mscorlib]System.String::Empty
0x6b760  br.s     loc_6B767
0x6b762  ldstr    aDisabled_0// " disabled "
0x6b767  stloc.s  7
0x6b769  ldarg.1
0x6b76a  ldstr    aSpanOnmouseove// "<span onmouseover=\"Mscrm.Visualization"...
0x6b76f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b774  ldarg.1
0x6b775  ldstr    aAHrefJavascrip// "<a href=\"javascript:;\""
0x6b77a  ldloc.s  7
0x6b77c  ldstr    aTabindex1IdCha// "tabIndex=\"-1\" id=\"chartTypeImageLink"...
0x6b781  call     string [mscorlib]System.String::Concat(string, string, string)
0x6b786  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b78b  ldloc.3
0x6b78c  ldarg.1
0x6b78d  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x6b792  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x6b797  ldarg.1
0x6b798  ldstr    aASpan// "</a></span>"
0x6b79d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b7a2  leave.s  loc_6B7AE
0x6b7a4  ldloc.3
0x6b7a5  brfalse.s loc_6B7AD
0x6b7a7  ldloc.3
0x6b7a8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b7ad  endfinally
0x6b7ae  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x6b7b3  stloc.s  8
0x6b7b5  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x6b7ba  ldc.i4.1
0x6b7bb  newarr   [mscorlib]System.Char
0x6b7c0  dup
0x6b7c1  ldc.i4.0
0x6b7c2  ldc.i4.s 0x2F
0x6b7c4  stelem.i2
0x6b7c5  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x6b7ca  ldstr    aImgsVisualizat_12// "/_imgs/visualization/designer/topbottom"...
0x6b7cf  call     string [mscorlib]System.String::Concat(string, string)
0x6b7d4  stloc.s  9
0x6b7d6  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x6b7db  ldloc.s  9
0x6b7dd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6b7e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6b7e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x6b7ec  stloc.s  0xA
0x6b7ee  ldloc.s  8
0x6b7f0  ldloc.s  0xA
0x6b7f2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x6b7f7  callvirt instance string [mscorlib]System.Object::ToString()
0x6b7fc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x6b801  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x6b806  ldloc.s  8
0x6b808  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b80d  ldstr    aId_1// "id"
0x6b812  ldstr    aTopbottomimage// "topBottomImage_0"
0x6b817  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b81c  ldloc.s  8
0x6b81e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b823  ldstr    aClass_0// "class"
0x6b828  ldloc.s  0xA
0x6b82a  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x6b82f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x6b834  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b839  ldloc.s  8
0x6b83b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b840  ldstr    aImgbase// "imgBase"
0x6b845  ldloc.s  9
0x6b847  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b84c  ldarg.0
0x6b84d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_ResourceManager()
0x6b852  ldstr    aRibbonVisualiz_0// "Ribbon.VisualizationTab.TopBottom.Title"
0x6b857  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6b85c  stloc.s  0xB
0x6b85e  ldloc.s  8
0x6b860  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b865  ldstr    aAlt// "alt"
0x6b86a  ldloc.s  0xB
0x6b86c  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b871  ldloc.s  8
0x6b873  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b878  ldstr    aTitle// "title"
0x6b87d  ldloc.s  0xB
0x6b87f  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b884  ldloc.s  8
0x6b886  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x6b88b  ldstr    aStyle_0// "style"
0x6b890  ldstr    aVerticalAlignB_1// "vertical-align:bottom"
0x6b895  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6b89a  ldarg.0
0x6b89b  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isEditMode
0x6b8a0  brfalse.s loc_6B8AA
0x6b8a2  ldarg.0
0x6b8a3  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isComplexChart
0x6b8a8  brtrue.s loc_6B8B1
0x6b8aa  ldsfld   string [mscorlib]System.String::Empty
0x6b8af  br.s     loc_6B8B6
0x6b8b1  ldstr    aDisabled_0// " disabled "
0x6b8b6  stloc.s  0xC
0x6b8b8  ldarg.0
0x6b8b9  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isEditMode
0x6b8be  brfalse.s loc_6B8CD
0x6b8c0  ldloc.s  8
0x6b8c2  ldarg.0
0x6b8c3  ldfld    bool Microsoft.Crm.Application.Controls.DesignerContentProvider::isComplexChart
0x6b8c8  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0x6b8cd  ldarg.1
0x6b8ce  ldstr    aSpanOnmouseove// "<span onmouseover=\"Mscrm.Visualization"...
0x6b8d3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b8d8  ldarg.1
0x6b8d9  ldstr    aAHrefJavascrip// "<a href=\"javascript:;\""
0x6b8de  ldloc.s  0xC
0x6b8e0  ldstr    aTabindex1IdTop// "tabIndex=\"-1\" id=\"topBottomImageLink"...
0x6b8e5  call     string [mscorlib]System.String::Concat(string, string, string)
0x6b8ea  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b8ef  ldloc.s  8
0x6b8f1  ldarg.1
0x6b8f2  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x6b8f7  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x6b8fc  ldarg.1
0x6b8fd  ldstr    aASpan// "</a></span>"
0x6b902  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6b907  leave.s  loc_6B915
0x6b909  ldloc.s  8
0x6b90b  brfalse.s loc_6B914
0x6b90d  ldloc.s  8
0x6b90f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b914  endfinally
0x6b915  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x6b91a  stloc.s  0xD
0x6b91c  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x6b921  ldc.i4.1
0x6b922  newarr   [mscorlib]System.Char
0x6b927  dup
  ... truncated ...
```
