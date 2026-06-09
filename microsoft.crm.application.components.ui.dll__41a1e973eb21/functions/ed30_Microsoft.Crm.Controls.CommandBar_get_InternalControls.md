# Microsoft.Crm.Controls.CommandBar::get_InternalControls

- ea: `0xed30`
- end: `0xed4a`
- name: `Microsoft.Crm.Controls.CommandBar::get_InternalControls`
- size: `26`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xed80`
- `0xedb0`
- `0xee20`
- `0xee80`
- `0xf1e0`
- `0xf220`
- `0xf4a0`
- `0xf5f0`

## callees

- `0xed30`
- `0xfdb0`

## pseudocode

```c

```

## disassembly

```asm
0xed30  ldarg.0
0xed31  ldfld    class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::_controls
0xed36  brtrue.s loc_ED43
0xed38  ldarg.0
0xed39  newobj   instance void Microsoft.Crm.Controls.CommandBarControlCollection::.ctor()
0xed3e  stfld    class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::_controls
0xed43  ldarg.0
0xed44  ldfld    class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::_controls
0xed49  ret
```
