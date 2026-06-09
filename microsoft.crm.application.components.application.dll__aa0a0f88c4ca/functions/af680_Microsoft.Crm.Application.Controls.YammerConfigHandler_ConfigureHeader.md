# Microsoft.Crm.Application.Controls.YammerConfigHandler::ConfigureHeader

- ea: `0xaf680`
- end: `0xaf6c7`
- name: `Microsoft.Crm.Application.Controls.YammerConfigHandler::ConfigureHeader`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0xaf68c`: `YammerConfigWebService`
- `0xaf6a8`: `/_static/_controls/YammerConfigHandler/YammerConfigHandler.js`
- `0xaf6b3`: `Mscrm.YammerConfigHandler`

## pseudocode

```c

```

## disassembly

```asm
0xaf680  ldarg.0
0xaf681  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0xaf686  ldarg.0
0xaf687  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaf68c  ldstr    aYammerconfigwe// "YammerConfigWebService"
0xaf691  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xaf696  ldarg.0
0xaf697  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaf69c  ldc.i4.1
0xaf69d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xaf6a2  ldarg.0
0xaf6a3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xaf6a8  ldstr    aStaticControls_46// "/_static/_controls/YammerConfigHandler/"...
0xaf6ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaf6b2  ldarg.0
0xaf6b3  ldstr    aMscrmYammercon// "Mscrm.YammerConfigHandler"
0xaf6b8  ldnull
0xaf6b9  ldnull
0xaf6ba  ldnull
0xaf6bb  ldarg.0
0xaf6bc  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xaf6c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0xaf6c6  ret
```
