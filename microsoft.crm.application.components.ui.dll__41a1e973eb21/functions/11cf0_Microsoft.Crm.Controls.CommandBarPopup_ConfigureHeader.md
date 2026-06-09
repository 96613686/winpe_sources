# Microsoft.Crm.Controls.CommandBarPopup::ConfigureHeader

- ea: `0x11cf0`
- end: `0x11d73`
- name: `Microsoft.Crm.Controls.CommandBarPopup::ConfigureHeader`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc960`

## callees

- `0x33d0`
- `0x39f0`
- `0x116b0`
- `0x11ab0`
- `0x11af0`
- `0x11cf0`
- `0x125c0`
- `0x23b60`
- `0x23c50`
- `0x23d10`
- `0x23f10`

## string_xrefs

- `0x11d43`: `/_static/_controls/commandbar/commandbar.js`
- `0x11d16`: `Microsoft.Crm.CommandBar.CommandMenuPopup`
- `0x11d1d`: `Microsoft.Crm.CommandBar.CommandJewelPopup`
- `0x11d58`: `/_common/styles/menucore.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x11cf0  ldarg.0
0x11cf1  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x11cf6  ldarg.0
0x11cf7  call     instance class Microsoft.Crm.Controls.Menu Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x11cfc  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x11d01  ldarg.0
0x11d02  callvirt instance class Microsoft.Crm.Controls.ICrmCommandBar Microsoft.Crm.Controls.CommandBarControl::get_ParentCommandBar()
0x11d07  callvirt instance valuetype Microsoft.Crm.Controls.CommandBarType Microsoft.Crm.Controls.ICrmCommandBar::get_Type()
0x11d0c  brtrue.s loc_11D72
0x11d0e  ldarg.0
0x11d0f  call     instance bool Microsoft.Crm.Controls.CommandBarPopup::get_JewelMenu()
0x11d14  brtrue.s loc_11D1D
0x11d16  ldstr    aMicrosoftCrmCo_0// "Microsoft.Crm.CommandBar.CommandMenuPop"...
0x11d1b  br.s     loc_11D22
0x11d1d  ldstr    aMicrosoftCrmCo_1// "Microsoft.Crm.CommandBar.CommandJewelPo"...
0x11d22  stloc.0
0x11d23  ldarg.0
0x11d24  ldloc.0
0x11d25  ldnull
0x11d26  ldnull
0x11d27  ldnull
0x11d28  ldstr    aMnu// "mnu"
0x11d2d  ldarg.0
0x11d2e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11d33  call     string [mscorlib]System.String::Concat(string, string)
0x11d38  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x11d3d  ldarg.0
0x11d3e  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x11d43  ldstr    aStaticControls_22// "/_static/_controls/commandbar/commandba"...
0x11d48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0x11d4d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri file)
0x11d52  ldarg.0
0x11d53  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x11d58  ldstr    aCommonStylesMe// "/_common/styles/menucore.css.aspx"
0x11d5d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x11d62  ldarg.0
0x11d63  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x11d68  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x11d6d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x11d72  ret
```
