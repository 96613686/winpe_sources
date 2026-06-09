# Microsoft.Crm.Common.MemoryCacheProvider::GetItem

- ea: `0x3b0`
- end: `0x3d0`
- name: `Microsoft.Crm.Common.MemoryCacheProvider::GetItem`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x380`
- `0x3b0`

## pseudocode

```c

```

## disassembly

```asm
0x3b0  ldarg.1
0x3b1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3b6  brfalse.s loc_3C3
0x3b8  ldstr    aKeyIsNullOrWhi// "Key is null or whitespace"
0x3bd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3c2  throw
0x3c3  ldarg.0
0x3c4  call     instance class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache Microsoft.Crm.Common.MemoryCacheProvider::get_Cache()
0x3c9  ldarg.1
0x3ca  callvirt instance object [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::get_Item(string)
0x3cf  ret
```
