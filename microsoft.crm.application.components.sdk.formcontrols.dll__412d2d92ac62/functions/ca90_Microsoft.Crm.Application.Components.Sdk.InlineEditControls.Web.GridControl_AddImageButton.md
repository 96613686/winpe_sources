# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddImageButton

- ea: `0xca90`
- end: `0xccf1`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddImageButton`
- size: `609`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xc7d0`

## callees

- `0xca90`
- `0x17a10`
- `0x1cb30`
- `0x1ce20`
- `0x1e700`
- `0x1e740`

## pseudocode

```c

```

## disassembly

```asm
0xca90  ldstr    aDiv// "div"
0xca95  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xca9a  stloc.0
0xca9b  ldloc.0
0xca9c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xcaa1  ldstr    aClass// "class"
0xcaa6  ldstr    aMsCrmContextbu// "ms-crm-contextButton"
0xcaab  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xcab0  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0xcab5  stloc.1
0xcab6  ldloc.1
0xcab7  ldarg.0
0xcab8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xcabd  ldstr    aAddimagebutton// "_addImageButton"
0xcac2  call     string [mscorlib]System.String::Concat(string, string)
0xcac7  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xcacc  ldloc.1
0xcacd  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xcad2  ldstr    aHref// "href"
0xcad7  ldstr    aJavascript// "javascript:;"
0xcadc  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xcae1  ldloc.1
0xcae2  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xcae7  ldstr    aOnclick// "onclick"
0xcaec  ldstr    aReturnFalse// "return false;"
0xcaf1  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xcaf6  ldloc.1
0xcaf7  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xcafc  ldstr    aStyle// "style"
0xcb01  ldstr    aDisplayNoneCur// "display:none; cursor: pointer"
0xcb06  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xcb0b  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xcb10  ldc.i4.1
0xcb11  newarr   [mscorlib]System.Char
0xcb16  dup
0xcb17  ldc.i4.0
0xcb18  ldc.i4.s 0x2F
0xcb1a  stelem.i2
0xcb1b  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xcb20  ldstr    aImgsGridAdd16N// "/_imgs/grid/add_16_new.png"
0xcb25  call     string [mscorlib]System.String::Concat(string, string)
0xcb2a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcb2f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcb34  stloc.2
0xcb35  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0xcb3a  ldloc.2
0xcb3b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xcb40  stloc.3
0xcb41  ldloc.1
0xcb42  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xcb47  ldstr    aClass// "class"
0xcb4c  ldloc.3
0xcb4d  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0xcb52  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xcb57  ldarg.0
0xcb58  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsSalesTeamGrid()
0xcb5d  brtrue.s loc_CB75
0xcb5f  ldarg.0
0xcb60  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsRecordCreationAndUpdateRuleSetGrid()
0xcb65  brtrue.s loc_CB6E
0xcb67  ldstr    aGridaddcontext// "GridAddContextualButtonTooltip"
0xcb6c  br.s     loc_CB7A
0xcb6e  ldstr    aConvertruleadd// "ConvertRuleAddExistingStandardToolTip"
0xcb73  br.s     loc_CB7A
0xcb75  ldstr    aSalesteamgrida// "SalesTeamGridAddContextualButtonTooltip"
0xcb7a  stloc.s  4
0xcb7c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb81  ldloc.s  4
0xcb83  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcb88  ldc.i4.1
0xcb89  newarr   [mscorlib]System.Object
0xcb8e  dup
0xcb8f  ldc.i4.0
0xcb90  ldarg.0
0xcb91  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0xcb96  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0xcb9b  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_EntityDisplayName()
0xcba0  stelem.ref
0xcba1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0xcba6  stloc.s  5
0xcba8  ldloc.1
0xcba9  ldloc.s  5
0xcbab  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_Title(string)
0xcbb0  ldloc.1
0xcbb1  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xcbb6  ldstr    aTabindex_0// "tabIndex"
0xcbbb  ldarg.0
0xcbbc  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0xcbc1  stloc.s  6
0xcbc3  ldloca.s 6
0xcbc5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcbca  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xcbcf  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xcbd4  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0xcbd9  stloc.s  7
0xcbdb  ldloc.s  7
0xcbdd  ldarg.0
0xcbde  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xcbe3  ldstr    aAddimagebutton_0// "_addImageButtonImage"
0xcbe8  call     string [mscorlib]System.String::Concat(string, string)
0xcbed  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xcbf2  ldloc.s  7
0xcbf4  ldloc.s  5
0xcbf6  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0xcbfb  ldloc.s  7
0xcbfd  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xcc02  ldstr    aTitle// "title"
0xcc07  ldloc.s  5
0xcc09  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xcc0e  ldloc.s  7
0xcc10  ldloc.3
0xcc11  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0xcc16  callvirt instance string [mscorlib]System.Object::ToString()
0xcc1b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0xcc20  ldloc.s  7
0xcc22  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xcc27  ldstr    aClass// "class"
0xcc2c  ldstr    aMsCrmAddButton// "ms-crm-add-button-icon"
0xcc31  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xcc36  ldloc.1
0xcc37  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xcc3c  ldloc.s  7
0xcc3e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xcc43  ldarg.0
0xcc44  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xcc49  ldstr    aActivitypointe_1// "activitypointer"
0xcc4e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcc53  brfalse.s loc_CCA1
0xcc55  ldarg.0
0xcc56  ldstr    asc_30804// ""
0xcc5b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcc60  ldstr    aOverflowmenuTo// "OverflowMenu_Tooltip"
0xcc65  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcc6a  ldarg.0
0xcc6b  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xcc70  ldstr    aMoreactivities// "moreActivitiesButton"
0xcc75  call     string [mscorlib]System.String::Concat(string, string)
0xcc7a  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SubGridNewActivityPopup::.ctor(string, string, string)
0xcc7f  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SubGridNewActivityPopup Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::_moreActivitiesButton
0xcc84  ldarg.0
0xcc85  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SubGridNewActivityPopup Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::_moreActivitiesButton
0xcc8a  ldc.i4.m1
0xcc8b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::set_TabIndex(int32)
0xcc90  ldloc.1
0xcc91  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xcc96  ldarg.0
0xcc97  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SubGridNewActivityPopup Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::_moreActivitiesButton
0xcc9c  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xcca1  leave.s  loc_CCAF
0xcca3  ldloc.s  7
0xcca5  brfalse.s loc_CCAE
0xcca7  ldloc.s  7
0xcca9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xccae  endfinally
0xccaf  ldloc.1
0xccb0  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xccb5  ldstr    aAction// "action"
0xccba  ldarg.2
0xccbb  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xccc0  ldloc.0
0xccc1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xccc6  ldloc.1
0xccc7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xcccc  leave.s  loc_CCD8
0xccce  ldloc.1
0xcccf  brfalse.s loc_CCD7
0xccd1  ldloc.1
0xccd2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xccd7  endfinally
0xccd8  ldarg.1
0xccd9  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xccde  ldloc.0
0xccdf  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xcce4  leave.s  loc_CCF0
0xcce6  ldloc.0
0xcce7  brfalse.s loc_CCEF
0xcce9  ldloc.0
0xccea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xccef  endfinally
0xccf0  ret
```
