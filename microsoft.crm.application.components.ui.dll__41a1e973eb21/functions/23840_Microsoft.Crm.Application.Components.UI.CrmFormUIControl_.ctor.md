# Microsoft.Crm.Application.Components.UI.CrmFormUIControl::.ctor

- ea: `0x23840`
- end: `0x2384e`
- name: `Microsoft.Crm.Application.Components.UI.CrmFormUIControl::.ctor`
- size: `14`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x145b0`
- `0x154b0`
- `0x16a40`
- `0x17890`
- `0x178c0`
- `0x19090`
- `0x195e0`
- `0x1f280`
- `0x20c70`
- `0x210c0`
- `0x22890`
- `0x22d20`
- `0x26760`

## callees

- `0x23890`
- `0x24040`

## pseudocode

```c

```

## disassembly

```asm
0x23840  ldarg.0
0x23841  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::.ctor()
0x23846  ldarg.0
0x23847  ldc.i4.0
0x23848  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::set_RegisterClientSideAttribute(bool value)
0x2384d  ret
```
