# Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader

- ea: `0x24080`
- end: `0x2409f`
- name: `Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader`
- size: `31`
- prototype: ``
- caller_count: `20`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x390`
- `0xad10`
- `0xaec0`
- `0x149e0`
- `0x15c90`
- `0x17900`
- `0x17ed0`
- `0x183a0`
- `0x19240`
- `0x1ad90`
- `0x1bd00`
- `0x1ccf0`
- `0x1d7b0`
- `0x20470`
- `0x20db0`
- `0x21f40`
- `0x236c0`
- `0x238a0`
- `0x24430`
- `0x26230`

## callees

- `0x39f0`
- `0x23b60`
- `0x23d10`
- `0x24080`

## pseudocode

```c

```

## disassembly

```asm
0x24080  ldarg.0
0x24081  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x24086  ldarg.0
0x24087  ldfld    bool Microsoft.Crm.Application.Components.UI.CrmUIControl::_includeControlsCss
0x2408c  brfalse.s loc_2409E
0x2408e  ldarg.0
0x2408f  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x24094  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x24099  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x2409e  ret
```
