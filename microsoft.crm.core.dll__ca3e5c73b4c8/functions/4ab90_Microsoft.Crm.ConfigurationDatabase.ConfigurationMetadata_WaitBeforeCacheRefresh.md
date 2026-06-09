# Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::WaitBeforeCacheRefresh

- ea: `0x4ab90`
- end: `0x4ac00`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::WaitBeforeCacheRefresh`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4ab40`

## callees

- `0x1840`
- `0x2da40`
- `0x2daa0`
- `0x34790`
- `0x4ab90`
- `0x4ac00`

## string_xrefs

- `0x4ab96`: `ConfigMetadataRefreshMaxHoldoffInSeconds`
- `0x4abbe`: `ConfigMetadataRefreshMaxHoldoffInSeconds`

## pseudocode

```c

```

## disassembly

```asm
0x4ab90  call     int32 Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::get_DefaultMaxHoldoff()
0x4ab95  stloc.0
0x4ab96  ldstr    aConfigmetadata_0// "ConfigMetadataRefreshMaxHoldoffInSecond"...
0x4ab9b  call     object Microsoft.Crm.RegistryCache::GetValue(string key)
0x4aba0  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x4aba5  stloc.1
0x4aba6  ldloca.s 1
0x4aba8  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x4abad  brfalse.s loc_4ABB9
0x4abaf  ldloca.s 1
0x4abb1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x4abb6  stloc.0
0x4abb7  br.s     loc_4ABDB
0x4abb9  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4abbe  ldstr    aConfigmetadata_0// "ConfigMetadataRefreshMaxHoldoffInSecond"...
0x4abc3  ldc.i4.0
0x4abc4  callvirt T0x2B000095
0x4abc9  stloc.2
0x4abca  ldloca.s 2
0x4abcc  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x4abd1  brfalse.s loc_4ABDB
0x4abd3  ldloca.s 2
0x4abd5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x4abda  stloc.0
0x4abdb  newobj   instance void Microsoft.Crm.RandomHelper::.ctor()
0x4abe0  stloc.3
0x4abe1  ldloc.3
0x4abe2  ldloc.0
0x4abe3  ldc.i4   0x3E8
0x4abe8  mul
0x4abe9  callvirt instance int32 Microsoft.Crm.RandomHelper::Rand(int32 max)
0x4abee  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x4abf3  leave.s  loc_4ABFF
0x4abf5  ldloc.3
0x4abf6  brfalse.s loc_4ABFE
0x4abf8  ldloc.3
0x4abf9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4abfe  endfinally
0x4abff  ret
```
