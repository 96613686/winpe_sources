# Microsoft.Crm.Service.Dialogs.ConfirmResolvePage::ConfigureForm

- ea: `0x2f10`
- end: `0x305c`
- name: `Microsoft.Crm.Service.Dialogs.ConfirmResolvePage::ConfigureForm`
- size: `332`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2f10`

## string_xrefs

- `0x2f66`: `/_static/_common/styles/AutoToolTip.js`
- `0x2f76`: `/_static/entities/ServiceRefreshUtilities.js`

## pseudocode

```c

```

## disassembly

```asm
0x2f10  ldarg.0
0x2f11  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x2f16  ldstr    aIncident// "incident"
0x2f1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2f20  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2f25  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x2f2a  ldarg.0
0x2f2b  ldarg.0
0x2f2c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2f31  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2f36  ldstr    aPid// "pId"
0x2f3b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2f40  stfld    string Microsoft.Crm.Service.Dialogs.ConfirmResolvePage::objectId
0x2f45  ldarg.0
0x2f46  ldfld    string Microsoft.Crm.Service.Dialogs.ConfirmResolvePage::objectId
0x2f4b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x2f50  ldarg.0
0x2f51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2f56  ldstr    aStaticCsCasesC// "/_static/cs/cases/cases.js"
0x2f5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2f60  ldarg.0
0x2f61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2f66  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x2f6b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2f70  ldarg.0
0x2f71  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2f76  ldstr    aStaticEntities// "/_static/entities/ServiceRefreshUtiliti"...
0x2f7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2f80  ldarg.0
0x2f81  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x2f86  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x2f8b  stloc.0
0x2f8c  ldloc.0
0x2f8d  ldc.i4.0
0x2f8e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x2f93  ldarg.0
0x2f94  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2f99  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2f9e  ldstr    aReason// "reason"
0x2fa3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2fa8  ldstr    aNovalidstatust// "novalidstatustransition"
0x2fad  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2fb2  brfalse.s loc_300E
0x2fb4  ldarg.0
0x2fb5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2fba  ldarg.0
0x2fbb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2fc0  ldstr    aWebRecordNavig// "Web.Record.NavigateConfirm.Window_Title"
0x2fc5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2fca  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x2fcf  ldloc.0
0x2fd0  ldarg.0
0x2fd1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2fd6  ldstr    aWebCsCasesDlgC// "Web._cs.Cases.dlg_ConfirmResolve.aspx_1"
0x2fdb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2fe0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x2fe5  ldarg.0
0x2fe6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Service.Dialogs.ConfirmResolvePage::statusMsg
0x2feb  ldstr    aWebCsCasesDlgC_0// "Web._cs.Cases.dlg_ConfirmResolve.aspx_3"
0x2ff0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x2ff5  ldloc.0
0x2ff6  ldc.i4.1
0x2ff7  ldstr    aButtonLabelCon// "Button_Label_Confirm"
0x2ffc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x3001  ldloc.0
0x3002  ldc.i4.2
0x3003  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x3008  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x300d  ret
0x300e  ldarg.0
0x300f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3014  ldarg.0
0x3015  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x301a  ldstr    aWebRecordNoval// "Web.Record.NoValidStatusReasonTransitio"...
0x301f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3024  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x3029  ldloc.0
0x302a  ldarg.0
0x302b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3030  ldstr    aWebRecordNoval// "Web.Record.NoValidStatusReasonTransitio"...
0x3035  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x303a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x303f  ldarg.0
0x3040  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Service.Dialogs.ConfirmResolvePage::statusMsg
0x3045  ldstr    aWebRecordNoval_0// "Web.Record.NoValidStatusReasonTransitio"...
0x304a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x304f  ldloc.0
0x3050  ldc.i4.2
0x3051  ldstr    aButtonLabelOk// "Button_Label_OK"
0x3056  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x305b  ret
```
