# Microsoft.Crm.Web.EntityHomepage::ConfigureHeader

- ea: `0x23ac0`
- end: `0x24153`
- name: `Microsoft.Crm.Web.EntityHomepage::ConfigureHeader`
- size: `1683`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x56bf0`

## callees

- `0x23ac0`
- `0x24160`
- `0x24190`
- `0x24300`
- `0x24350`
- `0x243e0`
- `0x24460`
- `0x244f0`

## string_xrefs

- `0x23dce`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x23dbe`: `/_static/_common/scripts/PerformanceUI.js`
- `0x23e83`: `Sys.Application.findComponent('crmPageManager').applicationLoadHandler();`
- `0x23d52`: `MailboxService`
- `0x23b4f`: `SystemCustomization.EntityUtil.Messages.ConfirmEntityDelete`
- `0x23dde`: `/_static/_common/scripts/Performance.js`
- `0x23aec`: `SystemCustomization.EntityUtil.Messages.CannotUpdateSystemEntityIcons`
- `0x23b0d`: `SystemCustomization.EntityUtil.Messages.CannotDeleteSystemEntity`
- `0x23d32`: `CustomerService`
- `0x23d42`: `CustomerService`
- `0x23dae`: `/_static/_common/scripts/es6-shim.js`
- `0x24067`: `LoadResourcesforGenericQuickCreate`
- `0x24072`: `var scripts = ['/_static/_common/scripts/InlineEditCommon.js', '/_static/_controls/GlobalQuickCreate/GlobalQuickCreateBehavior.js'];\n										for(var i=0;i<scripts.length;i=i+1) {\n											var element = document.createElement('script');\n											element.src = scripts[i];\n											document.head.appendChild(element);\n										}`
- `0x240be`: `Mscrm.CrmHeader.setScriptFile(Mscrm.CrmUri.create('/_static/_common/scripts/react.js'),true);\nMscrm.CrmHeader.setScriptFile(Mscrm.CrmUri.create('/_static/_common/scripts/react-fela.js'),true);\nMscrm.CrmHeader.setScriptFile(Mscrm.CrmUri.create('/_static/_common/scripts/fela.js'),true);\nMscrm.CrmHeader.setScriptFile(Mscrm.CrmUri.create('/_static/_common/scripts/CustomControls.js'),true);`

## pseudocode

```c

```

## disassembly

