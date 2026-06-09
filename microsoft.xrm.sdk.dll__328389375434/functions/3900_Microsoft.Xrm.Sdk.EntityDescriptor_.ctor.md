# Microsoft.Xrm.Sdk.EntityDescriptor::.ctor

- ea: `0x3900`
- end: `0x3916`
- name: `Microsoft.Xrm.Sdk.EntityDescriptor::.ctor`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14a70`
- `0x23400`

## callees

- `0x38a0`
- `0x38d0`
- `0x38f0`

## pseudocode

```c

```

## disassembly

```asm
0x3900  ldarg.0
0x3901  ldarg.1
0x3902  call     instance void Microsoft.Xrm.Sdk.Descriptor::.ctor(valuetype Microsoft.Xrm.Sdk.EntityStates state)
0x3907  ldarg.0
0x3908  ldarg.2
0x3909  call     instance void Microsoft.Xrm.Sdk.EntityDescriptor::set_Identity(class Microsoft.Xrm.Sdk.EntityReference value)
0x390e  ldarg.0
0x390f  ldarg.3
0x3910  call     instance void Microsoft.Xrm.Sdk.EntityDescriptor::set_Entity(class Microsoft.Xrm.Sdk.Entity value)
0x3915  ret
```
