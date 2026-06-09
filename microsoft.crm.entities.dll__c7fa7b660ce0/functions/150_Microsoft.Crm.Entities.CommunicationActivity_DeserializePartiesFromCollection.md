# Microsoft.Crm.Entities.CommunicationActivity::DeserializePartiesFromCollection

- ea: `0x150`
- end: `0x15f`
- name: `Microsoft.Crm.Entities.CommunicationActivity::DeserializePartiesFromCollection`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x160`

## pseudocode

```c

```

## disassembly

```asm
0x150  ldarg.0
0x151  ldarg.1
0x152  ldc.i4.0
0x153  ldarg.1
0x154  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x159  call     instance void Microsoft.Crm.Entities.CommunicationActivity::DeserializePartiesFromCollection(class [mscorlib]System.Collections.IList partiesToSort, int32 startIndex, int32 length)
0x15e  ret
```
