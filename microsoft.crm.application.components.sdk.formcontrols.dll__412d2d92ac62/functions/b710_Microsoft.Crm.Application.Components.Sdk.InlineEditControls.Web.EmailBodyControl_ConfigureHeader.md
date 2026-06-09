# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::ConfigureHeader

- ea: `0xb710`
- end: `0xb897`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::ConfigureHeader`
- size: `391`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1450`
- `0x1b80`
- `0xb710`
- `0xb8a0`

## string_xrefs

- `0xb7e0`: `Email_BadContent_Warning_With_No_Option_To_Open`
- `0xb800`: `Email_BadContent_Unblock_Command`

## pseudocode

```c

```

## disassembly

```asm
0xb710  ldarg.0
0xb711  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0xb716  ldarg.0
0xb717  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb71c  ldstr    aControlsHtmlba// "/_controls/htmlbar/htmlbar.css.aspx"
0xb721  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xb726  ldarg.0
0xb727  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb72c  ldstr    aStaticControls_7// "/_static/_controls/emailbody/emailbody."...
0xb731  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb736  ldarg.0
0xb737  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb73c  ldstr    aStaticFormsEma// "/_static/_forms/emailbodyinputbehavior."...
0xb741  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb746  ldarg.0
0xb747  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb74c  ldstr    aLocidDeverrorB_0// "LOCID_DEVERROR_BADTYPE_STRING"
0xb751  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb756  ldstr    aDeverrorBaddat_0// "DevError.BadDataType.String"
0xb75b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb760  ldc.i4.0
0xb761  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb766  ldarg.0
0xb767  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xb76c  brfalse.s loc_B7B0
0xb76e  ldarg.0
0xb76f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xb774  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_EntityId()
0xb779  ldarg.0
0xb77a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::_appointmentEntityId
0xb77f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb784  brfalse.s loc_B7B0
0xb786  ldarg.0
0xb787  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::IsRteAppointmentExperienceEnabled()
0xb78c  brfalse.s loc_B7B0
0xb78e  ldarg.0
0xb78f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb794  ldstr    aLocidEmailBadc// "LOCID_EMAIL_BADCONTENT_WARNING"
0xb799  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb79e  ldstr    aAppointmentBad// "Appointment_BadContent_Warning"
0xb7a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb7a8  ldc.i4.0
0xb7a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb7ae  br.s     loc_B7D0
0xb7b0  ldarg.0
0xb7b1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb7b6  ldstr    aLocidEmailBadc// "LOCID_EMAIL_BADCONTENT_WARNING"
0xb7bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb7c0  ldstr    aEmailBadconten_0// "Email_BadContent_Warning"
0xb7c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb7ca  ldc.i4.0
0xb7cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb7d0  ldarg.0
0xb7d1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb7d6  ldstr    aLocidEmailWarn// "LOCID_EMAIL_WARNING_NO_UNBLOCK"
0xb7db  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb7e0  ldstr    aEmailBadconten_1// "Email_BadContent_Warning_With_No_Option"...
0xb7e5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb7ea  ldc.i4.0
0xb7eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb7f0  ldarg.0
0xb7f1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb7f6  ldstr    aLocidEmailBadc_0// "LOCID_EMAIL_BADCONTENT_UNBLOCK"
0xb7fb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb800  ldstr    aEmailBadconten_2// "Email_BadContent_Unblock_Command"
0xb805  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb80a  ldc.i4.0
0xb80b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb810  ldarg.0
0xb811  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb816  ldstr    aLocidEmailBody// "LOCID_EMAIL_BODY_TOOLTIP"
0xb81b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb820  ldstr    aGeneralEmailBo// "General.Email.Body.Title"
0xb825  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb82a  ldc.i4.0
0xb82b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb830  ldarg.0
0xb831  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb836  ldstr    aLocidMsgbodyDe// "LOCID_MSGBODY_DEFAULTFONTFAMILY"
0xb83b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb840  ldstr    aMicrosoftCrmMs// "Microsoft_Crm_Msgbody_Default_fonts"
0xb845  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb84a  ldc.i4.0
0xb84b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb850  ldarg.0
0xb851  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb856  ldstr    aLocidMsgbodyDe_0// "LOCID_MSGBODY_DEFAULTFONTSIZE"
0xb85b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb860  ldstr    aHtmlbarCssAspx// "htmlbar.css.aspx.htmlStyle.font_size"
0xb865  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb86a  ldc.i4.0
0xb86b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb870  ldarg.0
0xb871  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::get_EmailHtmlBar()
0xb876  ldarg.0
0xb877  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xb87c  ldstr    aIframe// "IFrame"
0xb881  call     string [mscorlib]System.String::Concat(string, string)
0xb886  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl::set_TargetFrameId(string)
0xb88b  ldarg.0
0xb88c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::get_EmailHtmlBar()
0xb891  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0xb896  ret
```
