# Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::.ctor

- ea: `0xc90`
- end: `0xca5`
- name: `Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::.ctor`
- size: `21`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xcc0`
- `0xce0`
- `0xd20`
- `0xd60`
- `0xd90`

## pseudocode

```c

```

## disassembly

```asm
0xc90  ldarg.0
0xc91  ldc.i4.1
0xc92  stfld    bool Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::ShowLabel
0xc97  ldarg.0
0xc98  ldc.i4.1
0xc99  stfld    bool Microsoft.Crm.Application.SharedObjects.ControlDescriptorBase::Visible
0xc9e  ldarg.0
0xc9f  call     instance void [mscorlib]System.Object::.ctor()
0xca4  ret
```
