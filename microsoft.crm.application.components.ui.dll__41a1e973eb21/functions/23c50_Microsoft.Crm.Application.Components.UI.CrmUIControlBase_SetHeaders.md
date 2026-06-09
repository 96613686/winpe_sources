# Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders

- ea: `0x23c50`
- end: `0x23c66`
- name: `Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders`
- size: `22`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xe850`
- `0xef80`
- `0x11cf0`
- `0x15e10`
- `0x16f30`
- `0x18040`
- `0x18d20`
- `0x1ad90`
- `0x1bd00`
- `0x1be20`
- `0x1d7b0`
- `0x1d9e0`
- `0x1f440`
- `0x21190`
- `0x21c40`
- `0x26230`
- `0x26650`
- `0x281f0`

## callees

- `0x23c50`
- `0x23d10`

## pseudocode

```c

```

## disassembly

```asm
0x23c50  ldarg.0
0x23c51  ldfld    bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::_isHeaderConfigured
0x23c56  brtrue.s loc_23C65
0x23c58  ldarg.0
0x23c59  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x23c5e  ldarg.0
0x23c5f  ldc.i4.1
0x23c60  stfld    bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::_isHeaderConfigured
0x23c65  ret
```
