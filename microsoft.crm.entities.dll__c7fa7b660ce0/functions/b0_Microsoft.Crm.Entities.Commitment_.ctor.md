# Microsoft.Crm.Entities.Commitment::.ctor

- ea: `0xb0`
- end: `0xbd`
- name: `Microsoft.Crm.Entities.Commitment::.ctor`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0xb1`: `Commitment`

## pseudocode

```c

```

## disassembly

```asm
0xb0  ldarg.0
0xb1  ldstr    aCommitment// "Commitment"
0xb6  ldarg.1
0xb7  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, valuetype [mscorlib]System.Guid)
0xbc  ret
```
