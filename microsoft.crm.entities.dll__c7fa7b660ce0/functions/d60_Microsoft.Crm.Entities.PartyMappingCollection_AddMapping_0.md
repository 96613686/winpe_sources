# Microsoft.Crm.Entities.PartyMappingCollection::AddMapping_0

- ea: `0xd60`
- end: `0xd72`
- name: `Microsoft.Crm.Entities.PartyMappingCollection::AddMapping_0`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa10`

## callees

- `0xc30`

## pseudocode

```c

```

## disassembly

```asm
0xd60  ldarg.1
0xd61  ldarg.2
0xd62  ldarg.3
0xd63  newobj   instance void Microsoft.Crm.Entities.PartyMappingItem::.ctor(valuetype Microsoft.Crm.Entities.ParticipationType participationType, string name, string[] aliasedNames)
0xd68  stloc.0
0xd69  ldarg.0
0xd6a  ldloc.0
0xd6b  call     instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd70  pop
0xd71  ret
```
