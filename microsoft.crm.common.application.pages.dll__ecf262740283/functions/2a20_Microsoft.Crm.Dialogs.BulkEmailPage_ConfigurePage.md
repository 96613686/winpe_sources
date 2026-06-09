# Microsoft.Crm.Dialogs.BulkEmailPage::ConfigurePage

- ea: `0x2a20`
- end: `0x2deb`
- name: `Microsoft.Crm.Dialogs.BulkEmailPage::ConfigurePage`
- size: `971`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2a20`

## string_xrefs

- `0x2a3c`: `/_common/styles/dialogs.css.aspx`
- `0x2a4c`: `/_common/styles/global.css.aspx`
- `0x2a6c`: `/_common/styles/miniCal.css.aspx`
- `0x2a8c`: `/_static/_common/scripts/newdialog.js`
- `0x2acd`: `EmailTemplateService`
- `0x2b3a`: `AddTemplateWithoutAttachment`
- `0x2d4c`: `Dialog_BulkEmail_Template_Title`
- `0x2d62`: `Dialog_BulkEmail_Template_SubTitle`
- `0x2d78`: `Dialog_BulkEmail_Template_Description`
- `0x2d8e`: `Dialog_BulkEmail_Template_OkButton`
- `0x2dac`: `_templateTypeCode`

## pseudocode

```c

