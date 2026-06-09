# Microsoft.Crm.Dialogs.CloneProfilePage::ConfigurePage

- ea: `0x2f30`
- end: `0x2fae`
- name: `Microsoft.Crm.Dialogs.CloneProfilePage::ConfigurePage`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x2f36`: `/_common/styles/select.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x2f30  ldarg.0
0x2f31  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2f36  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x2f3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x2f40  ldarg.0
0x2f41  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2f46  ldstr    aStaticGridCmds// "/_static/_grid/cmds/multiaction.js"
0x2f4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2f50  ldarg.0
0x2f51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2f56  ldstr    aStaticGridCmds_0// "/_static/_grid/cmds/util.js"
0x2f5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2f60  ldarg.0
0x2f61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2f66  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x2f6b  ldarg.0
0x2f6c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2f71  ldstr    aLocidSavingMes// "LOCID_SAVING_MESSAGE"
0x2f76  ldarg.0
0x2f77  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2f7c  ldstr    aWebGridCmdsDlg_12// "Web._grid.cmds.dlg_cloneprofile.aspx_sa"...
0x2f81  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2f86  ldc.i4.0
0x2f87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2f8c  ldarg.0
0x2f8d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2f92  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x2f97  ldarg.0
0x2f98  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2f9d  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x2fa2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2fa7  ldc.i4.0
0x2fa8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2fad  ret
```
