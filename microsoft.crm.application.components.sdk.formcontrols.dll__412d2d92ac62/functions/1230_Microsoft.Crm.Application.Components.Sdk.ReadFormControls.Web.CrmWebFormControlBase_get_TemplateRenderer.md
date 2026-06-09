# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TemplateRenderer

- ea: `0x1230`
- end: `0x124a`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TemplateRenderer`
- size: `26`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x13e0`
- `0x1560`
- `0x1a20`
- `0x2fe0`
- `0x82d0`
- `0x8430`
- `0x8580`
- `0x93e0`
- `0xe810`

## callees

- `0x1110`
- `0x1230`

## pseudocode

```c

```

## disassembly

```asm
0x1230  ldarg.0
0x1231  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::_templateRenderer
0x1236  dup
0x1237  brtrue.s loc_1249
0x1239  pop
0x123a  ldarg.0
0x123b  ldarg.0
0x123c  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.BindingTemplateRendererFactory::GetRenderer(class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase control)
0x1241  dup
0x1242  stloc.0
0x1243  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::_templateRenderer
0x1248  ldloc.0
0x1249  ret
```
