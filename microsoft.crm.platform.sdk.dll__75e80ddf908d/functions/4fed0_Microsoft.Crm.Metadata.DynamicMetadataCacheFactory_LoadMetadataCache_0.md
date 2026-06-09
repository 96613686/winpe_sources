# Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache_0

- ea: `0x4fed0`
- end: `0x4ff9b`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache_0`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x4ec60`
- `0x6dd50`

## callees

- `0x4fed0`
- `0x50380`
- `0x50db0`
- `0x50e20`
- `0x523c0`

## string_xrefs

- `0x4fed8`: `LoadMetadataCache - LoadMethod=`
- `0x4fee9`: ` CacheType=`
- `0x4ff6e`: `LoadMetadataCache`
- `0x4ff56`: `Load Method Type should be Database for DynamicMetadataCache constructor that takes LoadMask parameter`

## pseudocode

```c

```

## disassembly

```asm
0x4fed0  ldc.i4.6
0x4fed1  newarr   [mscorlib]System.Object
0x4fed6  dup
0x4fed7  ldc.i4.0
0x4fed8  ldstr    aLoadmetadataca// "LoadMetadataCache - LoadMethod="
0x4fedd  stelem.ref
0x4fede  dup
0x4fedf  ldc.i4.1
0x4fee0  ldarg.0
0x4fee1  box      Microsoft.Crm.Metadata.LoadMethod
0x4fee6  stelem.ref
0x4fee7  dup
0x4fee8  ldc.i4.2
0x4fee9  ldstr    aCachetype_0// " CacheType="
0x4feee  stelem.ref
0x4feef  dup
0x4fef0  ldc.i4.3
0x4fef1  ldarg.1
0x4fef2  box      Microsoft.Crm.Metadata.CacheType
0x4fef7  stelem.ref
0x4fef8  dup
0x4fef9  ldc.i4.4
0x4fefa  ldstr    aLoadmasks// " LoadMasks="
0x4feff  stelem.ref
0x4ff00  dup
0x4ff01  ldc.i4.5
0x4ff02  ldarg.2
0x4ff03  box      Microsoft.Crm.Metadata.LoadMasks
0x4ff08  stelem.ref
0x4ff09  call     string [mscorlib]System.String::Concat(object[])
0x4ff0e  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name)
0x4ff13  stloc.0
0x4ff14  ldarg.3
0x4ff15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4ff1a  stloc.1
0x4ff1b  ldloc.1
0x4ff1c  ldc.i4.s 0x19
0x4ff1e  ldstr    aLoadingMetadat// "Loading metadata, method = {0}, type = "...
0x4ff23  ldc.i4.4
0x4ff24  newarr   [mscorlib]System.Object
0x4ff29  dup
0x4ff2a  ldc.i4.0
0x4ff2b  ldarg.0
0x4ff2c  box      Microsoft.Crm.Metadata.LoadMethod
0x4ff31  stelem.ref
0x4ff32  dup
0x4ff33  ldc.i4.1
0x4ff34  ldarg.1
0x4ff35  box      Microsoft.Crm.Metadata.CacheType
0x4ff3a  stelem.ref
0x4ff3b  dup
0x4ff3c  ldc.i4.2
0x4ff3d  ldarg.2
0x4ff3e  box      Microsoft.Crm.Metadata.LoadMasks
0x4ff43  stelem.ref
0x4ff44  dup
0x4ff45  ldc.i4.3
0x4ff46  ldloc.1
0x4ff47  box      [mscorlib]System.Guid
0x4ff4c  stelem.ref
0x4ff4d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ff52  ldarg.0
0x4ff53  ldc.i4.1
0x4ff54  beq.s    loc_4FF61
0x4ff56  ldstr    aLoadMethodType_0// "Load Method Type should be Database for"...
0x4ff5b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x4ff60  throw
0x4ff61  ldarg.2
0x4ff62  call     void Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::ValidateLoadMasks(valuetype Microsoft.Crm.Metadata.LoadMasks loadMask)
0x4ff67  ldarg.1
0x4ff68  ldarg.3
0x4ff69  call     class Microsoft.Crm.Metadata.DynamicMetadataCacheLoader Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::GetDynamicMetadataCacheLoader(valuetype Microsoft.Crm.Metadata.CacheType type, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x4ff6e  ldstr    aLoadmetadataca_0// "LoadMetadataCache"
0x4ff73  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::.ctor(string)
0x4ff78  stloc.2
0x4ff79  ldloc.2
0x4ff7a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Start()
0x4ff7f  ldarg.2
0x4ff80  ldloc.0
0x4ff81  callvirt instance class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::LoadCacheFromDatabase(valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x4ff86  ldloc.2
0x4ff87  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Stop()
0x4ff8c  stloc.3
0x4ff8d  leave.s  loc_4FF99
0x4ff8f  ldloc.0
0x4ff90  brfalse.s loc_4FF98
0x4ff92  ldloc.0
0x4ff93  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ff98  endfinally
0x4ff99  ldloc.3
0x4ff9a  ret
```
