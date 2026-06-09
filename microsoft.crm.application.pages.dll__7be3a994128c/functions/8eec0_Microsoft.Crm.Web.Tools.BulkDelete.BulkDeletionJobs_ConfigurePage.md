# Microsoft.Crm.Web.Tools.BulkDelete.BulkDeletionJobs::ConfigurePage

- ea: `0x8eec0`
- end: `0x8ef66`
- name: `Microsoft.Crm.Web.Tools.BulkDelete.BulkDeletionJobs::ConfigurePage`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x8eec0`

## string_xrefs

- `0x8eec6`: `/_static/_common/scripts/stage.js`
- `0x8eee6`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`
- `0x8eef1`: `bulkdeleteoperation`
- `0x8ef3e`: `BulkDelete_NonrecurringJob_ErrMsg`
- `0x8ef5a`: `BulkDelete_Offline_Notification`

## pseudocode

```c

```

## disassembly

```asm
0x8eec0  ldarg.0
0x8eec1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8eec6  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/stage.js"
0x8eecb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8eed0  ldarg.0
0x8eed1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8eed6  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x8eedb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8eee0  ldarg.0
0x8eee1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8eee6  ldstr    aToolsPersonals// "/Tools/PersonalSettings/cmds/cmd_update"...
0x8eeeb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x8eef0  ldarg.0
0x8eef1  ldstr    aBulkdeleteoper// "bulkdeleteoperation"
0x8eef6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8eefb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8ef00  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x8ef05  ldarg.0
0x8ef06  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::SetView()
0x8ef0b  ldarg.0
0x8ef0c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.BulkDelete.BulkDeletionJobs::crmGrid
0x8ef11  ldarg.0
0x8ef12  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewType()
0x8ef17  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x8ef1c  ldarg.0
0x8ef1d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.BulkDelete.BulkDeletionJobs::crmGrid
0x8ef22  ldarg.0
0x8ef23  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewId()
0x8ef28  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0x8ef2d  ldarg.0
0x8ef2e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8ef33  ldstr    aLocidModifyRec// "LOCID_MODIFY_RECURRENCE_ERR_MSG"
0x8ef38  ldarg.0
0x8ef39  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8ef3e  ldstr    aBulkdeleteNonr// "BulkDelete_NonrecurringJob_ErrMsg"
0x8ef43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8ef48  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8ef4d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x8ef52  brtrue.s loc_8EF65
0x8ef54  ldarg.0
0x8ef55  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_Notifications()
0x8ef5a  ldstr    aBulkdeleteOffl// "BulkDelete_Offline_Notification"
0x8ef5f  ldc.i4.3
0x8ef60  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(string, int32)
0x8ef65  ret
```
