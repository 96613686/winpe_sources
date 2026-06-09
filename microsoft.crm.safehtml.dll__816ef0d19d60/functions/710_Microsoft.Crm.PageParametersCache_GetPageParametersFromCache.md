# Microsoft.Crm.PageParametersCache::GetPageParametersFromCache

- ea: `0x710`
- end: `0x752`
- name: `Microsoft.Crm.PageParametersCache::GetPageParametersFromCache`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x480`
- `0x640`

## callees

- `0x710`
- `0x8c0`

## string_xrefs

- `0x724`: `Could not acquire read lock.`

## pseudocode

```c

```

## disassembly

```asm
0x710  ldnull
0x711  stloc.0
0x712  ldarg.0
0x713  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.PageParametersCache::_lock
0x718  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Crm.PageParametersCache::LockTimeout
0x71d  callvirt instance bool [System.Core]System.Threading.ReaderWriterLockSlim::TryEnterReadLock(valuetype [mscorlib]System.TimeSpan)
0x722  brtrue.s loc_72F
0x724  ldstr    aCouldNotAcquir// "Could not acquire read lock."
0x729  newobj   instance void Microsoft.Crm.PageParametersCacheException::.ctor(string message)
0x72e  throw
0x72f  nop
0x730  ldarg.0
0x731  ldfld    class [System]System.Collections.Specialized.HybridDictionary Microsoft.Crm.PageParametersCache::_pageParametersCache
0x736  ldarg.1
0x737  callvirt instance object [System]System.Collections.Specialized.HybridDictionary::get_Item(object)
0x73c  castclass Microsoft.Crm.PageParameters
0x741  stloc.0
0x742  leave.s  loc_750
0x744  ldarg.0
0x745  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.PageParametersCache::_lock
0x74a  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitReadLock()
0x74f  endfinally
0x750  ldloc.0
0x751  ret
```