```

## disassembly

```asm
0x2a20  ldarg.0
0x2a21  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x2a26  ldarg.0
0x2a27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2a2c  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x2a31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x2a36  ldarg.0
0x2a37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2a3c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x2a41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x2a46  ldarg.0
0x2a47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2a4c  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0x2a51  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x2a56  ldarg.0
0x2a57  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2a5c  ldstr    aStaticControls_0// "/_static/_controls/datetime/date.js"
0x2a61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2a66  ldarg.0
0x2a67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2a6c  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x2a71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x2a76  ldarg.0
0x2a77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2a7c  ldstr    aStaticControls// "/_static/_controls/lookup/lookup.js"
0x2a81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2a86  ldarg.0
0x2a87  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2a8c  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/newdialog.js"
0x2a91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2a96  ldarg.0
0x2a97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2a9c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x2aa1  ldnull
0x2aa2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x2aa7  ldarg.0
0x2aa8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2aad  ldstr    aGridCmdsCmdBul// "/_grid/cmds/cmd_bulkemailfromids.aspx"
0x2ab2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x2ab7  ldarg.0
0x2ab8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2abd  ldstr    aGridCmdsCmdBul_0// "/_grid/cmds/cmd_bulkemailfromview.aspx"
0x2ac2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x2ac7  ldarg.0
0x2ac8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2acd  ldstr    aEmailtemplates// "EmailTemplateService"
0x2ad2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x2ad7  ldarg.0
0x2ad8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2add  ldstr    aMarketingautom// "MarketingAutomation"
0x2ae2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x2ae7  ldarg.0
0x2ae8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2aed  ldstr    aLocidNooneSele// "LOCID_NOONE_SELECTED"
0x2af2  ldarg.0
0x2af3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2af8  ldstr    aWebGridCmdsDlg_9// "Web._grid.cmds.dlg_bulkemail.aspx_99"
0x2afd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2b02  ldc.i4.0
0x2b03  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2b08  ldarg.0
0x2b09  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2b0e  ldstr    aLocidNoEmail// "LOCID_NO_EMAIL"
0x2b13  ldarg.0
0x2b14  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2b19  ldstr    aWebGridCmdsDlg_10// "Web._grid.cmds.dlg_bulkemail.aspx_161"
0x2b1e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2b23  ldc.i4.0
0x2b24  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2b29  ldarg.0
0x2b2a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2b2f  ldstr    aLocidAddWithou// "LOCID_ADD_WITHOUT_ATTACHMENT"
0x2b34  ldarg.0
0x2b35  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2b3a  ldstr    aAddtemplatewit// "AddTemplateWithoutAttachment"
0x2b3f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2b44  ldc.i4.0
0x2b45  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2b4a  ldarg.0
0x2b4b  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.BulkEmailPage::_crmLookup
0x2b50  brfalse.s loc_2BB1
0x2b52  ldarg.0
0x2b53  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.BulkEmailPage::_crmLookup
0x2b58  ldc.i4.2
0x2b59  newarr   [mscorlib]System.Int32
0x2b5e  dup
0x2b5f  ldc.i4.0
0x2b60  ldc.i4.8
0x2b61  stelem.i4
0x2b62  dup
0x2b63  ldc.i4.1
0x2b64  ldc.i4   0x7E4
0x2b69  stelem.i4
0x2b6a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x2b6f  ldarg.0
0x2b70  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.BulkEmailPage::_crmLookup
0x2b75  ldarg.0
0x2b76  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x2b7b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x2b80  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x2b85  ldc.i4.8
0x2b86  ldarg.0
0x2b87  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x2b8c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0x2b91  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::AddItem(string, int32, string)
0x2b96  ldarg.0
0x2b97  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.BulkEmailPage::_crmLookup
0x2b9c  ldarg.0
0x2b9d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2ba2  ldstr    aWebGridCmdsDlg_11// "Web._grid.cmds.dlg_bulkemail.aspx_390"
0x2ba7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2bac  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_AccessibilityLabel(string)
0x2bb1  ldarg.0
0x2bb2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2bb7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2bbc  ldstr    aObjecttypecode// "objectTypeCode"
0x2bc1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2bc6  ldc.i4.7
0x2bc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2bcc  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x2bd1  stloc.0
0x2bd2  ldarg.0
0x2bd3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2bd8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2bdd  ldstr    aObjectid// "objectId"
0x2be2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2be7  stloc.1
0x2be8  ldarg.0
0x2be9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2bee  ldstr    aObjectid_0// "_objectId"
0x2bf3  ldloc.1
0x2bf4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x2bf9  ldarg.0
0x2bfa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2bff  ldstr    aObjecttypecode_0// "_objectTypeCode"
0x2c04  ldloc.0
0x2c05  conv.i8
0x2c06  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x2c0b  ldc.i4.0
0x2c0c  stloc.2
0x2c0d  ldloc.0
0x2c0e  ldc.i4   0x10CC
0x2c13  bne.un.s loc_2C35
0x2c15  ldstr    aList// "list"
0x2c1a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2c1f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2c24  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x2c29  ldloc.1
0x2c2a  callvirt instance int32 [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.List::RetrieveListMemberType(string)
0x2c2f  stloc.2
0x2c30  br       loc_2CCE
0x2c35  ldloc.0
0x2c36  ldc.i4   0x1132
0x2c3b  bne.un   loc_2CCC
0x2c40  ldloc.1
0x2c41  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2c46  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2c4b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveListsForCampaignActivity(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2c50  stloc.s  4
0x2c52  ldloc.s  4
0x2c54  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x2c59  ldc.i4.0
0x2c5a  bgt.s    loc_2C6C
0x2c5c  ldstr    aNoMarketingLis// "No marketing list associated with the i"...
0x2c61  ldc.i4   0x80048454
0x2c66  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2c6b  throw
0x2c6c  ldloc.s  4
0x2c6e  ldc.i4.0
0x2c6f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x2c74  ldstr    aMembertype// "membertype"
0x2c79  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2c7e  unbox.any [mscorlib]System.Int32
0x2c83  stloc.s  5
0x2c85  ldc.i4.1
0x2c86  stloc.s  6
0x2c88  ldc.i4.1
0x2c89  stloc.s  7
0x2c8b  br.s     loc_2CB4
0x2c8d  ldloc.s  4
0x2c8f  ldloc.s  7
0x2c91  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x2c96  ldstr    aMembertype// "membertype"
0x2c9b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2ca0  unbox.any [mscorlib]System.Int32
0x2ca5  ldloc.s  5
0x2ca7  beq.s    loc_2CAE
0x2ca9  ldc.i4.0
0x2caa  stloc.s  6
0x2cac  br.s     loc_2CBF
0x2cae  ldloc.s  7
0x2cb0  ldc.i4.1
0x2cb1  add
0x2cb2  stloc.s  7
0x2cb4  ldloc.s  7
0x2cb6  ldloc.s  4
0x2cb8  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x2cbd  blt.s    loc_2C8D
0x2cbf  ldloc.s  6
0x2cc1  brfalse.s loc_2CC8
0x2cc3  ldloc.s  5
0x2cc5  stloc.2
0x2cc6  br.s     loc_2CCE
0x2cc8  ldc.i4.8
0x2cc9  stloc.2
0x2cca  br.s     loc_2CCE
0x2ccc  ldloc.0
0x2ccd  stloc.2
0x2cce  ldarg.0
0x2ccf  ldfld    bool Microsoft.Crm.Dialogs.BulkEmailPage::_isBulkMail
0x2cd4  brfalse.s loc_2D40
0x2cd6  ldarg.0
0x2cd7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2cdc  ldarg.0
0x2cdd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2ce2  ldstr    aMenuitemLabelS// "MenuItem_Label_SendDirectEmail"
0x2ce7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2cec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x2cf1  ldarg.0
0x2cf2  ldarg.0
0x2cf3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2cf8  ldstr    aMenuitemLabelS// "MenuItem_Label_SendDirectEmail"
0x2cfd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d02  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x2d07  ldarg.0
0x2d08  ldarg.0
0x2d09  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2d0e  ldstr    aDialogBulkemai// "Dialog_BulkEmail_Description"
0x2d13  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d18  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x2d1d  ldarg.0
0x2d1e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x2d23  ldstr    aButbegin// "butBegin"
0x2d28  ldstr    aMenuitemLabelS_0// "MenuItem_Label_Send"
0x2d2d  ldstr    aApplychanges_0// "applychanges()"
0x2d32  ldc.i4.0
0x2d33  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0x2d38  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0x2d3d  pop
0x2d3e  br.s     loc_2D99
0x2d40  ldarg.0
0x2d41  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2d46  ldarg.0
0x2d47  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2d4c  ldstr    aDialogBulkemai_0// "Dialog_BulkEmail_Template_Title"
0x2d51  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d56  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x2d5b  ldarg.0
0x2d5c  ldarg.0
0x2d5d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2d62  ldstr    aDialogBulkemai_1// "Dialog_BulkEmail_Template_SubTitle"
0x2d67  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d6c  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x2d71  ldarg.0
0x2d72  ldarg.0
0x2d73  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2d78  ldstr    aDialogBulkemai_2// "Dialog_BulkEmail_Template_Description"
0x2d7d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d82  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x2d87  ldarg.0
0x2d88  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x2d8d  ldc.i4.1
0x2d8e  ldstr    aDialogBulkemai_3// "Dialog_BulkEmail_Template_OkButton"
0x2d93  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons, string)
0x2d98  pop
0x2d99  ldarg.0
0x2d9a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x2d9f  ldc.i4.2
0x2da0  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x2da5  pop
0x2da6  ldarg.0
0x2da7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2dac  ldstr    aTemplatetypeco// "_templateTypeCode"
0x2db1  ldloc.2
0x2db2  conv.i8
0x2db3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x2db8  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x2dbd  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x2dc2  ldloc.2
0x2dc3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2dc8  call     string [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RetrieveEmailTemplates(int32, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2dcd  stloc.3
0x2dce  ldarg.0
0x2dcf  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Dialogs.BulkEmailPage::xmlRenderer
0x2dd4  ldloc.3
0x2dd5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XmlData(string)
0x2dda  ldarg.0
0x2ddb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer Microsoft.Crm.Dialogs.BulkEmailPage::xmlRenderer
0x2de0  ldstr    aGridcmdsbulkem// "gridCmdsBulkEmail.xsl"
0x2de5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.XmlRenderer::set_XslFileId(string)
0x2dea  ret
```
