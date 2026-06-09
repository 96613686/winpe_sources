# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::ConfigureHeader

- ea: `0x17cd0`
- end: `0x17ce2`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::ConfigureHeader`
- size: `18`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1abe0`
- `0x1acc0`
- `0x1b050`
- `0x1ec70`
- `0x203c0`
- `0x2aca0`
- `0x2b0d0`

## callees

- `0x17aa0`

## pseudocode

```c

```

## disassembly

```asm
0x17cd0  ldarg.0
0x17cd1  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureHeader()
0x17cd6  ldarg.0
0x17cd7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::_uiControl
0x17cdc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x17ce1  ret
```
