# Microsoft.Crm.Setup.Common.UI.PathSpaceControl::set_Path

- ea: `0xb1d0`
- end: `0xb1df`
- name: `Microsoft.Crm.Setup.Common.UI.PathSpaceControl::set_Path`
- size: `15`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8130`
- `0x8370`
- `0x83e0`
- `0x84c0`
- `0x8620`

## callees

- `0xb210`

## pseudocode

```c

```

## disassembly

```asm
0xb1d0  ldarg.0
0xb1d1  ldarg.1
0xb1d2  call     instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::RecalcAvailableSpace(string path)
0xb1d7  ldarg.0
0xb1d8  ldarg.1
0xb1d9  stfld    string Microsoft.Crm.Setup.Common.UI.PathSpaceControl::path
0xb1de  ret
```
