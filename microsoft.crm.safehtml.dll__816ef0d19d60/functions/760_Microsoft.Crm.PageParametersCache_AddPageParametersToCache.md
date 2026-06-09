# Microsoft.Crm.PageParametersCache::AddPageParametersToCache

- ea: `0x760`
- end: `0x79a`
- name: `Microsoft.Crm.PageParametersCache::AddPageParametersToCache`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x480`
- `0x640`

## callees

- `0x760`
- `0x8c0`

## string_xrefs

- `0x772`: `Could not acquire write lock.`

## pseudocode

```c

```

## disassembly

```asm
0x760  ldarg.0
0x761  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.PageParametersCache::_lock
0x766  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Crm.PageParametersCache::LockTimeout
0x76b  callvirt instance bool [System.Core]System.Threading.ReaderWriterLockSlim::TryEnterWriteLock(valuetype [mscorlib]System.TimeSpan)
0x770  brtrue.s loc_77D
0x772  ldstr    aCouldNotAcquir_0// "Could not acquire write lock."
0x777  newobj   instance void Microsoft.Crm.PageParametersCacheException::.ctor(string message)
0x77c  throw
0x77d  nop
0x77e  ldarg.0
0x77f  ldfld    class [System]System.Collections.Specialized.HybridDictionary Microsoft.Crm.PageParametersCache::_pageParametersCache
0x784  ldarg.1
0x785  ldarg.2
0x786  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::set_Item(object, object)
0x78b  leave.s  loc_799
0x78d  ldarg.0
0x78e  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.PageParametersCache::_lock
0x793  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitWriteLock()
0x798  endfinally
0x799  ret
```
