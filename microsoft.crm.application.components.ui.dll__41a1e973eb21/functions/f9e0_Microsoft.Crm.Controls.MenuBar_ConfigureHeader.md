# Microsoft.Crm.Controls.MenuBar::ConfigureHeader

- ea: `0xf9e0`
- end: `0xfa61`
- name: `Microsoft.Crm.Controls.MenuBar::ConfigureHeader`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x33d0`
- `0x38d0`
- `0x39f0`
- `0xef80`
- `0xf450`
- `0x23b60`
- `0x23f10`

## string_xrefs

- `0xf9ec`: `/_static/_controls/commandbar/commandbar.js`

## pseudocode

```c

```

## disassembly

```asm
0xf9e0  ldarg.0
0xf9e1  call     instance void Microsoft.Crm.Controls.CommandBar::ConfigureHeader()
0xf9e6  ldarg.0
0xf9e7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf9ec  ldstr    aStaticControls_22// "/_static/_controls/commandbar/commandba"...
0xf9f1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0xf9f6  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri file)
0xf9fb  ldarg.0
0xf9fc  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xfa01  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0xfa06  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0xfa0b  ldarg.0
0xfa0c  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xfa11  ldstr    aLocidCloseButt// "LOCID_CLOSE_BUTTON_LABEL"
0xfa16  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfa1b  ldstr    aButtonLabelClo// "Button_Label_Close"
0xfa20  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfa25  ldc.i4.0
0xfa26  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xfa2b  ldarg.0
0xfa2c  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xfa31  ldstr    aLocidPopupMenu// "LOCID_POPUP_MENU_LABEL"
0xfa36  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfa3b  ldstr    aPopupMenuTitle// "Popup_Menu_Title_Format"
0xfa40  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfa45  ldc.i4.0
0xfa46  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xfa4b  ldarg.0
0xfa4c  ldarg.0
0xfa4d  call     instance string Microsoft.Crm.Controls.MenuBar::get_ClientSideClassName()
0xfa52  ldnull
0xfa53  ldnull
0xfa54  ldnull
0xfa55  ldarg.0
0xfa56  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xfa5b  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0xfa60  ret
```
