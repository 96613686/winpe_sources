# Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::BuildMetadataCacheFromMetadataContainer

- ea: `0x51730`
- end: `0x51770`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::BuildMetadataCacheFromMetadataContainer`
- size: `64`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x189d0`
- `0x4e790`
- `0x50fa0`
- `0x5bb60`

## callees

- `0x49c40`
- `0x51730`
- `0x51770`
- `0x523d0`

## string_xrefs

- `0x51730`: `BuildMetadataCacheFromMetadataContainer`
- `0x5173f`: `ASP_BEGIN_MDCACHE_LOADCACHE_BUILDFROMCONTAINERS`
- `0x51757`: `ASP_END_MDCACHE_LOADCACHE_BUILDFROMCONTAINERS`

## pseudocode

```c

```

## disassembly

```asm
0x51730  ldstr    aBuildmetadatac_0// "BuildMetadataCacheFromMetadataContainer"
0x51735  ldarg.3
0x51736  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x5173b  dup
0x5173c  starg.s  3
0x5173e  stloc.0
0x5173f  ldstr    aAspBeginMdcach_5// "ASP_BEGIN_MDCACHE_LOADCACHE_BUILDFROMCO"...
0x51744  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x51749  ldarg.0
0x5174a  ldarg.1
0x5174b  ldarg.2
0x5174c  ldarg.3
0x5174d  callvirt instance class Microsoft.Crm.Metadata.IMetadataCacheDataProvider Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::CreateMetadataCacheDataProvider(class Microsoft.Crm.Metadata.IMetadataContainer container, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x51752  newobj   instance void Microsoft.Crm.Metadata.ServerDynamicMetadataCache::.ctor(class Microsoft.Crm.Metadata.IMetadataCacheDataProvider provider)
0x51757  ldstr    aAspEndMdcacheL_1// "ASP_END_MDCACHE_LOADCACHE_BUILDFROMCONT"...
0x5175c  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x51761  stloc.1
0x51762  leave.s  loc_5176E
0x51764  ldloc.0
0x51765  brfalse.s loc_5176D
0x51767  ldloc.0
0x51768  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5176d  endfinally
0x5176e  ldloc.1
0x5176f  ret
```
