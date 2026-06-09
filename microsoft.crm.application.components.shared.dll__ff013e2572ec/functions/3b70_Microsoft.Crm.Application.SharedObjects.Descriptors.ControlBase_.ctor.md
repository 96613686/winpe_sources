# Microsoft.Crm.Application.SharedObjects.Descriptors.ControlBase::.ctor

- ea: `0x3b70`
- end: `0x3b85`
- name: `Microsoft.Crm.Application.SharedObjects.Descriptors.ControlBase::.ctor`
- size: `21`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x25c0`
- `0x3ba0`
- `0x3bc0`
- `0x3be0`
- `0x3c00`
- `0x3ce0`
- `0x3d10`

## pseudocode

```c

```

## disassembly

```asm
0x3b70  ldarg.0
0x3b71  ldc.i4.1
0x3b72  stfld    bool Microsoft.Crm.Application.SharedObjects.Descriptors.ControlBase::ShowLabel
0x3b77  ldarg.0
0x3b78  ldc.i4.1
0x3b79  stfld    bool Microsoft.Crm.Application.SharedObjects.Descriptors.ControlBase::Visible
0x3b7e  ldarg.0
0x3b7f  call     instance void [mscorlib]System.Object::.ctor()
0x3b84  ret
```
