# Microsoft.Crm.Application.Components.UI.CrmFormUIControl::ConfigureHeader

- ea: `0x238a0`
- end: `0x238b7`
- name: `Microsoft.Crm.Application.Components.UI.CrmFormUIControl::ConfigureHeader`
- size: `23`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14600`
- `0x15540`
- `0x169d0`
- `0x16f30`
- `0x18d20`
- `0x194f0`
- `0x1f3f0`
- `0x20820`
- `0x21190`
- `0x22a30`
- `0x22f10`
- `0x26650`

## callees

- `0x3380`
- `0x23b60`
- `0x24080`

## pseudocode

```c

```

## disassembly

```asm
0x238a0  ldarg.0
0x238a1  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x238a6  ldarg.0
0x238a7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x238ac  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0x238b1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x238b6  ret
```
