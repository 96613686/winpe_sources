# Microsoft.Crm.Caching.CacheConfiguration::get_CrmCacheDefaultExpirationInterval

- ea: `0x79550`
- end: `0x795b0`
- name: `Microsoft.Crm.Caching.CacheConfiguration::get_CrmCacheDefaultExpirationInterval`
- size: `96`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4bac0`
- `0x79bc0`
- `0x79be0`
- `0x79bf0`
- `0x95140`

## callees

- `0x79550`
- `0x795d0`

## string_xrefs

- `0x7956a`: `CrmCacheExpirationIntervalForWebAppInMinutes`
- `0x79587`: `CrmCacheDefaultExpirationIntervalInMinutes`

## pseudocode

```c

```

## disassembly

```asm
0x79550  call     bool Microsoft.Crm.Caching.CacheConfiguration::get_IsMetadataCacheStorageOnHttpRuntimeEnabled()
0x79555  brfalse.s loc_79582
0x79557  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInAspWorkerProcessContext()
0x7955c  brfalse.s loc_79582
0x7955e  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInScaleGroupApiAppPoolContext()
0x79563  brtrue.s loc_79582
0x79565  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x7956a  ldstr    aCrmcacheexpira// "CrmCacheExpirationIntervalForWebAppInMi"...
0x7956f  ldc.i4   0x168
0x79574  callvirt T0x2B0000BE
0x79579  conv.r8
0x7957a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x7957f  stloc.0
0x79580  leave.s  loc_795AE
0x79582  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x79587  ldstr    aCrmcachedefaul// "CrmCacheDefaultExpirationIntervalInMinu"...
0x7958c  ldc.i4.s 0x14
0x7958e  callvirt T0x2B0000BE
0x79593  conv.r8
0x79594  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x79599  stloc.0
0x7959a  leave.s  loc_795AE
0x7959c  pop
0x7959d  ldc.r8   20.0
0x795a6  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x795ab  stloc.0
0x795ac  leave.s  loc_795AE
0x795ae  ldloc.0
0x795af  ret
```
