# Microsoft.Crm.Dialogs.SelectEmailSignatureDialogPage::ConfigurePage

- ea: `0x3e30`
- end: `0x3fb5`
- name: `Microsoft.Crm.Dialogs.SelectEmailSignatureDialogPage::ConfigurePage`
- size: `389`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3e30`

## string_xrefs

- `0x3e4c`: `/_common/styles/dialogs.css.aspx`
- `0x3e5c`: `/_common/styles/global.css.aspx`
- `0x3e7c`: `/_common/styles/miniCal.css.aspx`
- `0x3e9c`: `/_static/_common/scripts/newdialog.js`
- `0x3f15`: `Dialog_BulkEmail_Template_OkButton`
- `0x3ebd`: `EmailSignatureService`

## pseudocode

```c

```

## disassembly

```asm
0x3e30  ldarg.0
0x3e31  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x3e36  ldarg.0
0x3e37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3e3c  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x3e41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x3e46  ldarg.0
0x3e47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3e4c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x3e51  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x3e56  ldarg.0
0x3e57  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3e5c  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0x3e61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x3e66  ldarg.0
0x3e67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3e6c  ldstr    aStaticControls_0// "/_static/_controls/datetime/date.js"
0x3e71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3e76  ldarg.0
0x3e77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3e7c  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x3e81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x3e86  ldarg.0
0x3e87  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3e8c  ldstr    aStaticControls// "/_static/_controls/lookup/lookup.js"
0x3e91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3e96  ldarg.0
0x3e97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3e9c  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/newdialog.js"
0x3ea1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3ea6  ldarg.0
0x3ea7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3eac  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x3eb1  ldnull
0x3eb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x3eb7  ldarg.0
0x3eb8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3ebd  ldstr    aEmailsignature// "EmailSignatureService"
0x3ec2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x3ec7  ldarg.0
0x3ec8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3ecd  ldarg.0
0x3ece  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3ed3  ldstr    aDialogEmailsig// "Dialog_EmailSignature_SelectSignature_T"...
0x3ed8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3edd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x3ee2  ldarg.0
0x3ee3  ldarg.0
0x3ee4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3ee9  ldstr    aDialogEmailsig// "Dialog_EmailSignature_SelectSignature_T"...
0x3eee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3ef3  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x3ef8  ldarg.0
0x3ef9  ldarg.0
0x3efa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3eff  ldstr    aDialogEmailsig_0// "Dialog_EmailSignature_SelectSignature_T"...
0x3f04  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3f09  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x3f0e  ldarg.0
0x3f0f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x3f14  ldc.i4.1
0x3f15  ldstr    aDialogBulkemai_3// "Dialog_BulkEmail_Template_OkButton"
0x3f1a  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons, string)
0x3f1f  pop
0x3f20  ldarg.0
0x3f21  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x3f26  ldc.i4.2
0x3f27  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x3f2c  pop
0x3f2d  ldloca.s 0
0x3f2f  ldarg.0
0x3f30  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3f35  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3f3a  ldstr    aOwnerid_0// "ownerId"
0x3f3f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3f44  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3f49  ldarg.0
0x3f4a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3f4f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3f54  ldstr    aEntityname_0// "entityName"
0x3f59  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3f5e  stloc.1
0x3f5f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x3f64  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x3f69  ldloc.0
0x3f6a  ldloc.1
0x3f6b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3f70  call     string [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RetrieveEmailSignatures(int32, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3f75  stloc.2
0x3f76  ldloc.2
0x3f77  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3f7c  brfalse.s loc_3F84
0x3f7e  ldstr    aEmailsignature_0// "<emailsignatures />"
0x3f83  stloc.2
0x3f84  ldarg.0
0x3f85  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Dialogs.SelectEmailSignatureDialogPage::xmlRenderer
0x3f8a  ldloc.2
0x3f8b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XmlData(string)
0x3f90  ldarg.0
0x3f91  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Dialogs.SelectEmailSignatureDialogPage::xmlRenderer
0x3f96  ldstr    aGridcmdsemails// "gridCmdsEmailSignature.xsl"
0x3f9b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XslFileId(string)
0x3fa0  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.EmailSignatureTelemetryEvents [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.EmailSignatureTelemetryEvents::get_Instance()
0x3fa5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3faa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x3faf  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.EmailSignatureTelemetryEvents::InsertSignatureButtonClicked(valuetype [mscorlib]System.Guid)
0x3fb4  ret
```
