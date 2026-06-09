# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureControl

- ea: `0x178c0`
- end: `0x178e5`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureControl`
- size: `37`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x17d00`
- `0x19770`
- `0x19f70`
- `0x1a610`
- `0x1b370`
- `0x1c1b0`
- `0x1d330`
- `0x24ef0`

## callees

- `0x178c0`

## pseudocode

```c

```

## disassembly

```asm
0x178c0  ldarg.0
0x178c1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureControl()
0x178c6  ldarg.0
0x178c7  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x178cc  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage
0x178d1  stloc.0
0x178d2  ldloc.0
0x178d3  brfalse.s loc_178E4
0x178d5  ldloc.0
0x178d6  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_EnableOnDemandControlInit()
0x178db  brfalse.s loc_178E4
0x178dd  ldarg.0
0x178de  ldc.i4.1
0x178df  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_EnableOnDemandInit(bool)
0x178e4  ret
```
