# Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::.ctor

- ea: `0x2310`
- end: `0x2322`
- name: `Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::.ctor`
- size: `18`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x90`
- `0x990`
- `0xd40`
- `0x2920`

## callees

- `0x2340`

## pseudocode

```c

```

## disassembly

```asm
0x2310  ldarg.0
0x2311  call     instance void [mscorlib]System.MarshalByRefObject::.ctor()
0x2316  ldarg.0
0x2317  call     int32 Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::GetDefaultLeaseTime()
0x231c  stfld    int32 Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::leaseTime
0x2321  ret
```
