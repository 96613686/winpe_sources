# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddOpenAssociatedGridViewImageButton

- ea: `0xd700`
- end: `0xd9d0`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddOpenAssociatedGridViewImageButton`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xd480`

## callees

- `0xd700`
- `0x17a10`
- `0x1c7f0`
- `0x1ce20`

## string_xrefs

- `0xd7e8`: `OpenAssociatedGridViewImageButtonTooltip`
- `0xd7b1`: `/_imgs/grid/openassociatedgridview_16_new.png`
- `0xd716`: `openAssociatedGridViewImageButton`
- `0xd74e`: `_openAssociatedGridViewImageButton`
- `0xd871`: `ms-crm-openAssociatedGridView-button-icon`
- `0xd8ee`: `ms-crm-openAssociatedGridView-button-icon`
- `0xd8a5`: `_openAssociatedGridViewImageButtonImage`

## pseudocode

```c

```

## disassembly

```asm
0xd700  ldstr    aDiv// "div"
0xd705  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xd70a  stloc.0
0xd70b  ldloc.0
0xd70c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd711  ldstr    aClass// "class"
0xd716  ldstr    aOpenassociated_1// "openAssociatedGridViewImageButton"
0xd71b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd720  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd725  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd72a  brfalse.s loc_D741
0xd72c  ldloc.0
0xd72d  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xd732  ldstr    aPaddingTop// "padding-top"
0xd737  ldstr    a10px// "10px"
0xd73c  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0xd741  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0xd746  stloc.1
0xd747  ldloc.1
0xd748  ldarg.0
0xd749  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xd74e  ldstr    aOpenassociated_2// "_openAssociatedGridViewImageButton"
0xd753  call     string [mscorlib]System.String::Concat(string, string)
0xd758  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xd75d  ldloc.1
0xd75e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd763  ldstr    aHref// "href"
0xd768  ldstr    aJavascript// "javascript:;"
0xd76d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd772  ldloc.1
0xd773  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd778  ldstr    aOnclick// "onclick"
0xd77d  ldstr    aReturnFalse// "return false;"
0xd782  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd787  ldloc.1
0xd788  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd78d  ldstr    aStyle// "style"
0xd792  ldstr    aDisplayNoneCur// "display:none; cursor: pointer"
0xd797  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd79c  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xd7a1  ldc.i4.1
0xd7a2  newarr   [mscorlib]System.Char
0xd7a7  dup
0xd7a8  ldc.i4.0
0xd7a9  ldc.i4.s 0x2F
0xd7ab  stelem.i2
0xd7ac  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xd7b1  ldstr    aImgsGridOpenas// "/_imgs/grid/openassociatedgridview_16_n"...
0xd7b6  call     string [mscorlib]System.String::Concat(string, string)
0xd7bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd7c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd7c5  stloc.2
0xd7c6  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0xd7cb  ldloc.2
0xd7cc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xd7d1  stloc.3
0xd7d2  ldloc.1
0xd7d3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd7d8  ldstr    aClass// "class"
0xd7dd  ldloc.3
0xd7de  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0xd7e3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd7e8  ldstr    aOpenassociated_0// "OpenAssociatedGridViewImageButtonToolti"...
0xd7ed  stloc.s  4
0xd7ef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd7f4  ldloc.s  4
0xd7f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd7fb  ldc.i4.1
0xd7fc  newarr   [mscorlib]System.Object
0xd801  dup
0xd802  ldc.i4.0
0xd803  ldarg.0
0xd804  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0xd809  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0xd80e  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_EntityDisplayName()
0xd813  stelem.ref
0xd814  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0xd819  stloc.s  5
0xd81b  ldloc.1
0xd81c  ldloc.s  5
0xd81e  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_Title(string)
0xd823  ldloc.1
0xd824  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd829  ldstr    aTabindex_0// "tabIndex"
0xd82e  ldarg.0
0xd82f  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0xd834  stloc.s  7
0xd836  ldloca.s 7
0xd838  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd83d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xd842  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd847  ldnull
0xd848  stloc.s  6
0xd84a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd84f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd854  brfalse.s loc_D896
0xd856  ldstr    aSpan// "span"
0xd85b  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xd860  dup
0xd861  stloc.s  6
0xd863  stloc.s  8
0xd865  ldloc.s  6
0xd867  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd86c  ldstr    aClass// "class"
0xd871  ldstr    aMsCrmOpenassoc// "ms-crm-openAssociatedGridView-button-ic"...
0xd876  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd87b  ldloc.1
0xd87c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd881  ldloc.s  6
0xd883  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd888  leave.s  loc_D896
0xd88a  ldloc.s  8
0xd88c  brfalse.s loc_D895
0xd88e  ldloc.s  8
0xd890  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd895  endfinally
0xd896  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0xd89b  stloc.s  9
0xd89d  ldloc.s  9
0xd89f  ldarg.0
0xd8a0  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xd8a5  ldstr    aOpenassociated_3// "_openAssociatedGridViewImageButtonImage"
0xd8aa  call     string [mscorlib]System.String::Concat(string, string)
0xd8af  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xd8b4  ldloc.s  9
0xd8b6  ldloc.s  5
0xd8b8  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0xd8bd  ldloc.s  9
0xd8bf  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd8c4  ldstr    aTitle// "title"
0xd8c9  ldloc.s  5
0xd8cb  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd8d0  ldloc.s  9
0xd8d2  ldloc.3
0xd8d3  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0xd8d8  callvirt instance string [mscorlib]System.Object::ToString()
0xd8dd  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0xd8e2  ldloc.s  9
0xd8e4  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd8e9  ldstr    aClass// "class"
0xd8ee  ldstr    aMsCrmOpenassoc// "ms-crm-openAssociatedGridView-button-ic"...
0xd8f3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd8f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd8fd  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd902  brfalse.s loc_D918
0xd904  ldloc.s  6
0xd906  brfalse.s loc_D918
0xd908  ldloc.s  6
0xd90a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd90f  ldloc.s  9
0xd911  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd916  leave.s  loc_D933
0xd918  ldloc.1
0xd919  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd91e  ldloc.s  9
0xd920  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd925  leave.s  loc_D933
0xd927  ldloc.s  9
0xd929  brfalse.s loc_D932
0xd92b  ldloc.s  9
0xd92d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd932  endfinally
0xd933  ldarg.1
0xd934  brfalse.s loc_D956
0xd936  ldarg.1
0xd937  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0xd93c  brtrue.s loc_D956
0xd93e  ldloc.1
0xd93f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd944  ldstr    aAssocview// "assocView"
0xd949  ldarg.1
0xd94a  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem::get_Action()
0xd94f  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd954  br.s     loc_D96B
0xd956  ldloc.1
0xd957  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd95c  ldstr    aNonrelationshi// "nonRelationShipGrid"
0xd961  ldstr    aTrue// "true"
0xd966  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd96b  ldloc.1
0xd96c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd971  ldstr    aAction// "action"
0xd976  ldstr    asc_30804// ""
0xd97b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd980  ldloc.1
0xd981  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd986  ldstr    aTarget// "target"
0xd98b  ldstr    aSelf// "_self"
0xd990  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd995  ldloc.0
0xd996  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd99b  ldloc.1
0xd99c  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd9a1  leave.s  loc_D9AD
0xd9a3  ldloc.1
0xd9a4  brfalse.s loc_D9AC
0xd9a6  ldloc.1
0xd9a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd9ac  endfinally
0xd9ad  ldarg.0
0xd9ae  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_QueryFilter()
0xd9b3  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter::get_ContextualActionsContainerProvider()
0xd9b8  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd9bd  ldloc.0
0xd9be  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd9c3  leave.s  loc_D9CF
0xd9c5  ldloc.0
0xd9c6  brfalse.s loc_D9CE
0xd9c8  ldloc.0
0xd9c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd9ce  endfinally
0xd9cf  ret
```
