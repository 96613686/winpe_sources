# Microsoft.Crm.Application.Components.UI.EditableSelect::ConfigureHeader

- ea: `0x17900`
- end: `0x17974`
- name: `Microsoft.Crm.Application.Components.UI.EditableSelect::ConfigureHeader`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2450`
- `0x3380`
- `0x38d0`
- `0x39f0`
- `0x17900`
- `0x23b60`
- `0x23f10`
- `0x24080`

## string_xrefs

- `0x17918`: `/_common/styles/select.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x17900  ldarg.0
0x17901  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x17906  ldarg.0
0x17907  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1790c  ldc.i4.1
0x1790d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool value)
0x17912  ldarg.0
0x17913  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x17918  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x1791d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x17922  ldarg.0
0x17923  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x17928  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x1792d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x17932  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x17937  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1793c  ldc.i4.0
0x1793d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x17942  ldarg.0
0x17943  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x17948  ldstr    aStaticControls_10// "/_static/_controls/editableselect/edita"...
0x1794d  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x17952  ldarg.0
0x17953  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x17958  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1795d  brtrue.s loc_17973
0x1795f  ldarg.0
0x17960  ldstr    aMscrmEditables// "Mscrm.EditableSelectControl"
0x17965  ldnull
0x17966  ldnull
0x17967  ldnull
0x17968  ldarg.0
0x17969  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1796e  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x17973  ret
```
