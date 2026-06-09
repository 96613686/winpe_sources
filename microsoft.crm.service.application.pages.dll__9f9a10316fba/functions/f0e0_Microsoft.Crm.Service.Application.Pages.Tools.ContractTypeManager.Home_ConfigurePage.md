# Microsoft.Crm.Service.Application.Pages.Tools.ContractTypeManager.Home::ConfigurePage

- ea: `0xf0e0`
- end: `0xf165`
- name: `Microsoft.Crm.Service.Application.Pages.Tools.ContractTypeManager.Home::ConfigurePage`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0xf0e6`: `/_static/_common/scripts/stage.js`
- `0xf106`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`
- `0xf111`: `contracttemplate`

## pseudocode

```c

```

## disassembly

```asm
0xf0e0  ldarg.0
0xf0e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0e6  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/stage.js"
0xf0eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0f0  ldarg.0
0xf0f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0f6  ldstr    aToolsContractt// "/tools/contracttypemanager/styles/contr"...
0xf0fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf100  ldarg.0
0xf101  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf106  ldstr    aToolsPersonals// "/Tools/PersonalSettings/cmds/cmd_update"...
0xf10b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0xf110  ldarg.0
0xf111  ldstr    aContracttempla_0// "contracttemplate"
0xf116  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf11b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf120  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xf125  ldarg.0
0xf126  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppViewSelector::.ctor()
0xf12b  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppViewSelector Microsoft.Crm.Service.Application.Pages.Tools.ContractTypeManager.Home::crmViewSelector
0xf130  ldarg.0
0xf131  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::SetView()
0xf136  ldarg.0
0xf137  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.ContractTypeManager.Home::crmGrid
0xf13c  ldarg.0
0xf13d  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewType()
0xf142  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0xf147  ldarg.0
0xf148  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.ContractTypeManager.Home::crmGrid
0xf14d  ldarg.0
0xf14e  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewId()
0xf153  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0xf158  ldarg.0
0xf159  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.ContractTypeManager.Home::crmGrid
0xf15e  ldc.i4.0
0xf15f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0xf164  ret
```
