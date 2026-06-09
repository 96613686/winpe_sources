# Microsoft.Crm.Application.SharedObjects.Descriptors.Dialog::.ctor

- ea: `0x3ce0`
- end: `0x3cee`
- name: `Microsoft.Crm.Application.SharedObjects.Descriptors.Dialog::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3b70`

## pseudocode

```c

```

## disassembly

```asm
0x3ce0  ldarg.0
0x3ce1  ldc.i4.1
0x3ce2  stfld    bool Microsoft.Crm.Application.SharedObjects.Descriptors.Dialog::IsTabletEnabled
0x3ce7  ldarg.0
0x3ce8  call     instance void Microsoft.Crm.Application.SharedObjects.Descriptors.ControlBase::.ctor()
0x3ced  ret
```
