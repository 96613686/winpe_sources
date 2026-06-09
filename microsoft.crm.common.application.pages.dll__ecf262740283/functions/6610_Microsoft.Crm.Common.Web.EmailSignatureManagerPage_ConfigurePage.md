# Microsoft.Crm.Common.Web.EmailSignatureManagerPage::ConfigurePage

- ea: `0x6610`
- end: `0x6684`
- name: `Microsoft.Crm.Common.Web.EmailSignatureManagerPage::ConfigurePage`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x661c`: `/_static/_common/scripts/stage.js`
- `0x663c`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x6610  ldarg.0
0x6611  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigurePage()
0x6616  ldarg.0
0x6617  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x661c  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/stage.js"
0x6621  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6626  ldarg.0
0x6627  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x662c  ldstr    aToolsMailmerge// "/tools/mailmerge/styles/mailmerge.css.a"...
0x6631  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6636  ldarg.0
0x6637  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x663c  ldstr    aToolsPersonals// "/Tools/PersonalSettings/cmds/cmd_update"...
0x6641  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x6646  ldarg.0
0x6647  ldstr    aEmailsignature_1// "emailsignature"
0x664c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6651  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6656  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x665b  ldarg.0
0x665c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::SetView()
0x6661  ldarg.0
0x6662  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.EmailSignatureManagerPage::crmGrid
0x6667  ldarg.0
0x6668  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewType()
0x666d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x6672  ldarg.0
0x6673  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.EmailSignatureManagerPage::crmGrid
0x6678  ldarg.0
0x6679  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::get_HomepageViewId()
0x667e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0x6683  ret
```
