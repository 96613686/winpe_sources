# Microsoft.Crm.Service.Dialogs.CancelCasePage::ConfigureForm

- ea: `0x3280`
- end: `0x3439`
- name: `Microsoft.Crm.Service.Dialogs.CancelCasePage::ConfigureForm`
- size: `441`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3280`

## pseudocode

```c

```

## disassembly

```asm
0x3280  ldarg.0
0x3281  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x3286  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x328b  stloc.0
0x328c  ldnull
0x328d  stloc.1
0x328e  ldloca.s 0
0x3290  ldarg.0
0x3291  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3296  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x329b  ldstr    aPid// "pId"
0x32a0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x32a5  call     instance void [mscorlib]System.Guid::.ctor(string)
0x32aa  ldstr    aIncident// "incident"
0x32af  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x32b4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x32b9  stloc.1
0x32ba  ldarg.0
0x32bb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x32c0  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x32c5  dup
0x32c6  ldarg.0
0x32c7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32cc  ldstr    aWebCsCasesDlgC_2// "Web.CS.cases.dlg_cancel.aspx_20"
0x32d1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32d6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x32db  dup
0x32dc  ldarg.0
0x32dd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x32e2  ldstr    aRibbonTooltipC// "Ribbon.Tooltip.CancelCase"
0x32e7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x32ec  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x32f1  dup
0x32f2  ldc.i4.0
0x32f3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x32f8  dup
0x32f9  ldc.i4.1
0x32fa  ldstr    aButtonLabelCon// "Button_Label_Confirm"
0x32ff  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x3304  ldc.i4.2
0x3305  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x330a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x330f  ldarg.0
0x3310  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x3315  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x331a  ldstr    aStatuscode// "statuscode"
0x331f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x3324  stloc.2
0x3325  ldloc.2
0x3326  brtrue.s loc_3343
0x3328  ldarg.0
0x3329  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Service.Dialogs.CancelCasePage::StatusPickerDiv
0x332e  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x3333  ldstr    aDisplay// "display"
0x3338  ldstr    aNone// "none"
0x333d  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x3342  ret
0x3343  ldarg.0
0x3344  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.CancelCasePage::statusCode
0x3349  ldloc.2
0x334a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x334f  ldstr    aIncident// "incident"
0x3354  ldc.i4.2
0x3355  stloc.s  5
0x3357  ldloca.s 5
0x3359  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.IncidentState
0x335f  callvirt instance string [mscorlib]System.Object::ToString()
0x3364  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x3369  stloc.3
0x336a  ldc.i4.0
0x336b  stloc.s  4
0x336d  ldloc.1
0x336e  ldloc.0
0x336f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3374  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCurrentStatusCode(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3379  stloc.s  4
0x337b  ldarg.0
0x337c  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.CancelCasePage::statusCode
0x3381  ldloc.s  4
0x3383  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_CurrentStatus(int32)
0x3388  ldarg.0
0x3389  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.CancelCasePage::statusCode
0x338e  ldc.i4.1
0x338f  newarr   [mscorlib]System.Int32
0x3394  dup
0x3395  ldc.i4.0
0x3396  ldloc.3
0x3397  stelem.i4
0x3398  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x339d  ldarg.0
0x339e  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.CancelCasePage::statusCode
0x33a3  callvirt instance int32 [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::get_OptionCount()
0x33a8  dup
0x33a9  ldc.i4.1
0x33aa  ble.s    loc_341B
0x33ac  ldarg.0
0x33ad  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x33b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x33b7  ldc.i4.2
0x33b8  stloc.s  5
0x33ba  ldloca.s 5
0x33bc  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.IncidentState
0x33c2  callvirt instance string [mscorlib]System.Object::ToString()
0x33c7  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetDefaultStatusForState(string, string)
0x33cc  stloc.s  6
0x33ce  ldc.i4.1
0x33cf  stloc.s  7
0x33d1  ldloc.2
0x33d2  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata
0x33d7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStatusOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata::get_StatusOptions()
0x33dc  ldloc.s  4
0x33de  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption>::get_Item(!!T0)
0x33e3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption::get_AllowedStatusTransition()
0x33e8  ldloc.s  6
0x33ea  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Contains(var<u1>)
0x33ef  stloc.s  7
0x33f1  ldloc.s  6
0x33f3  ldc.i4.m1
0x33f4  ceq
0x33f6  ldc.i4.0
0x33f7  ceq
0x33f9  ldloc.s  7
0x33fb  and
0x33fc  brfalse.s loc_341B
0x33fe  ldarg.0
0x33ff  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.CancelCasePage::statusCode
0x3404  ldarg.0
0x3405  ldloc.s  6
0x3407  dup
0x3408  stloc.s  8
0x340a  stfld    int32 Microsoft.Crm.Service.Dialogs.CancelCasePage::defaultStatusCode
0x340f  ldloc.s  8
0x3411  box      [mscorlib]System.Int32
0x3416  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x341b  ldc.i4.1
0x341c  bgt.s    loc_3438
0x341e  ldarg.0
0x341f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Service.Dialogs.CancelCasePage::StatusPickerDiv
0x3424  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x3429  ldstr    aDisplay// "display"
0x342e  ldstr    aNone// "none"
0x3433  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x3438  ret
```
