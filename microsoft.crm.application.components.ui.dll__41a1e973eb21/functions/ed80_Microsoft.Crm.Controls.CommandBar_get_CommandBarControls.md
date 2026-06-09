# Microsoft.Crm.Controls.CommandBar::get_CommandBarControls

- ea: `0xed80`
- end: `0xed87`
- name: `Microsoft.Crm.Controls.CommandBar::get_CommandBarControls`
- size: `7`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc6c0`
- `0xc6f0`
- `0xc760`
- `0xec80`
- `0xeee0`
- `0xef80`
- `0xf000`
- `0xf280`
- `0xf690`
- `0x11b10`
- `0x12480`

## callees

- `0xed30`

## pseudocode

```c

```

## disassembly

```asm
0xed80  ldarg.0
0xed81  call     instance class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::get_InternalControls()
0xed86  ret
```
