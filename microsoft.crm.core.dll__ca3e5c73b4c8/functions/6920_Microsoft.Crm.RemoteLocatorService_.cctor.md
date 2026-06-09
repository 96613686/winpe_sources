# Microsoft.Crm.RemoteLocatorService::.cctor

- ea: `0x6920`
- end: `0x69ac`
- name: `Microsoft.Crm.RemoteLocatorService::.cctor`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6969`: `TraceDirectory`
- `0x6931`: `GeoReadOnlyModeEnabled`
- `0x6929`: `GeoReadOnlyModeReplica`

## pseudocode

```c

```

## disassembly

```asm
0x6920  ldc.i4.s 0xD
0x6922  newarr   [mscorlib]System.String
0x6927  dup
0x6928  ldc.i4.0
0x6929  ldstr    aGeoreadonlymod_0// "GeoReadOnlyModeReplica"
0x692e  stelem.ref
0x692f  dup
0x6930  ldc.i4.1
0x6931  ldstr    aGeoreadonlymod// "GeoReadOnlyModeEnabled"
0x6936  stelem.ref
0x6937  dup
0x6938  ldc.i4.2
0x6939  ldstr    aGeoname// "GeoName"
0x693e  stelem.ref
0x693f  dup
0x6940  ldc.i4.3
0x6941  ldstr    aEnvironmenttyp// "EnvironmentType"
0x6946  stelem.ref
0x6947  dup
0x6948  ldc.i4.4
0x6949  ldstr    aCmamdmaccountn// "CmaMdmAccountName"
0x694e  stelem.ref
0x694f  dup
0x6950  ldc.i4.5
0x6951  ldstr    aTracerefresh// "TraceRefresh"
0x6956  stelem.ref
0x6957  dup
0x6958  ldc.i4.6
0x6959  ldstr    aTraceenabled// "TraceEnabled"
0x695e  stelem.ref
0x695f  dup
0x6960  ldc.i4.7
0x6961  ldstr    aTracecallstack// "TraceCallStack"
0x6966  stelem.ref
0x6967  dup
0x6968  ldc.i4.8
0x6969  ldstr    aTracedirectory// "TraceDirectory"
0x696e  stelem.ref
0x696f  dup
0x6970  ldc.i4.s 9
0x6972  ldstr    aTracebypassorg// "TraceBypassOrganizations"
0x6977  stelem.ref
0x6978  dup
0x6979  ldc.i4.s 0xA
0x697b  ldstr    aTracecategorie// "TraceCategories"
0x6980  stelem.ref
0x6981  dup
0x6982  ldc.i4.s 0xB
0x6984  ldstr    aTracefilesize// "TraceFileSize"
0x6989  stelem.ref
0x698a  dup
0x698b  ldc.i4.s 0xC
0x698d  ldstr    aTraceuseetwonl// "TraceUseEtwOnly"
0x6992  stelem.ref
0x6993  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x6998  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.RemoteLocatorService::SiteSettingToFetchFromSql
0x699d  ldc.r8   15.0
0x69a6  stsfld   float64 Microsoft.Crm.RemoteLocatorService::FCBRefreshInterval
0x69ab  ret
```