```asm
0x23ac0  ldarg.0
0x23ac1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigureHeader()
0x23ac6  ldarg.0
0x23ac7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23acc  ldstr    aInitializeNoti// "Initialize NotificationContext"
0x23ad1  ldstr    aWindowTopNotif// "window.top.notificationContext='Global'"...
0x23ad6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x23adb  ldarg.0
0x23adc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23ae1  ldstr    aLocidEntutlCan// "LOCID_ENTUTL_CANTUPDSYSENTICN"
0x23ae6  ldarg.0
0x23ae7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23aec  ldstr    aSystemcustomiz_4// "SystemCustomization.EntityUtil.Messages"...
0x23af1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23af6  ldc.i4.0
0x23af7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23afc  ldarg.0
0x23afd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23b02  ldstr    aLocidEntutlCan_0// "LOCID_ENTUTL_CANTDELSYSENT"
0x23b07  ldarg.0
0x23b08  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23b0d  ldstr    aSystemcustomiz_5// "SystemCustomization.EntityUtil.Messages"...
0x23b12  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23b17  ldc.i4.0
0x23b18  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23b1d  ldarg.0
0x23b1e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23b23  ldstr    aLocidEntutlCan_1// "LOCID_ENTUTL_CANTPUBLISHENT"
0x23b28  ldarg.0
0x23b29  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23b2e  ldstr    aSystemcustomiz_6// "SystemCustomization.EntityUtil.Messages"...
0x23b33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23b38  ldc.i4.0
0x23b39  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23b3e  ldarg.0
0x23b3f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23b44  ldstr    aLocidEntutlCon// "LOCID_ENTUTL_CONFIRMDEL"
0x23b49  ldarg.0
0x23b4a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23b4f  ldstr    aSystemcustomiz_0// "SystemCustomization.EntityUtil.Messages"...
0x23b54  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23b59  ldc.i4.0
0x23b5a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23b5f  ldarg.0
0x23b60  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23b65  ldstr    aLocidEntutlCre// "LOCID_ENTUTL_CREATINGENT"
0x23b6a  ldarg.0
0x23b6b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23b70  ldstr    aSystemcustomiz_7// "SystemCustomization.EntityUtil.Messages"...
0x23b75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23b7a  ldc.i4.0
0x23b7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23b80  ldarg.0
0x23b81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23b86  ldstr    aLocidEntutlUpd// "LOCID_ENTUTL_UPDATINGENT"
0x23b8b  ldarg.0
0x23b8c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23b91  ldstr    aSystemcustomiz_8// "SystemCustomization.EntityUtil.Messages"...
0x23b96  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23b9b  ldc.i4.0
0x23b9c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23ba1  ldarg.0
0x23ba2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23ba7  ldstr    aLocidEntutlDel// "LOCID_ENTUTL_DELETINGENT"
0x23bac  ldarg.0
0x23bad  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23bb2  ldstr    aSystemcustomiz_9// "SystemCustomization.EntityUtil.Messages"...
0x23bb7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23bbc  ldc.i4.0
0x23bbd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23bc2  ldarg.0
0x23bc3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23bc8  ldstr    aLocidEntutlPub// "LOCID_ENTUTL_PUBLISHINGENT"
0x23bcd  ldarg.0
0x23bce  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23bd3  ldstr    aSystemcustomiz_10// "SystemCustomization.EntityUtil.Messages"...
0x23bd8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23bdd  ldc.i4.0
0x23bde  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23be3  ldarg.0
0x23be4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23be9  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0x23bee  ldarg.0
0x23bef  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23bf4  ldstr    aSystemcustomiz_11// "SystemCustomization.Validation.Errors.C"...
0x23bf9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23bfe  ldc.i4.0
0x23bff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23c04  ldarg.0
0x23c05  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23c0a  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0x23c0f  ldarg.0
0x23c10  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23c15  ldstr    aSystemcustomiz_12// "SystemCustomization.Validation.Errors.C"...
0x23c1a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23c1f  ldc.i4.0
0x23c20  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23c25  ldarg.0
0x23c26  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23c2b  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0x23c30  ldarg.0
0x23c31  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23c36  ldstr    aSystemcustomiz_13// "SystemCustomization.Validation.Errors.C"...
0x23c3b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23c40  ldc.i4.0
0x23c41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23c46  ldarg.0
0x23c47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23c4c  ldstr    aLocidVerboselo// "LOCID_VERBOSELOG_ERROR"
0x23c51  ldarg.0
0x23c52  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23c57  ldstr    aToggleverbosel// "ToggleVerboseLogging.ErrorMessage"
0x23c5c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23c61  ldc.i4.0
0x23c62  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23c67  ldarg.0
0x23c68  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23c6d  ldstr    aLocidVerboselo_0// "LOCID_VERBOSELOG_SUCCESS"
0x23c72  ldarg.0
0x23c73  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23c78  ldstr    aToggleverbosel_0// "ToggleVerboseLogging.SuccessMessage"
0x23c7d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23c82  ldc.i4.0
0x23c83  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23c88  ldarg.0
0x23c89  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23c8e  ldstr    aLocidVerboselo_1// "LOCID_VERBOSELOG_MAXMAILBOX"
0x23c93  ldarg.0
0x23c94  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23c99  ldstr    aToggleverbosel_1// "ToggleVerboseLogging.MaxMailbox"
0x23c9e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23ca3  ldc.i4.0
0x23ca4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23ca9  ldarg.0
0x23caa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23caf  ldstr    aLocidMailboxst// "LOCID_MAILBOXSTATISTICS_ON"
0x23cb4  ldarg.0
0x23cb5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23cba  ldstr    aTogglemailboxs// "ToggleMailboxStatistics.OnMessage"
0x23cbf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23cc4  ldc.i4.0
0x23cc5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23cca  ldarg.0
0x23ccb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23cd0  ldstr    aLocidMailboxst_0// "LOCID_MAILBOXSTATISTICS_OFF"
0x23cd5  ldarg.0
0x23cd6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23cdb  ldstr    aTogglemailboxs_0// "ToggleMailboxStatistics.OffMessage"
0x23ce0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23ce5  ldc.i4.0
0x23ce6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23ceb  ldarg.0
0x23cec  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23cf1  ldstr    aLocidUnapprove// "LOCID_UNAPPROVE_MAILBOX_VIEW"
0x23cf6  ldarg.0
0x23cf7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x23cfc  ldstr    aMailboxGridTes// "Mailbox.Grid.TestEnable.Message.Unappro"...
0x23d01  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23d06  ldc.i4.0
0x23d07  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x23d0c  ldarg.0
0x23d0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23d12  ldstr    aSystemcustomiz_14// "SystemCustomization"
0x23d17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x23d1c  ldarg.0
0x23d1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23d22  ldstr    aSystemcustomiz_14// "SystemCustomization"
0x23d27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathAshxWebService(string)
0x23d2c  ldarg.0
0x23d2d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23d32  ldstr    aCustomerservic// "CustomerService"
0x23d37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x23d3c  ldarg.0
0x23d3d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23d42  ldstr    aCustomerservic// "CustomerService"
0x23d47  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathAshxWebService(string)
0x23d4c  ldarg.0
0x23d4d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23d52  ldstr    aMailboxservice// "MailboxService"
0x23d57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x23d5c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x23d61  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23d66  ldarg.0
0x23d67  call     instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::get_HandlerEntityTypeCode()
0x23d6c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x23d71  stloc.0
0x23d72  ldarg.0
0x23d73  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23d78  ldstr    aEnforcestatetr// "_EnforceStateTransitions"
0x23d7d  ldloc.0
0x23d7e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x23d83  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x23d88  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::IsStateModelAware(valuetype [mscorlib]System.Guid)
0x23d8d  brfalse.s loc_23D97
0x23d8f  ldloc.0
0x23d90  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EnforceStateTransitions()
0x23d95  brtrue.s loc_23D9E
0x23d97  ldstr    a0_1// "0"
0x23d9c  br.s     loc_23DA3
0x23d9e  ldstr    a1// "1"
0x23da3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x23da8  ldarg.0
0x23da9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23dae  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/es6-shim.js"
0x23db3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x23db8  ldarg.0
0x23db9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23dbe  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/PerformanceUI."...
0x23dc3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x23dc8  ldarg.0
0x23dc9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23dce  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0x23dd3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x23dd8  ldarg.0
0x23dd9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23dde  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Performance.js"
0x23de3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x23de8  ldarg.0
0x23de9  call     instance void Microsoft.Crm.Web.EntityHomepage::LoadResourcesforGenericQuickCreate()
0x23dee  ldarg.0
0x23def  call     instance void Microsoft.Crm.Web.EntityHomepage::LoadResourcesforProductQuickCreate()
0x23df4  ldarg.0
0x23df5  call     instance void Microsoft.Crm.Web.EntityHomepage::LoadResourcesForTemplateTourDialog()
0x23dfa  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x23dff  stloc.1
0x23e00  ldloc.1
0x23e01  ldstr    aSubscribedeven// "subscribedEvents"
0x23e06  ldc.i4.1
0x23e07  newarr   [mscorlib]System.Int32
0x23e0c  dup
0x23e0d  ldc.i4.0
0x23e0e  ldc.i4.s 9
0x23e10  stelem.i4
0x23e11  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x23e16  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x23e1b  stloc.2
0x23e1c  ldarg.0
0x23e1d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EventManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::get_EventManager()
0x23e22  brfalse.s loc_23E3A
0x23e24  ldloc.2
0x23e25  ldstr    aEventmanager// "eventManager"
0x23e2a  ldarg.0
0x23e2b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EventManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::get_EventManager()
0x23e30  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x23e35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x23e3a  ldarg.0
0x23e3b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23e40  ldstr    aMscrmGridsizec// "Mscrm.GridSizeCalculator"
0x23e45  ldloc.1
0x23e46  ldnull
0x23e47  ldloc.2
0x23e48  ldstr    aHomepagetablec// "homepageTableCell"
0x23e4d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x23e52  ldarg.0
0x23e53  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x23e58  ldc.i4.1
0x23e59  newarr   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock
0x23e5e  dup
0x23e5f  ldc.i4.0
0x23e60  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x23e65  dup
0x23e66  ldstr    aInitpagemanage// "InitPageManager"
0x23e6b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string)
0x23e70  dup
0x23e71  ldc.i4   0x12C
0x23e76  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32)
0x23e7b  dup
0x23e7c  ldc.i4.1
0x23e7d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_DoNotUseSetTimeout(bool)
0x23e82  dup
0x23e83  ldstr    aSysApplication// "Sys.Application.findComponent('crmPageM"...
0x23e88  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string)
0x23e8d  stelem.ref
0x23e8e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock[])
0x23e93  ldarg.0
0x23e94  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0x23e99  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::RenderYammerGlobalVariables()
0x23e9e  ldarg.0
0x23e9f  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0x23ea4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::RenderActionHubGlobalVariables()
0x23ea9  ldarg.0
0x23eaa  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentEntityMetadata()
0x23eaf  brtrue.s loc_23EB8
0x23eb1  ldstr    asc_11EF2A// ""
0x23eb6  br.s     loc_23ECC
0x23eb8  ldarg.0
0x23eb9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentEntityMetadata()
0x23ebe  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x23ec3  dup
0x23ec4  brtrue.s loc_23ECC
0x23ec6  pop
0x23ec7  ldstr    asc_11EF2A// ""
0x23ecc  stloc.3
0x23ecd  ldarg.0
0x23ece  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentEntityMetadata()
0x23ed3  brtrue.s loc_23EDC
0x23ed5  ldstr    asc_11EF2A// ""
0x23eda  br.s     loc_23EF0
0x23edc  ldarg.0
0x23edd  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentEntityMetadata()
  ... truncated ...
```
