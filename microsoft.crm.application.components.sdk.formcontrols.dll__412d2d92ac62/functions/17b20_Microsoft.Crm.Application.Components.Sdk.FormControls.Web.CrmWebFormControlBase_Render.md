# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::Render

- ea: `0x17b20`
- end: `0x17b8a`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::Render`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1e180`
- `0x1ecd0`

## callees

- `0x179f0`
- `0x17b20`
- `0x17b90`
- `0x17bb0`
- `0x17bd0`
- `0x17bf0`
- `0x17c00`
- `0x17c10`

## pseudocode

```c

```

## disassembly

```asm
0x17b20  ldarg.0
0x17b21  call     instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlRenderMode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_RenderMode()
0x17b26  stloc.0
0x17b27  ldloc.0
0x17b28  switch   loc_17B52, loc_17B62, loc_17B4A, loc_17B82, loc_17B6A, loc_17B4A, loc_17B5A
0x17b49  ret
0x17b4a  ldarg.0
0x17b4b  ldarg.1
0x17b4c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::RenderStandard(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x17b51  ret
0x17b52  ldarg.0
0x17b53  ldarg.1
0x17b54  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::RenderForPrinting(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x17b59  ret
0x17b5a  ldarg.0
0x17b5b  ldarg.1
0x17b5c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::RenderForRead(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x17b61  ret
0x17b62  ldarg.0
0x17b63  ldarg.1
0x17b64  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::RenderForReadTemplate(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x17b69  ret
0x17b6a  ldarg.0
0x17b6b  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x17b70  brfalse.s loc_17B7A
0x17b72  ldarg.0
0x17b73  ldarg.1
0x17b74  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::RenderForMobileRead(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x17b79  ret
0x17b7a  ldarg.0
0x17b7b  ldarg.1
0x17b7c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::RenderForMobileEdit(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x17b81  ret
0x17b82  ldarg.0
0x17b83  ldarg.1
0x17b84  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::RenderForMobileRead(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x17b89  ret
```
