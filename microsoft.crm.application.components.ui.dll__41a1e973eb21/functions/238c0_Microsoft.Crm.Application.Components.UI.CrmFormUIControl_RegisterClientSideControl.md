# Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl

- ea: `0x238c0`
- end: `0x238cd`
- name: `Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl`
- size: `13`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14600`
- `0x15540`
- `0x15e10`
- `0x16a90`
- `0x16f30`
- `0x20820`
- `0x22a30`
- `0x22f10`

## callees

- `0x238d0`

## pseudocode

```c

```

## disassembly

```asm
0x238c0  ldarg.0
0x238c1  ldarg.1
0x238c2  ldstr    aMscrmFormdatac// "Mscrm.FormDataControl"
0x238c7  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName, string controlClassName)
0x238cc  ret
```
