# Microsoft.Crm.Sdk.SchemaHelper::CreateSortedList

- ea: `0x6f50`
- end: `0x6f6a`
- name: `Microsoft.Crm.Sdk.SchemaHelper::CreateSortedList`
- size: `26`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x6f70`
- `0x7090`
- `0x77d0`
- `0x78f0`
- `0x7df0`

## pseudocode

```c

```

## disassembly

```asm
0x6f50  ldarg.0
0x6f51  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x6f56  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0x6f5b  dup
0x6f5c  ldarg.0
0x6f5d  callvirt instance void [mscorlib]System.Collections.ArrayList::AddRange(class [mscorlib]System.Collections.ICollection)
0x6f62  dup
0x6f63  ldarg.1
0x6f64  callvirt instance void [mscorlib]System.Collections.ArrayList::Sort(class [mscorlib]System.Collections.IComparer)
0x6f69  ret
```
