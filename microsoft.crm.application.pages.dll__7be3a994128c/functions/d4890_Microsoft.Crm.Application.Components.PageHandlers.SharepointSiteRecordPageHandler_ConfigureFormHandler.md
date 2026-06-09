# Microsoft.Crm.Application.Components.PageHandlers.SharepointSiteRecordPageHandler::ConfigureFormHandler

- ea: `0xd4890`
- end: `0xd4b04`
- name: `Microsoft.Crm.Application.Components.PageHandlers.SharepointSiteRecordPageHandler::ConfigureFormHandler`
- size: `628`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0xd2130`
- `0xd2150`
- `0xd2180`
- `0xd4890`

## string_xrefs

- `0xd4925`: `SharePointSiteForm.Error.Validation_Fail_IE_Security_Settings`
- `0xd49e0`: `LOCID_SP_GRID_NOT_INSTALLED`
- `0xd49eb`: `SharePointSite.Form.ListComponentNotInstalled`
- `0xd4a01`: `LOCID_SP_GRID_INSTALLED`
- `0xd4a0c`: `SharePointSite.Form.ListComponentIsInstalled`

## pseudocode

```c

```

## disassembly

```asm
0xd4890  ldarg.0
0xd4891  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd4896  ldstr    aLocidSpParentS// "LOCID_SP_PARENT_SITE_EMPTY"
0xd489b  ldarg.0
0xd489c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd48a1  ldstr    aSharepointsite_3// "SharePointSiteForm.Error.ParentSiteEmpt"...
0xd48a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd48ab  ldc.i4.0
0xd48ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd48b1  ldarg.0
0xd48b2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd48b7  ldstr    aLocidSpRelUrlE// "LOCID_SP_REL_URL_EMPTY"
0xd48bc  ldarg.0
0xd48bd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd48c2  ldstr    aSharepointsite_4// "SharePointSiteForm.Error.RelativeURLEmp"...
0xd48c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd48cc  ldc.i4.0
0xd48cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd48d2  ldarg.0
0xd48d3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd48d8  ldstr    aLocidSpAbsUrlE// "LOCID_SP_ABS_URL_EMPTY"
0xd48dd  ldarg.0
0xd48de  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd48e3  ldstr    aSharepointsite_5// "SharePointSiteForm.Error.AbsoluteURLEmp"...
0xd48e8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd48ed  ldc.i4.0
0xd48ee  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd48f3  ldarg.0
0xd48f4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd48f9  ldstr    aLocidSpUrlNotv// "LOCID_SP_URL_NOTVALID"
0xd48fe  ldarg.0
0xd48ff  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd4904  ldstr    aSharepointsite_6// "SharePointSiteForm.Error.Validation_Fai"...
0xd4909  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd490e  ldc.i4.0
0xd490f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd4914  ldarg.0
0xd4915  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd491a  ldstr    aLocidSpIeSetti// "LOCID_SP_IE_SETTINGS"
0xd491f  ldarg.0
0xd4920  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd4925  ldstr    aSharepointsite_7// "SharePointSiteForm.Error.Validation_Fai"...
0xd492a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd492f  ldc.i4.0
0xd4930  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd4935  ldarg.0
0xd4936  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd493b  ldstr    aLocidSpDiffere// "LOCID_SP_DIFFERENT_SCHEMES"
0xd4940  ldarg.0
0xd4941  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd4946  ldstr    aSharepointsite_8// "SharePointSiteForm.Error.Validation_Fai"...
0xd494b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4950  ldc.i4.0
0xd4951  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd4956  ldarg.0
0xd4957  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd495c  ldstr    aLocidDocmCrmht// "LOCID_DOCM_CRMHTTPS_SPHTTP"
0xd4961  ldarg.0
0xd4962  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd4967  ldstr    aWebToolsDocume_4// "Web.Tools.DocumentManagement.SettingsPa"...
0xd496c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4971  ldc.i4.0
0xd4972  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd4977  ldarg.0
0xd4978  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd497d  ldstr    aLocidSpSaving// "LOCID_SP_SAVING"
0xd4982  ldarg.0
0xd4983  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd4988  ldstr    aSharepointForm// "SharePoint.Form.Saving"
0xd498d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4992  ldc.i4.0
0xd4993  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd4998  ldarg.0
0xd4999  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd499e  ldstr    aLocidSpValidat_10// "LOCID_SP_VALIDATING"
0xd49a3  ldarg.0
0xd49a4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd49a9  ldstr    aWebToolsDocume_65// "Web.Tools.DocumentManagement.SettingsPa"...
0xd49ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd49b3  ldc.i4.0
0xd49b4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd49b9  ldarg.0
0xd49ba  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd49bf  ldstr    aLocidDocmInval_0// "LOCID_DOCM_INVALIDURL"
0xd49c4  ldarg.0
0xd49c5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd49ca  ldstr    aWebToolsDocume_3// "Web.Tools.DocumentManagement.SettingsPa"...
0xd49cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd49d4  ldc.i4.0
0xd49d5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd49da  ldarg.0
0xd49db  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd49e0  ldstr    aLocidSpGridNot// "LOCID_SP_GRID_NOT_INSTALLED"
0xd49e5  ldarg.0
0xd49e6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd49eb  ldstr    aSharepointsite_9// "SharePointSite.Form.ListComponentNotIns"...
0xd49f0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd49f5  ldc.i4.0
0xd49f6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd49fb  ldarg.0
0xd49fc  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd4a01  ldstr    aLocidSpGridIns// "LOCID_SP_GRID_INSTALLED"
0xd4a06  ldarg.0
0xd4a07  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd4a0c  ldstr    aSharepointsite_10// "SharePointSite.Form.ListComponentIsInst"...
0xd4a11  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4a16  ldc.i4.0
0xd4a17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd4a1c  ldarg.0
0xd4a1d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd4a22  ldstr    aLocidDocmSpsit// "LOCID_DOCM_SPSITE_INVALIDPARENT"
0xd4a27  ldarg.0
0xd4a28  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd4a2d  ldstr    aSharepointsite_1// "SharePointSite.Error.InvalidParentURL"
0xd4a32  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4a37  ldc.i4.0
0xd4a38  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd4a3d  ldarg.0
0xd4a3e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd4a43  ldc.i4.5
0xd4a44  ldarg.0
0xd4a45  dup
0xd4a46  ldvirtftn instance void Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ChangeState(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xd4a4c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xd4a51  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xd4a56  ldarg.0
0xd4a57  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd4a5c  ldc.i4.6
0xd4a5d  ldarg.0
0xd4a5e  dup
0xd4a5f  ldvirtftn instance void Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ChangeState(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xd4a65  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xd4a6a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xd4a6f  ldarg.0
0xd4a70  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd4a75  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrudForm
0xd4a7a  ldarg.0
0xd4a7b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd4a80  ldarg.0
0xd4a81  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd4a86  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xd4a8b  dup
0xd4a8c  ldstr    aUrloption// "urloption"
0xd4a91  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xd4a96  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RadioControl
0xd4a9b  stloc.0
0xd4a9c  ldloc.0
0xd4a9d  ldarg.0
0xd4a9e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd4aa3  ldstr    aSharepointsite_11// "SharePointSiteForm.URLOption.AbsoluteUR"...
0xd4aa8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4aad  ldc.i4.0
0xd4aae  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RadioControl::AddItem(string, int32)
0xd4ab3  ldloc.0
0xd4ab4  ldarg.0
0xd4ab5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xd4aba  ldstr    aSharepointsite_12// "SharePointSiteForm.URLOption.RelativeUR"...
0xd4abf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4ac4  ldc.i4.1
0xd4ac5  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RadioControl::AddItem(string, int32)
0xd4aca  ldstr    aRelativeurl// "relativeurl"
0xd4acf  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xd4ad4  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl
0xd4ad9  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0xd4ade  castclass [mscorlib]System.String
0xd4ae3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd4ae8  brtrue.s loc_D4AF7
0xd4aea  ldloc.0
0xd4aeb  ldc.i4.1
0xd4aec  box      [mscorlib]System.Int32
0xd4af1  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xd4af6  ret
0xd4af7  ldloc.0
0xd4af8  ldc.i4.0
0xd4af9  box      [mscorlib]System.Int32
0xd4afe  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xd4b03  ret
```
