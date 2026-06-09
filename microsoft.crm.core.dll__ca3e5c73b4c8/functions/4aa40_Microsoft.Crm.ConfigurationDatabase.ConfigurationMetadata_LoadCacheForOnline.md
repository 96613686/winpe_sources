# Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::LoadCacheForOnline

- ea: `0x4aa40`
- end: `0x4aa96`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::LoadCacheForOnline`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4aa00`

## callees

- `0x34780`
- `0x4a0d0`
- `0x4a520`
- `0x4a650`
- `0x4aa40`
- `0x5f5b0`

## string_xrefs

- `0x4aa67`: `DumpConfigMetadataPath`
- `0x4aa85`: `ConfigMetadataDump.txt`

## pseudocode

```c

```

## disassembly

```asm
0x4aa40  newobj   instance void Microsoft.Crm.ConfigurationDatabase.OnlineMetadataXmlBuilder::.ctor()
0x4aa45  ldarg.0
0x4aa46  call     class Microsoft.Crm.ConfigurationDatabase.ConfigMetadataLoadOptions Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::get_LoadOptions()
0x4aa4b  ldloca.s 0
0x4aa4d  callvirt instance string Microsoft.Crm.ConfigurationDatabase.OnlineMetadataXmlBuilder::BuildXml(string geoConnectionString, class Microsoft.Crm.ConfigurationDatabase.ConfigMetadataLoadOptions loadOptions, [out] int32& maxBlobSize)
0x4aa52  stloc.1
0x4aa53  ldloc.1
0x4aa54  ldloc.0
0x4aa55  newobj   instance void Microsoft.Crm.SharedDatabase.DBMetadataCache::.ctor(string metadataXml, int32 maxBlobSize)
0x4aa5a  stloc.2
0x4aa5b  ldsflda  modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.Crm.SharedDatabase.DBMetadataCache Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::_cache
0x4aa60  ldloc.2
0x4aa61  call     T0x2B000084
0x4aa66  pop
0x4aa67  ldstr    aDumpconfigmeta// "DumpConfigMetadataPath"
0x4aa6c  ldsfld   string [mscorlib]System.String::Empty
0x4aa71  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x4aa76  castclass [mscorlib]System.String
0x4aa7b  stloc.3
0x4aa7c  ldloc.3
0x4aa7d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4aa82  brtrue.s loc_4AA95
0x4aa84  ldloc.3
0x4aa85  ldstr    aConfigmetadata// "ConfigMetadataDump.txt"
0x4aa8a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4aa8f  ldloc.1
0x4aa90  call     void [mscorlib]System.IO.File::WriteAllText(string, string)
0x4aa95  ret
```
