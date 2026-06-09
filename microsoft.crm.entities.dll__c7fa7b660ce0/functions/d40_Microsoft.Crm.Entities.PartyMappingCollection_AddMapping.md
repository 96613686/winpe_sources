# Microsoft.Crm.Entities.PartyMappingCollection::AddMapping

- ea: `0xd40`
- end: `0xd51`
- name: `Microsoft.Crm.Entities.PartyMappingCollection::AddMapping`
- size: `17`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x30`
- `0xd0`
- `0xab0`
- `0xe10`
- `0xe60`

## callees

- `0xc00`

## pseudocode

```c

```

## disassembly

```asm
0xd40  ldarg.1
0xd41  ldarg.2
0xd42  newobj   instance void Microsoft.Crm.Entities.PartyMappingItem::.ctor(valuetype Microsoft.Crm.Entities.ParticipationType participationType, string name)
0xd47  stloc.0
0xd48  ldarg.0
0xd49  ldloc.0
0xd4a  call     instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd4f  pop
0xd50  ret
```
