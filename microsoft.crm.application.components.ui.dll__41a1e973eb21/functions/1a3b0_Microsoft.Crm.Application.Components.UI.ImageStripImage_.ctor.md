# Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor

- ea: `0x1a3b0`
- end: `0x1a3be`
- name: `Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor`
- size: `14`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf7b0`
- `0x101a0`
- `0x11d80`
- `0x1ec60`
- `0x1fdf0`
- `0x25ab0`
- `0x27980`
- `0x27be0`
- `0x294e0`

## callees

- `0x1a3e0`
- `0x24040`

## pseudocode

```c

```

## disassembly

```asm
0x1a3b0  ldarg.0
0x1a3b1  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::.ctor()
0x1a3b6  ldarg.0
0x1a3b7  ldarg.1
0x1a3b8  call     instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::Initialize(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri source)
0x1a3bd  ret
```
