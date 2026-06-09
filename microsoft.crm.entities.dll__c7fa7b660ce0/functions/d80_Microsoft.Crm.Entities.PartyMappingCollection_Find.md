# Microsoft.Crm.Entities.PartyMappingCollection::Find

- ea: `0xd80`
- end: `0xdaa`
- name: `Microsoft.Crm.Entities.PartyMappingCollection::Find`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x160`
- `0x360`
- `0x800`

## callees

- `0xc90`
- `0xd80`

## pseudocode

```c

```

## disassembly

```asm
0xd80  ldarg.0
0xd81  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xd86  stloc.0
0xd87  br.s     loc_DA0
0xd89  ldloc.0
0xd8a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd8f  castclass Microsoft.Crm.Entities.PartyMappingItem
0xd94  stloc.1
0xd95  ldarg.1
0xd96  ldloc.1
0xd97  callvirt instance valuetype Microsoft.Crm.Entities.ParticipationType Microsoft.Crm.Entities.PartyMappingItem::get_Type()
0xd9c  bne.un.s loc_DA0
0xd9e  ldloc.1
0xd9f  ret
0xda0  ldloc.0
0xda1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xda6  brtrue.s loc_D89
0xda8  ldnull
0xda9  ret
```
