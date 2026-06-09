# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddTitleAndActions

- ea: `0xbee0`
- end: `0xc17f`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddTitleAndActions`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0xbd60`

## callees

- `0xbee0`
- `0xc200`
- `0xc210`
- `0xc280`
- `0xc300`
- `0xc510`
- `0xc590`
- `0xc620`
- `0xc7d0`
- `0xd9d0`
- `0xdba0`
- `0xdc60`
- `0xe480`
- `0x17930`
- `0x179b0`
- `0x1c790`
- `0x1cd70`
- `0x1ce20`

## pseudocode

```c

```

## disassembly

```asm
0xbee0  ldarg.1
0xbee1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbee6  brfalse.s loc_BEF3
0xbee8  ldarg.0
0xbee9  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableContextualActions()
0xbeee  brfalse  loc_C17E
0xbef3  ldnull
0xbef4  stloc.0
0xbef5  ldstr    aDiv// "div"
0xbefa  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xbeff  dup
0xbf00  stloc.0
0xbf01  stloc.1
0xbf02  ldloc.0
0xbf03  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xbf08  ldstr    aClass// "class"
0xbf0d  ldstr    aMsCrmGridTitle_0// "ms-crm-Grid-Title"
0xbf12  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xbf17  ldloc.0
0xbf18  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xbf1d  ldstr    aId// "id"
0xbf22  ldarg.0
0xbf23  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xbf28  ldstr    aTitlewitherror// "_titleWithErrors"
0xbf2d  call     string [mscorlib]System.String::Concat(string, string)
0xbf32  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xbf37  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xbf3c  ldloc.0
0xbf3d  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbf42  ldarg.2
0xbf43  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbf48  ldarg.0
0xbf49  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_IsEntityBound()
0xbf4e  brfalse  loc_C02F
0xbf53  ldarg.0
0xbf54  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableContextualActions()
0xbf59  brfalse  loc_C02F
0xbf5e  ldloc.0
0xbf5f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbf64  ldarg.0
0xbf65  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddQuickAddHiddenContainerToTitleContainer()
0xbf6a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbf6f  ldarg.0
0xbf70  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::UserHasAddPrivileges()
0xbf75  brfalse.s loc_BFAA
0xbf77  ldloc.0
0xbf78  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbf7d  ldarg.0
0xbf7e  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddErrorMessageToTitleContainer_1()
0xbf83  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbf88  ldloc.0
0xbf89  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbf8e  ldarg.0
0xbf8f  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddErrorMessageToTitleContainer_2()
0xbf94  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbf99  ldloc.0
0xbf9a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbf9f  ldarg.0
0xbfa0  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddQuickAddHiddenPrivilegeDivToTitleContainer()
0xbfa5  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbfaa  ldarg.0
0xbfab  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xbfb0  brtrue.s loc_BFCB
0xbfb2  ldarg.0
0xbfb3  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::UserHasEditPrivileges()
0xbfb8  brfalse.s loc_BFCB
0xbfba  ldloc.0
0xbfbb  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbfc0  ldarg.0
0xbfc1  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddEditHiddenDivToTitleContainer()
0xbfc6  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbfcb  ldarg.0
0xbfcc  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xbfd1  brtrue.s loc_BFEC
0xbfd3  ldarg.0
0xbfd4  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::UserHasPriceOverridePrivileges()
0xbfd9  brfalse.s loc_BFEC
0xbfdb  ldloc.0
0xbfdc  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbfe1  ldarg.0
0xbfe2  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddOverridePricePrivilegeDivToTitleContainer()
0xbfe7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbfec  ldloc.0
0xbfed  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbff2  ldarg.0
0xbff3  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddInlineLookupDivToTitleContainer()
0xbff8  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbffd  ldarg.0
0xbffe  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0xc003  brfalse.s loc_C02F
0xc005  ldarg.0
0xc006  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0xc00b  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0xc010  brtrue.s loc_C02F
0xc012  ldarg.0
0xc013  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xc018  brtrue.s loc_C02F
0xc01a  ldarg.2
0xc01b  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xc020  ldstr    aDisplay// "display"
0xc025  ldstr    aNone// "none"
0xc02a  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0xc02f  ldarg.3
0xc030  ldstr    aTitlecontainer// "titleContainer_"
0xc035  ldarg.0
0xc036  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xc03b  call     string [mscorlib]System.String::Concat(string, string)
0xc040  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xc045  ldarg.3
0xc046  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xc04b  ldloc.0
0xc04c  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xc051  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc056  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc05b  brfalse.s loc_C0B4
0xc05d  ldarg.3
0xc05e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc063  ldstr    aClass// "class"
0xc068  ldstr    aMsCrmGridTitle_1// "ms-crm-grid-titlecontainer  ms-crm-Grid"...
0xc06d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc072  ldarg.0
0xc073  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0xc078  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_IsGridEnabled()
0xc07d  brfalse.s loc_C09D
0xc07f  ldarg.0
0xc080  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_HeaderColorCode()
0xc085  brfalse.s loc_C09D
0xc087  ldarg.3
0xc088  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xc08d  ldstr    aBackgroundColo// "background-color"
0xc092  ldarg.0
0xc093  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_HeaderColorCode()
0xc098  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0xc09d  ldarg.3
0xc09e  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xc0a3  ldstr    aHeight// "height"
0xc0a8  ldstr    a40px// "40px"
0xc0ad  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0xc0b2  br.s     loc_C0DE
0xc0b4  ldarg.3
0xc0b5  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc0ba  ldstr    aClass// "class"
0xc0bf  ldstr    aMsCrmGridTitle_2// "ms-crm-grid-titlecontainer"
0xc0c4  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc0c9  ldarg.3
0xc0ca  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xc0cf  ldstr    aHeight// "height"
0xc0d4  ldstr    a25px// "25px"
0xc0d9  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0xc0de  ldarg.0
0xc0df  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableContextualActions()
0xc0e4  brfalse  loc_C172
0xc0e9  ldnull
0xc0ea  stloc.2
0xc0eb  ldstr    aDiv// "div"
0xc0f0  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xc0f5  dup
0xc0f6  stloc.2
0xc0f7  stloc.3
0xc0f8  ldloc.2
0xc0f9  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc0fe  ldstr    aClass// "class"
0xc103  ldstr    aMsCrmGridConte// "ms-crm-Grid-ContextualButtonsContainer"
0xc108  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc10d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc112  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc117  brfalse.s loc_C12E
0xc119  ldloc.2
0xc11a  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xc11f  ldstr    aPaddingTop// "padding-top"
0xc124  ldstr    a10px// "10px"
0xc129  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0xc12e  ldloc.2
0xc12f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc134  ldstr    aId// "id"
0xc139  ldarg.0
0xc13a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xc13f  ldstr    aContextualbutt// "_contextualButtonsContainer"
0xc144  call     string [mscorlib]System.String::Concat(string, string)
0xc149  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xc14e  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc153  leave.s  loc_C15F
0xc155  ldloc.3
0xc156  brfalse.s loc_C15E
0xc158  ldloc.3
0xc159  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc15e  endfinally
0xc15f  ldarg.3
0xc160  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xc165  ldloc.2
0xc166  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xc16b  ldarg.0
0xc16c  ldloc.2
0xc16d  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::HandleContextualActions(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl titleContainer)
0xc172  leave.s  loc_C17E
0xc174  ldloc.1
0xc175  brfalse.s loc_C17D
0xc177  ldloc.1
0xc178  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc17d  endfinally
0xc17e  ret
```
