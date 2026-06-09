# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.UrlControl::ConfigureHeader

- ea: `0x2b0d0`
- end: `0x2b117`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.UrlControl::ConfigureHeader`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x17cd0`

## string_xrefs

- `0x2b0dc`: `LOCID_URLCTRL_INVALID_PROTOCOL`
- `0x2b0fc`: `LOCID_DBLCLICK_URL_OPEN`

## pseudocode

```c

```

## disassembly

```asm
0x2b0d0  ldarg.0
0x2b0d1  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::ConfigureHeader()
0x2b0d6  ldarg.0
0x2b0d7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2b0dc  ldstr    aLocidUrlctrlIn// "LOCID_URLCTRL_INVALID_PROTOCOL"
0x2b0e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2b0e6  ldstr    aWebFormsContro// "Web._forms.controls.INPUT.text.url.htc_"...
0x2b0eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2b0f0  ldc.i4.0
0x2b0f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2b0f6  ldarg.0
0x2b0f7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2b0fc  ldstr    aLocidDblclickU// "LOCID_DBLCLICK_URL_OPEN"
0x2b101  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2b106  ldstr    aWebFormsStyles_2// "Web._forms.styles.INPUT.url.htc_19"
0x2b10b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2b110  ldc.i4.0
0x2b111  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2b116  ret
```
