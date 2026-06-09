# Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetGeoConnectionStringWithReadOnlyCheck

- ea: `0x4a8c0`
- end: `0x4a93e`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetGeoConnectionStringWithReadOnlyCheck`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4a840`

## callees

- `0x1840`
- `0x1f80`
- `0x4640`
- `0x4a860`
- `0x4a8c0`
- `0x4a940`

## string_xrefs

- `0x4a8e7`: `GeoReadOnlyModeEnabled`
- `0x4a915`: `GeoReadOnlyModeReplica`

## pseudocode

```c

```

## disassembly

```asm
0x4a8c0  ldc.i4.0
0x4a8c1  call     string Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetConnectionString(bool removeProvider)
0x4a8c6  stloc.0
0x4a8c7  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x4a8cc  ldc.i4.2
0x4a8cd  bne.un.s loc_4A93C
0x4a8cf  call     string Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetSiteConnectionStringFromRegistry()
0x4a8d4  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4a8d9  brtrue.s loc_4A93C
0x4a8db  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x4a8e0  brfalse.s loc_4A8F4
0x4a8e2  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4a8e7  ldstr    aGeoreadonlymod// "GeoReadOnlyModeEnabled"
0x4a8ec  ldc.i4.0
0x4a8ed  callvirt T0x2B000079
0x4a8f2  br.s     loc_4A8FD
0x4a8f4  ldloca.s 2
0x4a8f6  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x4a8fc  ldloc.2
0x4a8fd  stloc.1
0x4a8fe  ldloca.s 1
0x4a900  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4a905  brfalse.s loc_4A93C
0x4a907  ldloca.s 1
0x4a909  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x4a90e  brfalse.s loc_4A93C
0x4a910  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4a915  ldstr    aGeoreadonlymod_0// "GeoReadOnlyModeReplica"
0x4a91a  ldc.i4.0
0x4a91b  callvirt T0x2B000034
0x4a920  stloc.3
0x4a921  ldloc.3
0x4a922  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4a927  brtrue.s loc_4A93C
0x4a929  ldloc.0
0x4a92a  newobj   instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::.ctor(string)
0x4a92f  dup
0x4a930  ldloc.3
0x4a931  callvirt instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::set_DataSource(string)
0x4a936  callvirt instance string [System.Data]System.Data.Common.DbConnectionStringBuilder::get_ConnectionString()
0x4a93b  stloc.0
0x4a93c  ldloc.0
0x4a93d  ret
```
