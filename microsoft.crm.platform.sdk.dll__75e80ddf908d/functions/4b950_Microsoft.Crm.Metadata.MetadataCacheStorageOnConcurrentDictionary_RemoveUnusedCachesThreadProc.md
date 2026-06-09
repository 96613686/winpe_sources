# Microsoft.Crm.Metadata.MetadataCacheStorageOnConcurrentDictionary::RemoveUnusedCachesThreadProc

- ea: `0x4b950`
- end: `0x4bab3`
- name: `Microsoft.Crm.Metadata.MetadataCacheStorageOnConcurrentDictionary::RemoveUnusedCachesThreadProc`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x4b950`
- `0x4bac0`
- `0x4efd0`

## string_xrefs

- `0x4b964`: `RemoveUnusedCachesThreadProc Started. `
- `0x4ba1f`: `MetadataCacheItemRemoval thread found the metadata cache for this organization is not being actively used.  Results of attempting to remove the cache were, itemShouldStillBeRemoved: {0}; itemWasFound: {1}`
- `0x4ba73`: `Exception in RemoveUnusedCachesThreadProc: {0}`
- `0x4baa7`: `RemoveUnusedCachesThreadProc Stopped.`

## pseudocode

```c

```

## disassembly

```asm
0x4b950  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4b955  ldc.i4.s 0x14
0x4b957  ldstr    a0// "{0}"
0x4b95c  ldc.i4.1
0x4b95d  newarr   [mscorlib]System.Object
0x4b962  dup
0x4b963  ldc.i4.0
0x4b964  ldstr    aRemoveunusedca// "RemoveUnusedCachesThreadProc Started. "
0x4b969  stelem.ref
0x4b96a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4b96f  nop
0x4b970  ldc.i4   0xEA60
0x4b975  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x4b97a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x4b97f  stloc.0
0x4b980  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry> Microsoft.Crm.Metadata.MetadataCacheStorageOnConcurrentDictionary::_caches
0x4b985  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry>::GetEnumerator()
0x4b98a  stloc.1
0x4b98b  br.s     loc_4B9B5
0x4b98d  ldloc.1
0x4b98e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry>>::get_Current()
0x4b993  stloc.2
0x4b994  ldloca.s 2
0x4b996  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry>::get_Value()
0x4b99b  ldflda   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) int32 Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry::minutesToCacheExpiration
0x4b9a0  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x4b9a5  ldc.i4.0
0x4b9a6  bgt.s    loc_4B9B5
0x4b9a8  ldloc.0
0x4b9a9  ldloca.s 2
0x4b9ab  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry>::get_Key()
0x4b9b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x4b9b5  ldloc.1
0x4b9b6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4b9bb  brtrue.s loc_4B98D
0x4b9bd  leave.s  loc_4B9C9
0x4b9bf  ldloc.1
0x4b9c0  brfalse.s loc_4B9C8
0x4b9c2  ldloc.1
0x4b9c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4b9c8  endfinally
0x4b9c9  ldloc.0
0x4b9ca  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x4b9cf  stloc.3
0x4b9d0  br.s     loc_4BA43
0x4b9d2  ldloca.s 3
0x4b9d4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x4b9d9  stloc.s  4
0x4b9db  ldc.i4.0
0x4b9dc  stloc.s  5
0x4b9de  ldc.i4.0
0x4b9df  stloc.s  6
0x4b9e1  ldnull
0x4b9e2  stloc.s  7
0x4b9e4  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry> Microsoft.Crm.Metadata.MetadataCacheStorageOnConcurrentDictionary::_caches
0x4b9e9  ldloc.s  4
0x4b9eb  ldloca.s 7
0x4b9ed  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry>::TryGetValue(var<u1>, !!T0)
0x4b9f2  brfalse.s loc_4BA18
0x4b9f4  ldloc.s  7
0x4b9f6  volatile.
0x4b9f8  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) int32 Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry::minutesToCacheExpiration
0x4b9fd  ldc.i4.0
0x4b9fe  bgt.s    loc_4BA18
0x4ba00  ldc.i4.1
0x4ba01  stloc.s  5
0x4ba03  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry> Microsoft.Crm.Metadata.MetadataCacheStorageOnConcurrentDictionary::_caches
0x4ba08  ldloc.s  4
0x4ba0a  ldloca.s 7
0x4ba0c  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry>::TryRemove(var<u1>, !!T0)
0x4ba11  stloc.s  6
0x4ba13  call     void Microsoft.Crm.Metadata.MetadataCache::TrackNumberOfOrganizationsInCache()
0x4ba18  ldnull
0x4ba19  stloc.s  7
0x4ba1b  ldloc.s  4
0x4ba1d  ldc.i4.s 0x19
0x4ba1f  ldstr    aMetadatacachei// "MetadataCacheItemRemoval thread found t"...
0x4ba24  ldc.i4.2
0x4ba25  newarr   [mscorlib]System.Object
0x4ba2a  dup
0x4ba2b  ldc.i4.0
0x4ba2c  ldloc.s  5
0x4ba2e  box      [mscorlib]System.Boolean
0x4ba33  stelem.ref
0x4ba34  dup
0x4ba35  ldc.i4.1
0x4ba36  ldloc.s  6
0x4ba38  box      [mscorlib]System.Boolean
0x4ba3d  stelem.ref
0x4ba3e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ba43  ldloca.s 3
0x4ba45  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x4ba4a  brtrue.s loc_4B9D2
0x4ba4c  leave.s  loc_4BA5C
0x4ba4e  ldloca.s 3
0x4ba50  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x4ba56  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ba5b  endfinally
0x4ba5c  call     void Microsoft.Crm.Metadata.MetadataCacheStorageOnConcurrentDictionary::ResetCacheSlidingExpirationMinutes()
0x4ba61  leave    loc_4B96F
0x4ba66  pop
0x4ba67  rethrow
0x4ba69  stloc.s  8
0x4ba6b  ldloc.s  8
0x4ba6d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4ba72  ldc.i4.6
0x4ba73  ldstr    aExceptionInRem// "Exception in RemoveUnusedCachesThreadPr"...
0x4ba78  ldc.i4.1
0x4ba79  newarr   [mscorlib]System.Object
0x4ba7e  dup
0x4ba7f  ldc.i4.0
0x4ba80  ldloc.s  8
0x4ba82  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4ba87  stelem.ref
0x4ba88  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ba8d  leave    loc_4B96F
0x4ba92  ldnull
0x4ba93  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4ba98  ldc.i4.s 0x14
0x4ba9a  ldstr    a0// "{0}"
0x4ba9f  ldc.i4.1
0x4baa0  newarr   [mscorlib]System.Object
0x4baa5  dup
0x4baa6  ldc.i4.0
0x4baa7  ldstr    aRemoveunusedca_0// "RemoveUnusedCachesThreadProc Stopped."
0x4baac  stelem.ref
0x4baad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4bab2  endfinally
```
