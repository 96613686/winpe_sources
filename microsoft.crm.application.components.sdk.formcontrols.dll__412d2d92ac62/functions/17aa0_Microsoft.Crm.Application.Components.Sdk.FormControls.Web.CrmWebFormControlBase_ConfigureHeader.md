# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureHeader

- ea: `0x17aa0`
- end: `0x17ae7`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureHeader`
- size: `71`
- prototype: ``
- caller_count: `12`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16f90`
- `0x17cd0`
- `0x19a70`
- `0x19ed0`
- `0x1af30`
- `0x1b280`
- `0x1c1c0`
- `0x21770`
- `0x24ed0`
- `0x29280`
- `0x2a180`
- `0x2b1c0`

## callees

- `0x179f0`
- `0x17aa0`
- `0x17af0`
- `0x17b00`
- `0x17b10`

## pseudocode

```c

```

## disassembly

```asm
0x17aa0  ldarg.0
0x17aa1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x17aa6  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x17aab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x17ab0  ldarg.0
0x17ab1  call     instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlRenderMode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_RenderMode()
0x17ab6  stloc.0
0x17ab7  ldloc.0
0x17ab8  switch   loc_17AD9, loc_17AE6, loc_17AD2, loc_17AE6, loc_17AE0
0x17ad1  ret
0x17ad2  ldarg.0
0x17ad3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureHeaderStandard()
0x17ad8  ret
0x17ad9  ldarg.0
0x17ada  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureHeaderForPrinting()
0x17adf  ret
0x17ae0  ldarg.0
0x17ae1  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureHeaderForMobileRead()
0x17ae6  ret
```
