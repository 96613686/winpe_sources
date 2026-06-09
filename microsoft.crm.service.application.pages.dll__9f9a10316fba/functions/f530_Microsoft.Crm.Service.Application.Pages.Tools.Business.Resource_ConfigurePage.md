# Microsoft.Crm.Service.Application.Pages.Tools.Business.Resource::ConfigurePage

- ea: `0xf530`
- end: `0xf5b4`
- name: `Microsoft.Crm.Service.Application.Pages.Tools.Business.Resource::ConfigurePage`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0xf54c`: `/_static/_common/scripts/stage.js`
- `0xf56c`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`

## pseudocode

```c

```

## disassembly

```asm
0xf530  ldarg.0
0xf531  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigurePage()
0xf536  ldarg.0
0xf537  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf53c  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0xf541  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf546  ldarg.0
0xf547  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf54c  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/stage.js"
0xf551  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf556  ldarg.0
0xf557  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf55c  ldstr    aStaticControls_3// "/_static/_controls/lookup/lookup.js"
0xf561  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf566  ldarg.0
0xf567  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf56c  ldstr    aToolsPersonals// "/Tools/PersonalSettings/cmds/cmd_update"...
0xf571  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0xf576  ldarg.0
0xf577  ldstr    aEquipment// "equipment"
0xf57c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf581  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf586  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xf58b  ldarg.0
0xf58c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::SetView()
0xf591  ldarg.0
0xf592  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Resource::crmGrid
0xf597  ldarg.0
0xf598  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewType()
0xf59d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0xf5a2  ldarg.0
0xf5a3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Resource::crmGrid
0xf5a8  ldarg.0
0xf5a9  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewId()
0xf5ae  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0xf5b3  ret
```
