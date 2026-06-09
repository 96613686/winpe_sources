# Microsoft.Crm.Common.MemoryCacheProvider::Contains

- ea: `0x460`
- end: `0x483`
- name: `Microsoft.Crm.Common.MemoryCacheProvider::Contains`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x380`
- `0x460`

## pseudocode

```c

```

## disassembly

```asm
0x460  ldarg.1
0x461  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x466  brfalse.s loc_473
0x468  ldstr    aKeyIsNullOrWhi// "Key is null or whitespace"
0x46d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x472  throw
0x473  ldarg.0
0x474  call     instance class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache Microsoft.Crm.Common.MemoryCacheProvider::get_Cache()
0x479  ldarg.1
0x47a  callvirt instance object [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::get_Item(string)
0x47f  ldnull
0x480  cgt.un
0x482  ret
```
