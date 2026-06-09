# Microsoft.Crm.Web.Tools.QueuePage::ConfigurePage

- ea: `0xac0`
- end: `0xb1e`
- name: `Microsoft.Crm.Web.Tools.QueuePage::ConfigurePage`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0xac6`: `/_static/_common/scripts/stage.js`
- `0xad6`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`

## pseudocode

```c

```

## disassembly

```asm
0xac0  ldarg.0
0xac1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xac6  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/stage.js"
0xacb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xad0  ldarg.0
0xad1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xad6  ldstr    aToolsPersonals// "/Tools/PersonalSettings/cmds/cmd_update"...
0xadb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0xae0  ldarg.0
0xae1  ldstr    aQueue// "queue"
0xae6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaeb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaf0  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xaf5  ldarg.0
0xaf6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::SetView()
0xafb  ldarg.0
0xafc  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.QueuePage::crmGrid
0xb01  ldarg.0
0xb02  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewType()
0xb07  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0xb0c  ldarg.0
0xb0d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Tools.QueuePage::crmGrid
0xb12  ldarg.0
0xb13  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewId()
0xb18  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0xb1d  ret
```
