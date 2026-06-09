# Microsoft.Crm.Sdk.CrmServiceInternal::.ctor

- ea: `0x540`
- end: `0x54d`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::.ctor`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xac50`

## callees

- `0x550`

## pseudocode

```c

```

## disassembly

```asm
0x540  ldarg.0
0x541  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x546  ldarg.1
0x547  call     instance void Microsoft.Crm.Sdk.CrmServiceInternal::.ctor(valuetype [mscorlib]System.Guid transactionContextId, class [mscorlib]System.Version endpointVersion)
0x54c  ret
```
