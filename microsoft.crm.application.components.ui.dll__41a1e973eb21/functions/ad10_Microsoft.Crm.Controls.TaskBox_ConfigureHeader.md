# Microsoft.Crm.Controls.TaskBox::ConfigureHeader

- ea: `0xad10`
- end: `0xad3b`
- name: `Microsoft.Crm.Controls.TaskBox::ConfigureHeader`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3380`
- `0x23b60`
- `0x23f10`
- `0x24080`

## string_xrefs

- `0xad1c`: `/_static/_controls/TaskBoxControl/TaskBoxControl.js`
- `0xad27`: `Mscrm.TaskBoxControl`

## pseudocode

```c

```

## disassembly

```asm
0xad10  ldarg.0
0xad11  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0xad16  ldarg.0
0xad17  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xad1c  ldstr    aStaticControls_18// "/_static/_controls/TaskBoxControl/TaskB"...
0xad21  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xad26  ldarg.0
0xad27  ldstr    aMscrmTaskboxco// "Mscrm.TaskBoxControl"
0xad2c  ldnull
0xad2d  ldnull
0xad2e  ldnull
0xad2f  ldarg.0
0xad30  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xad35  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0xad3a  ret
```
