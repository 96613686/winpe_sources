# Microsoft.Crm.Common.MemoryCacheProvider::Remove

- ea: `0x430`
- end: `0x452`
- name: `Microsoft.Crm.Common.MemoryCacheProvider::Remove`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x380`
- `0x430`

## pseudocode

```c

```

## disassembly

```asm
0x430  ldarg.1
0x431  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x436  brfalse.s loc_443
0x438  ldstr    aKeyIsNullOrWhi// "Key is null or whitespace"
0x43d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x442  throw
0x443  ldarg.0
0x444  call     instance class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache Microsoft.Crm.Common.MemoryCacheProvider::get_Cache()
0x449  ldarg.1
0x44a  ldnull
0x44b  callvirt instance object [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Remove(string, string)
0x450  pop
0x451  ret
```
