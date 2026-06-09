# Microsoft.Crm.CustomMetricNames::.cctor

- ea: `0x3ca60`
- end: `0x3caed`
- name: `Microsoft.Crm.CustomMetricNames::.cctor`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x3ca60`: `LocatorCacheSyncStart`
- `0x3ca6a`: `LocatorCacheDataLoad`
- `0x3ca74`: `LocatorCacheSyncSuccess`
- `0x3ca7e`: `LocatorCacheSyncFailure`
- `0x3ca88`: `LocatorCacheRemoveEntry`
- `0x3ca92`: `ConfigLocatorServiceRetrieveById`
- `0x3ca9c`: `ServerLocatorServiceRetrieveById`
- `0x3caa6`: `ServerLocatorServiceRetrieve`
- `0x3cab0`: `ServerLocatorServiceRetrieveTable`
- `0x3caba`: `ServerLocatorServiceRetrieveSingleRow`
- `0x3cac4`: `ServerLocatorServiceRetrieveFromCache`
- `0x3cace`: `ConfigDBExecuteReader`
- `0x3cad8`: `ConfigDBExecuteScalar`
- `0x3cae2`: `ConfigDBExecuteNonQuery`

## pseudocode

```c

```

## disassembly

```asm
0x3ca60  ldstr    aLocatorcachesy// "LocatorCacheSyncStart"
0x3ca65  stsfld   string Microsoft.Crm.CustomMetricNames::LocatorCacheSyncStart
0x3ca6a  ldstr    aLocatorcacheda// "LocatorCacheDataLoad"
0x3ca6f  stsfld   string Microsoft.Crm.CustomMetricNames::LocatorCacheDataLoad
0x3ca74  ldstr    aLocatorcachesy_0// "LocatorCacheSyncSuccess"
0x3ca79  stsfld   string Microsoft.Crm.CustomMetricNames::LocatorCacheSyncSuccess
0x3ca7e  ldstr    aLocatorcachesy_1// "LocatorCacheSyncFailure"
0x3ca83  stsfld   string Microsoft.Crm.CustomMetricNames::LocatorCacheSyncFailure
0x3ca88  ldstr    aLocatorcachere// "LocatorCacheRemoveEntry"
0x3ca8d  stsfld   string Microsoft.Crm.CustomMetricNames::LocatorCacheRemoveEntry
0x3ca92  ldstr    aConfiglocators// "ConfigLocatorServiceRetrieveById"
0x3ca97  stsfld   string Microsoft.Crm.CustomMetricNames::ConfigLocatorServiceRetrieveById
0x3ca9c  ldstr    aServerlocators_0// "ServerLocatorServiceRetrieveById"
0x3caa1  stsfld   string Microsoft.Crm.CustomMetricNames::ServerLocatorServiceRetrieveById
0x3caa6  ldstr    aServerlocators_1// "ServerLocatorServiceRetrieve"
0x3caab  stsfld   string Microsoft.Crm.CustomMetricNames::ServerLocatorServiceRetrieve
0x3cab0  ldstr    aServerlocators_2// "ServerLocatorServiceRetrieveTable"
0x3cab5  stsfld   string Microsoft.Crm.CustomMetricNames::ServerLocatorServiceRetrieveTable
0x3caba  ldstr    aServerlocators_3// "ServerLocatorServiceRetrieveSingleRow"
0x3cabf  stsfld   string Microsoft.Crm.CustomMetricNames::ServerLocatorServiceRetrieveSingleRow
0x3cac4  ldstr    aServerlocators_4// "ServerLocatorServiceRetrieveFromCache"
0x3cac9  stsfld   string Microsoft.Crm.CustomMetricNames::ServerLocatorServiceRetrieveFromCache
0x3cace  ldstr    aConfigdbexecut// "ConfigDBExecuteReader"
0x3cad3  stsfld   string Microsoft.Crm.CustomMetricNames::ConfigDBExecuteReader
0x3cad8  ldstr    aConfigdbexecut_0// "ConfigDBExecuteScalar"
0x3cadd  stsfld   string Microsoft.Crm.CustomMetricNames::ConfigDBExecuteScalar
0x3cae2  ldstr    aConfigdbexecut_1// "ConfigDBExecuteNonQuery"
0x3cae7  stsfld   string Microsoft.Crm.CustomMetricNames::ConfigDBExecuteNonQuery
0x3caec  ret
```
