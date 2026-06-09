# Microsoft.Crm.Entities.PartyMappingItem::set_Parties

- ea: `0xc60`
- end: `0xc88`
- name: `Microsoft.Crm.Entities.PartyMappingItem::set_Parties`
- size: `40`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x160`
- `0x2f0`
- `0x350`
- `0x750`
- `0x7a0`
- `0x800`

## callees

- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0xc60  ldarg.1
0xc61  brfalse.s loc_C80
0xc63  ldarg.1
0xc64  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityName()
0xc69  ldstr    aActivityparty// "ActivityParty"
0xc6e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xc73  brfalse.s loc_C80
0xc75  ldstr    aPartiesMustBeB// "Parties must be BusinessEntityCollectio"...
0xc7a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0xc7f  throw
0xc80  ldarg.0
0xc81  ldarg.1
0xc82  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::parties
0xc87  ret
```
