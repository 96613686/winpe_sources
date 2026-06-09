# Microsoft.Xrm.Sdk.LinkDescriptor::.ctor_0

- ea: `0x39a0`
- end: `0x39be`
- name: `Microsoft.Xrm.Sdk.LinkDescriptor::.ctor_0`
- size: `30`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x3990`
- `0x13a40`
- `0x13be0`

## callees

- `0x38a0`
- `0x3940`
- `0x3960`
- `0x3980`

## pseudocode

```c

```

## disassembly

```asm
0x39a0  ldarg.0
0x39a1  ldarg.1
0x39a2  call     instance void Microsoft.Xrm.Sdk.Descriptor::.ctor(valuetype Microsoft.Xrm.Sdk.EntityStates state)
0x39a7  ldarg.0
0x39a8  ldarg.2
0x39a9  call     instance void Microsoft.Xrm.Sdk.LinkDescriptor::set_Source(class Microsoft.Xrm.Sdk.Entity value)
0x39ae  ldarg.0
0x39af  ldarg.3
0x39b0  call     instance void Microsoft.Xrm.Sdk.LinkDescriptor::set_Relationship(class Microsoft.Xrm.Sdk.Relationship value)
0x39b5  ldarg.0
0x39b6  ldarg.s  4
0x39b8  call     instance void Microsoft.Xrm.Sdk.LinkDescriptor::set_Target(class Microsoft.Xrm.Sdk.Entity value)
0x39bd  ret
```
