# Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache

- ea: `0x4fd60`
- end: `0x4fecb`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4ec60`

## callees

- `0x4fd60`
- `0x503a0`
- `0x509a0`
- `0x50db0`
- `0x50e20`
- `0x523c0`

## string_xrefs

- `0x4fd68`: `LoadMetadataCache - LoadMethod=`
- `0x4fd79`: ` CacheType=`
- `0x4fdba`: `You cannot build a metadata cache from XML without providing the XML`
- `0x4fe48`: `LoadMetadataCache`
- `0x4fe68`: `MetadataCache is loading, but LoadMethod has not been set. LoadMethod.Database will be used instead. Please correct this error by explicitly setting the LoadMethod.`
- `0x4fea1`: `Load Method type Xml needs to provide XmlTextReader`

## pseudocode

```c

```

## disassembly

```asm
0x4fd60  ldc.i4.6
0x4fd61  newarr   [mscorlib]System.Object
0x4fd66  dup
0x4fd67  ldc.i4.0
0x4fd68  ldstr    aLoadmetadataca// "LoadMetadataCache - LoadMethod="
0x4fd6d  stelem.ref
0x4fd6e  dup
0x4fd6f  ldc.i4.1
0x4fd70  ldarg.0
0x4fd71  box      Microsoft.Crm.Metadata.LoadMethod
0x4fd76  stelem.ref
0x4fd77  dup
0x4fd78  ldc.i4.2
0x4fd79  ldstr    aCachetype_0// " CacheType="
0x4fd7e  stelem.ref
0x4fd7f  dup
0x4fd80  ldc.i4.3
0x4fd81  ldarg.1
0x4fd82  box      Microsoft.Crm.Metadata.CacheType
0x4fd87  stelem.ref
0x4fd88  dup
0x4fd89  ldc.i4.4
0x4fd8a  ldstr    aIsinclientcont// " IsInClientContext="
0x4fd8f  stelem.ref
0x4fd90  dup
0x4fd91  ldc.i4.5
0x4fd92  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x4fd97  stloc.1
0x4fd98  ldloca.s 1
0x4fd9a  call     instance string [mscorlib]System.Boolean::ToString()
0x4fd9f  stelem.ref
0x4fda0  call     string [mscorlib]System.String::Concat(object[])
0x4fda5  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name)
0x4fdaa  stloc.0
0x4fdab  ldarg.2
0x4fdac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4fdb1  stloc.2
0x4fdb2  ldarg.0
0x4fdb3  ldc.i4.2
0x4fdb4  beq.s    loc_4FDBA
0x4fdb6  ldarg.0
0x4fdb7  ldc.i4.3
0x4fdb8  bne.un.s loc_4FDC5
0x4fdba  ldstr    aYouCannotBuild// "You cannot build a metadata cache from "...
0x4fdbf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x4fdc4  throw
0x4fdc5  ldc.i4   0x5E90F
0x4fdca  stloc.3
0x4fdcb  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInAsyncServiceContext()
0x4fdd0  brtrue.s loc_4FDE0
0x4fdd2  ldloc.3
0x4fdd3  ldc.i4   0x1000
0x4fdd8  or
0x4fdd9  ldc.i4   0x80000
0x4fdde  or
0x4fddf  stloc.3
0x4fde0  ldarg.1
0x4fde1  ldc.i4.5
0x4fde2  bne.un.s loc_4FDEC
0x4fde4  ldloc.3
0x4fde5  ldc.i4   0xFFFFDFFF
0x4fdea  and
0x4fdeb  stloc.3
0x4fdec  ldloc.2
0x4fded  ldc.i4.s 0x19
0x4fdef  ldstr    aLoadingMetadat// "Loading metadata, method = {0}, type = "...
0x4fdf4  ldc.i4.4
0x4fdf5  newarr   [mscorlib]System.Object
0x4fdfa  dup
0x4fdfb  ldc.i4.0
0x4fdfc  ldarg.0
0x4fdfd  box      Microsoft.Crm.Metadata.LoadMethod
0x4fe02  stelem.ref
0x4fe03  dup
0x4fe04  ldc.i4.1
0x4fe05  ldarg.1
0x4fe06  box      Microsoft.Crm.Metadata.CacheType
0x4fe0b  stelem.ref
0x4fe0c  dup
0x4fe0d  ldc.i4.2
0x4fe0e  ldloc.3
0x4fe0f  box      Microsoft.Crm.Metadata.LoadMasks
0x4fe14  stelem.ref
0x4fe15  dup
0x4fe16  ldc.i4.3
0x4fe17  ldloc.2
0x4fe18  box      [mscorlib]System.Guid
0x4fe1d  stelem.ref
0x4fe1e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4fe23  ldarg.1
0x4fe24  ldarg.2
0x4fe25  call     class Microsoft.Crm.Metadata.DynamicMetadataCacheLoader Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::GetDynamicMetadataCacheLoader(valuetype Microsoft.Crm.Metadata.CacheType type, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x4fe2a  stloc.s  4
0x4fe2c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x4fe31  brfalse.s loc_4FE45
0x4fe33  ldarg.0
0x4fe34  ldloc.s  4
0x4fe36  ldloc.3
0x4fe37  ldarg.2
0x4fe38  ldloc.0
0x4fe39  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadCacheForRichClient(valuetype Microsoft.Crm.Metadata.LoadMethod loadMethod, class Microsoft.Crm.Metadata.DynamicMetadataCacheLoader loader, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x4fe3e  stloc.s  5
0x4fe40  leave    loc_4FEC8
0x4fe45  ldnull
0x4fe46  stloc.s  6
0x4fe48  ldstr    aLoadmetadataca_0// "LoadMetadataCache"
0x4fe4d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::.ctor(string)
0x4fe52  stloc.s  7
0x4fe54  ldloc.s  7
0x4fe56  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Start()
0x4fe5b  ldarg.0
0x4fe5c  brfalse.s loc_4FE68
0x4fe5e  ldarg.0
0x4fe5f  ldc.i4.1
0x4fe60  beq.s    loc_4FE85
0x4fe62  ldarg.0
0x4fe63  ldc.i4.6
0x4fe64  beq.s    loc_4FE92
0x4fe66  br.s     loc_4FEA1
0x4fe68  ldstr    aMetadatacacheI// "MetadataCache is loading, but LoadMetho"...
0x4fe6d  ldc.i4.0
0x4fe6e  newarr   [mscorlib]System.Object
0x4fe73  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Warning(string, object[])
0x4fe78  ldloc.s  4
0x4fe7a  ldloc.3
0x4fe7b  ldloc.0
0x4fe7c  callvirt instance class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::LoadCacheFromDatabase(valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x4fe81  stloc.s  6
0x4fe83  br.s     loc_4FEB1
0x4fe85  ldloc.s  4
0x4fe87  ldloc.3
0x4fe88  ldloc.0
0x4fe89  callvirt instance class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::LoadCacheFromDatabase(valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x4fe8e  stloc.s  6
0x4fe90  br.s     loc_4FEB1
0x4fe92  ldloc.s  4
0x4fe94  ldloc.3
0x4fe95  ldarg.2
0x4fe96  ldc.i4.0
0x4fe97  ldloc.0
0x4fe98  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadCacheFromWebService(class Microsoft.Crm.Metadata.DynamicMetadataCacheLoader loader, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool writeCacheToLocalFile, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x4fe9d  stloc.s  6
0x4fe9f  br.s     loc_4FEB1
0x4fea1  ldstr    aLoadMethodType// "Load Method type Xml needs to provide X"...
0x4fea6  ldstr    aMethod// "method"
0x4feab  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x4feb0  throw
0x4feb1  ldloc.s  7
0x4feb3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Stop()
0x4feb8  ldloc.s  6
0x4feba  stloc.s  5
0x4febc  leave.s  loc_4FEC8
0x4febe  ldloc.0
0x4febf  brfalse.s loc_4FEC7
0x4fec1  ldloc.0
0x4fec2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4fec7  endfinally
0x4fec8  ldloc.s  5
0x4feca  ret
```
