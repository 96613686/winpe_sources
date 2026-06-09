# Microsoft.Crm.Application.Controls.TreeNavControl::ConfigureHeader

- ea: `0xaee00`
- end: `0xaee67`
- name: `Microsoft.Crm.Application.Controls.TreeNavControl::ConfigureHeader`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xaece0`

## string_xrefs

- `0xaee26`: `/_common/styles/fonts.css.aspx`
- `0xaee16`: `/_common/styles/left.css.aspx`
- `0xaee36`: `/_common/styles/global.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0xaee00  ldarg.0
0xaee01  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaee06  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0xaee0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xaee10  ldarg.0
0xaee11  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaee16  ldstr    aCommonStylesLe// "/_common/styles/left.css.aspx"
0xaee1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xaee20  ldarg.0
0xaee21  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaee26  ldstr    aCommonStylesFo// "/_common/styles/fonts.css.aspx"
0xaee2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xaee30  ldarg.0
0xaee31  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaee36  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0xaee3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xaee40  ldarg.0
0xaee41  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaee46  ldstr    aControlsTreena// "/_controls/treenavcontrol/treenavcontro"...
0xaee4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xaee50  ldarg.0
0xaee51  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaee56  ldstr    aStaticControls_44// "/_static/_controls/TreeNav/treenavcontr"...
0xaee5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaee60  ldarg.0
0xaee61  call     instance void Microsoft.Crm.Application.Controls.TreeNavControl::RegisterAjaxComponent()
0xaee66  ret
```
