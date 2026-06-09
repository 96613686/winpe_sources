# Microsoft.Crm.Entities.PartyMappingCollection::Find_0

- ea: `0xdb0`
- end: `0xded`
- name: `Microsoft.Crm.Entities.PartyMappingCollection::Find_0`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x250`
- `0x2f0`
- `0x7a0`

## callees

- `0xca0`
- `0xcb0`
- `0xdb0`

## pseudocode

```c

```

## disassembly

```asm
0xdb0  ldarg.0
0xdb1  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xdb6  stloc.0
0xdb7  br.s     loc_DE3
0xdb9  ldloc.0
0xdba  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xdbf  castclass Microsoft.Crm.Entities.PartyMappingItem
0xdc4  stloc.1
0xdc5  ldarg.1
0xdc6  ldloc.1
0xdc7  callvirt instance string Microsoft.Crm.Entities.PartyMappingItem::get_LogicalName()
0xdcc  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdd1  brtrue.s loc_DE1
0xdd3  ldloc.1
0xdd4  callvirt instance string[] Microsoft.Crm.Entities.PartyMappingItem::get_AliasedLogicalNames()
0xdd9  ldarg.1
0xdda  call     T0x2B000003
0xddf  brfalse.s loc_DE3
0xde1  ldloc.1
0xde2  ret
0xde3  ldloc.0
0xde4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xde9  brtrue.s loc_DB9
0xdeb  ldnull
0xdec  ret
```
