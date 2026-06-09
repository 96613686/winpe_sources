# Microsoft.Crm.Service.Dialogs.ReactivateCasePage::ConfigureForm

- ea: `0x3a90`
- end: `0x3c8f`
- name: `Microsoft.Crm.Service.Dialogs.ReactivateCasePage::ConfigureForm`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3a90`
- `0x3c90`

## pseudocode

```c

```

## disassembly

```asm
0x3a90  ldarg.0
0x3a91  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x3a96  ldarg.0
0x3a97  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x3a9c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x3aa1  stloc.0
0x3aa2  ldloc.0
0x3aa3  ldc.i4.0
0x3aa4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x3aa9  ldarg.0
0x3aaa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x3aaf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x3ab4  ldstr    aStatuscode// "statuscode"
0x3ab9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x3abe  stloc.1
0x3abf  ldarg.0
0x3ac0  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.ReactivateCasePage::statusCode
0x3ac5  ldloc.1
0x3ac6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x3acb  ldarg.0
0x3acc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x3ad1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x3ad6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EnforceStateTransitions()
0x3adb  brtrue.s loc_3AFE
0x3add  ldarg.0
0x3ade  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Service.Dialogs.ReactivateCasePage::StatusPickerDiv
0x3ae3  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x3ae8  ldstr    aDisplay// "display"
0x3aed  ldstr    aNone// "none"
0x3af2  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x3af7  ldarg.0
0x3af8  call     instance void Microsoft.Crm.Service.Dialogs.ReactivateCasePage::SetDialogProperties()
0x3afd  ret
0x3afe  ldarg.0
0x3aff  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3b04  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3b09  ldstr    aReason// "reason"
0x3b0e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3b13  ldstr    aNovalidstatust// "novalidstatustransition"
0x3b18  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b1d  brfalse.s loc_3B87
0x3b1f  ldarg.0
0x3b20  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Service.Dialogs.ReactivateCasePage::StatusPickerDiv
0x3b25  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x3b2a  ldstr    aDisplay// "display"
0x3b2f  ldstr    aNone// "none"
0x3b34  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x3b39  ldarg.0
0x3b3a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3b3f  ldarg.0
0x3b40  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3b45  ldstr    aWebRecordNoval// "Web.Record.NoValidStatusReasonTransitio"...
0x3b4a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3b4f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x3b54  ldloc.0
0x3b55  ldarg.0
0x3b56  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3b5b  ldstr    aWebRecordNoval// "Web.Record.NoValidStatusReasonTransitio"...
0x3b60  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3b65  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x3b6a  ldarg.0
0x3b6b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Service.Dialogs.ReactivateCasePage::statusMsg
0x3b70  ldstr    aWebRecordNoval_2// "Web.Record.NoValidStatusReasonTransitio"...
0x3b75  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x3b7a  ldloc.0
0x3b7b  ldc.i4.2
0x3b7c  ldstr    aButtonLabelOk// "Button_Label_OK"
0x3b81  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x3b86  ret
0x3b87  ldloca.s 2
0x3b89  ldarg.0
0x3b8a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3b8f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3b94  ldstr    aPid// "pId"
0x3b99  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3b9e  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3ba3  ldstr    aIncident// "incident"
0x3ba8  ldc.i4.0
0x3ba9  stloc.s  5
0x3bab  ldloca.s 5
0x3bad  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.IncidentState
0x3bb3  callvirt instance string [mscorlib]System.Object::ToString()
0x3bb8  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x3bbd  stloc.3
0x3bbe  ldarg.0
0x3bbf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x3bc4  ldloc.2
0x3bc5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3bca  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetCurrentStatusCode(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3bcf  stloc.s  4
0x3bd1  ldarg.0
0x3bd2  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.ReactivateCasePage::statusCode
0x3bd7  ldloc.s  4
0x3bd9  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_CurrentStatus(int32)
0x3bde  ldarg.0
0x3bdf  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.ReactivateCasePage::statusCode
0x3be4  ldc.i4.1
0x3be5  newarr   [mscorlib]System.Int32
0x3bea  dup
0x3beb  ldc.i4.0
0x3bec  ldloc.3
0x3bed  stelem.i4
0x3bee  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x3bf3  ldarg.0
0x3bf4  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.ReactivateCasePage::statusCode
0x3bf9  callvirt instance int32 [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::get_OptionCount()
0x3bfe  dup
0x3bff  ldc.i4.1
0x3c00  ble.s    loc_3C6B
0x3c02  ldarg.0
0x3c03  ldarg.0
0x3c04  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x3c09  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x3c0e  ldc.i4.0
0x3c0f  stloc.s  5
0x3c11  ldloca.s 5
0x3c13  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.IncidentState
0x3c19  callvirt instance string [mscorlib]System.Object::ToString()
0x3c1e  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetDefaultStatusForState(string, string)
0x3c23  stfld    int32 Microsoft.Crm.Service.Dialogs.ReactivateCasePage::defaultStatusCode
0x3c28  ldarg.0
0x3c29  ldfld    int32 Microsoft.Crm.Service.Dialogs.ReactivateCasePage::defaultStatusCode
0x3c2e  ldc.i4.m1
0x3c2f  beq.s    loc_3C6B
0x3c31  ldloc.1
0x3c32  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata
0x3c37  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStatusOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata::get_StatusOptions()
0x3c3c  ldloc.s  4
0x3c3e  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption>::get_Item(!!T0)
0x3c43  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption::get_AllowedStatusTransition()
0x3c48  ldarg.0
0x3c49  ldfld    int32 Microsoft.Crm.Service.Dialogs.ReactivateCasePage::defaultStatusCode
0x3c4e  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Contains(var<u1>)
0x3c53  brfalse.s loc_3C6B
0x3c55  ldarg.0
0x3c56  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Service.Dialogs.ReactivateCasePage::statusCode
0x3c5b  ldarg.0
0x3c5c  ldfld    int32 Microsoft.Crm.Service.Dialogs.ReactivateCasePage::defaultStatusCode
0x3c61  box      [mscorlib]System.Int32
0x3c66  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x3c6b  ldc.i4.1
0x3c6c  bgt.s    loc_3C88
0x3c6e  ldarg.0
0x3c6f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Service.Dialogs.ReactivateCasePage::StatusPickerDiv
0x3c74  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x3c79  ldstr    aDisplay// "display"
0x3c7e  ldstr    aNone// "none"
0x3c83  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x3c88  ldarg.0
0x3c89  call     instance void Microsoft.Crm.Service.Dialogs.ReactivateCasePage::SetDialogProperties()
0x3c8e  ret
```
