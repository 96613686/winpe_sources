# Microsoft.Crm.Common.Web.TemplateManagerPage::ConfigurePage

- ea: `0x6540`
- end: `0x65b4`
- name: `Microsoft.Crm.Common.Web.TemplateManagerPage::ConfigurePage`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x654c`: `/_static/_common/scripts/stage.js`
- `0x656c`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`
- `0x6577`: `template`
- `0x655c`: `/_static/oobwebresource/Email_template_library.js`

## pseudocode

```c

```

## disassembly

```asm
0x6540  ldarg.0
0x6541  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigurePage()
0x6546  ldarg.0
0x6547  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x654c  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/stage.js"
0x6551  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6556  ldarg.0
0x6557  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x655c  ldstr    aStaticOobwebre// "/_static/oobwebresource/Email_template_"...
0x6561  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6566  ldarg.0
0x6567  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x656c  ldstr    aToolsPersonals// "/Tools/PersonalSettings/cmds/cmd_update"...
0x6571  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x6576  ldarg.0
0x6577  ldstr    aTemplate// "template"
0x657c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6581  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6586  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x658b  ldarg.0
0x658c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::SetView()
0x6591  ldarg.0
0x6592  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.TemplateManagerPage::crmGrid
0x6597  ldarg.0
0x6598  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewType()
0x659d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x65a2  ldarg.0
0x65a3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.TemplateManagerPage::crmGrid
0x65a8  ldarg.0
0x65a9  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewId()
0x65ae  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0x65b3  ret
```
