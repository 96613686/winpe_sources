# Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::BuildMetadataContainerFromDatabase

- ea: `0x5a7d0`
- end: `0x5a969`
- name: `Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::BuildMetadataContainerFromDatabase`
- size: `409`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x50cf0`
- `0x515d0`
- `0x523d0`
- `0x524e0`
- `0x52640`
- `0x52960`
- `0x5a7d0`
- `0x5a970`
- `0x5aaf0`
- `0x5ad80`
- `0x5ae90`
- `0x5b460`
- `0x5b4c0`
- `0x5b500`
- `0x5b570`
- `0x5b5a0`
- `0x5b610`
- `0x96a00`

## string_xrefs

- `0x5a7d8`: `You cannot load the latest properties XML into the multiple-org-sharable metadata cache - use either a Comparable or Optimized cache`
- `0x5a84b`: `Multi-org sharable cache loading system and non-system metadata with build number {0} and language {1}`
- `0x5a877`: `Multi-org sharable cache loading non-system metadata with build number {0} and language {1}. System data is already loaded. Language data is {2} loaded`
- `0x5a89c`: `already`

## pseudocode

```c

```

## disassembly

```asm
0x5a7d0  ldarg.1
0x5a7d1  ldc.i4.s 0x10
0x5a7d3  and
0x5a7d4  ldc.i4.s 0x10
0x5a7d6  bne.un.s loc_5A7E3
0x5a7d8  ldstr    aYouCannotLoadT// "You cannot load the latest properties X"...
0x5a7dd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5a7e2  throw
0x5a7e3  ldarg.2
0x5a7e4  ldc.i4.1
0x5a7e5  call     class [mscorlib]System.Version Microsoft.Crm.Metadata.Helpers::GetVersionFromDatabase(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, valuetype Microsoft.Crm.Metadata.VersionType versionType)
0x5a7ea  callvirt instance string [mscorlib]System.Object::ToString()
0x5a7ef  stloc.0
0x5a7f0  call     class Microsoft.Crm.Caching.OrganizationLanguagePackVersionCache Microsoft.Crm.Caching.OrganizationLanguagePackVersionCache::Instance()
0x5a7f5  ldarg.0
0x5a7f6  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_OrganizationContext()
0x5a7fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a800  ldarg.0
0x5a801  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_OrganizationContext()
0x5a806  callvirt instance var<u1> class Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class Microsoft.Crm.Caching.OrganizationLanguagePackVersionCacheData>>::LookupEntry(void, var<u1>)
0x5a80b  call     T0x2B0000A4
0x5a810  stloc.s  5
0x5a812  ldloca.s 5
0x5a814  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class Microsoft.Crm.Caching.OrganizationLanguagePackVersionCacheData>::get_Key()
0x5a819  stloc.1
0x5a81a  ldloc.1
0x5a81b  brfalse.s loc_5A820
0x5a81d  ldloc.1
0x5a81e  br.s     loc_5A827
0x5a820  ldarg.0
0x5a821  ldarg.2
0x5a822  call     instance int32 Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::GetOrganizationLCIDFromDatabase(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser)
0x5a827  stloc.2
0x5a828  ldarg.0
0x5a829  ldloc.0
0x5a82a  call     instance bool Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::IsSystemDataLoaded(string organizationBuildNumber)
0x5a82f  stloc.3
0x5a830  ldarg.0
0x5a831  ldloc.0
0x5a832  ldloc.2
0x5a833  call     instance bool Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::IsSystemLanguageDataLoaded(string organizationBuildNumber, int32 languageCode)
0x5a838  stloc.s  4
0x5a83a  ldloc.3
0x5a83b  brtrue.s loc_5A86A
0x5a83d  ldnull
0x5a83e  ldarg.0
0x5a83f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_OrganizationContext()
0x5a844  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a849  ldc.i4.s 0x19
0x5a84b  ldstr    aMultiOrgSharab// "Multi-org sharable cache loading system"...
0x5a850  ldc.i4.2
0x5a851  newarr   [mscorlib]System.Object
0x5a856  dup
0x5a857  ldc.i4.0
0x5a858  ldloc.0
0x5a859  stelem.ref
0x5a85a  dup
0x5a85b  ldc.i4.1
0x5a85c  ldloc.2
0x5a85d  box      [mscorlib]System.Int32
0x5a862  stelem.ref
0x5a863  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5a868  br.s     loc_5A8A7
0x5a86a  ldarg.0
0x5a86b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_OrganizationContext()
0x5a870  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a875  ldc.i4.s 0x19
0x5a877  ldstr    aMultiOrgSharab_0// "Multi-org sharable cache loading non-sy"...
0x5a87c  ldc.i4.3
0x5a87d  newarr   [mscorlib]System.Object
0x5a882  dup
0x5a883  ldc.i4.0
0x5a884  ldloc.0
0x5a885  stelem.ref
0x5a886  dup
0x5a887  ldc.i4.1
0x5a888  ldloc.2
0x5a889  box      [mscorlib]System.Int32
0x5a88e  stelem.ref
0x5a88f  dup
0x5a890  ldc.i4.2
0x5a891  ldloc.s  4
0x5a893  brtrue.s loc_5A89C
0x5a895  ldstr    aNot_0// "not"
0x5a89a  br.s     loc_5A8A1
0x5a89c  ldstr    aAlready// "already"
0x5a8a1  stelem.ref
0x5a8a2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5a8a7  ldstr    aBuildmetadatac_1// "BuildMetadataContainerFromDatabase - is"...
0x5a8ac  ldloca.s 3
0x5a8ae  call     instance string [mscorlib]System.Boolean::ToString()
0x5a8b3  ldstr    aIssystemlangua// " isSystemLanguageDataLoaded="
0x5a8b8  ldloca.s 4
0x5a8ba  call     instance string [mscorlib]System.Boolean::ToString()
0x5a8bf  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x5a8c4  ldarg.3
0x5a8c5  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x5a8ca  dup
0x5a8cb  starg.s  3
0x5a8cd  stloc.s  6
0x5a8cf  ldnull
0x5a8d0  stloc.s  7
0x5a8d2  ldloc.3
0x5a8d3  ldloc.s  4
0x5a8d5  and
0x5a8d6  brfalse.s loc_5A8E4
0x5a8d8  ldarg.0
0x5a8d9  ldloc.0
0x5a8da  ldloc.2
0x5a8db  call     instance class Microsoft.Crm.Metadata.MetadataContainer Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::GetSystemDataByBuildNumberAndLCID(string organizationBuildNumber, int32 lcid)
0x5a8e0  stloc.s  7
0x5a8e2  br.s     loc_5A8F9
0x5a8e4  ldloc.3
0x5a8e5  brfalse.s loc_5A8F2
0x5a8e7  ldarg.0
0x5a8e8  ldloc.0
0x5a8e9  call     instance class Microsoft.Crm.Metadata.MetadataContainer Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::CreateLCIDSpecificMetadataContainer(string organizationBuildNumber)
0x5a8ee  stloc.s  7
0x5a8f0  br.s     loc_5A8F9
0x5a8f2  newobj   instance void Microsoft.Crm.Metadata.MetadataContainer::.ctor()
0x5a8f7  stloc.s  7
0x5a8f9  newobj   instance void Microsoft.Crm.Metadata.MetadataContainer::.ctor()
0x5a8fe  stloc.s  8
0x5a900  ldarg.0
0x5a901  call     instance class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg> Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::BuildTableFillProperties()
0x5a906  stloc.s  9
0x5a908  ldarg.0
0x5a909  ldarg.2
0x5a90a  ldloc.s  9
0x5a90c  ldarg.3
0x5a90d  call     instance void Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::IdentifyCollectionsCount(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg> fillProperties, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5a912  ldarg.0
0x5a913  ldloc.3
0x5a914  ldloc.s  4
0x5a916  ldarg.2
0x5a917  ldloc.s  7
0x5a919  ldloc.s  8
0x5a91b  ldloc.s  9
0x5a91d  ldarg.3
0x5a91e  call     instance void Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::LoadContainerData(bool isSystemDataLoaded, bool isSystemLanguageDataLoaded, class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class Microsoft.Crm.Metadata.MetadataContainer systemContainer, class Microsoft.Crm.Metadata.MetadataContainer aggregateContainer, class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg> fillProperties, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5a923  ldarg.0
0x5a924  ldloc.s  8
0x5a926  ldarg.2
0x5a927  ldarg.3
0x5a928  call     instance void Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::LoadOrgSettings(class Microsoft.Crm.Metadata.IMetadataContainer container, class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5a92d  ldloc.s  8
0x5a92f  ldarg.0
0x5a930  ldarg.2
0x5a931  ldarg.3
0x5a932  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>> Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::RetrieveOrganizationSpecificTimestamps(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5a937  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::set_MetadataTimestamps(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>> value)
0x5a93c  ldloc.3
0x5a93d  brtrue.s loc_5A954
0x5a93f  ldarg.0
0x5a940  ldloc.s  7
0x5a942  ldarg.0
0x5a943  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_OrganizationContext()
0x5a948  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5a94d  ldloc.0
0x5a94e  ldloc.2
0x5a94f  call     instance void Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::SetSystemDataByBuildNumberAndLCID(class Microsoft.Crm.Metadata.MetadataContainer systemContainer, valuetype [mscorlib]System.Guid organizationId, string organizationBuildNumber, int32 lcid)
0x5a954  ldloc.s  8
0x5a956  stloc.s  0xA
0x5a958  leave.s  loc_5A966
0x5a95a  ldloc.s  6
0x5a95c  brfalse.s loc_5A965
0x5a95e  ldloc.s  6
0x5a960  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a965  endfinally
0x5a966  ldloc.s  0xA
0x5a968  ret
```
