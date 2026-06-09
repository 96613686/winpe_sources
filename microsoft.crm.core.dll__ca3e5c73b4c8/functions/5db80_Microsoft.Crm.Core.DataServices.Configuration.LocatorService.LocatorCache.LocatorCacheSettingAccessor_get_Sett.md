# Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::get_Settings

- ea: `0x5db80`
- end: `0x5dc96`
- name: `Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::get_Settings`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x69d0`

## callees

- `0x1eaa0`
- `0x1f510`
- `0x336c0`
- `0x5db80`
- `0x5dd30`

## string_xrefs

- `0x5db86`: `LocatorCacheSyncEnabled-`
- `0x5dba5`: `LocatorCacheSyncEnabled`
- `0x5dc03`: `LocatorCacheSyncEnabled`
- `0x5dc40`: `LocatorCacheSyncEnabled`
- `0x5dc7a`: `LocatorCacheSyncEnabled`
- `0x5dbee`: `Error while parsing {0} object from registry key '{1}' for service named '{2}': {3}`
- `0x5dbfb`: `LocatorCacheSettings`
- `0x5dc38`: `LocatorCacheSettings`
- `0x5dc72`: `LocatorCacheSettings`
- `0x5dc2b`: `One or more values in the {0} object from registry key '{1}' for service named '{2}' are invalid: {3}`
- `0x5dc65`: `Could not find {0} value registry key '{1}' for service named '{2}'`

## pseudocode

```c

```

## disassembly

```asm
0x5db80  ldarg.0
0x5db81  ldfld    class Microsoft.Crm.IRegistryDataProvider Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::_registryDataProvider
0x5db86  ldstr    aLocatorcachesy_2// "LocatorCacheSyncEnabled-"
0x5db8b  ldarg.0
0x5db8c  ldfld    string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::_serviceIdentifier
0x5db91  call     string [mscorlib]System.String::Concat(string, string)
0x5db96  callvirt instance object Microsoft.Crm.IRegistryDataProvider::GetValue(string key)
0x5db9b  dup
0x5db9c  brtrue.s loc_5DBAF
0x5db9e  pop
0x5db9f  ldarg.0
0x5dba0  ldfld    class Microsoft.Crm.IRegistryDataProvider Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::_registryDataProvider
0x5dba5  ldstr    aLocatorcachesy_3// "LocatorCacheSyncEnabled"
0x5dbaa  callvirt instance object Microsoft.Crm.IRegistryDataProvider::GetValue(string key)
0x5dbaf  stloc.0
0x5dbb0  ldloc.0
0x5dbb1  isinst   [mscorlib]System.String
0x5dbb6  brfalse  loc_5DC5F
0x5dbbb  ldloc.0
0x5dbbc  castclass [mscorlib]System.String
0x5dbc1  call     T0x2B000106
0x5dbc6  dup
0x5dbc7  callvirt instance int32 Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings::get_RefreshIntervalInSec()
0x5dbcc  ldc.i4.0
0x5dbcd  bgt.s    loc_5DBDF
0x5dbcf  ldstr    aArgumentMustBe// "Argument must be greater than zero."
0x5dbd4  ldstr    aRefreshinterva// "RefreshIntervalInSec"
0x5dbd9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x5dbde  throw
0x5dbdf  stloc.1
0x5dbe0  leave    loc_5DC94
0x5dbe5  stloc.2
0x5dbe6  ldloc.2
0x5dbe7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5dbec  ldc.i4.s 0x14
0x5dbee  ldstr    aErrorWhilePars// "Error while parsing {0} object from reg"...
0x5dbf3  ldc.i4.4
0x5dbf4  newarr   [mscorlib]System.Object
0x5dbf9  dup
0x5dbfa  ldc.i4.0
0x5dbfb  ldstr    aLocatorcachese// "LocatorCacheSettings"
0x5dc00  stelem.ref
0x5dc01  dup
0x5dc02  ldc.i4.1
0x5dc03  ldstr    aLocatorcachesy_3// "LocatorCacheSyncEnabled"
0x5dc08  stelem.ref
0x5dc09  dup
0x5dc0a  ldc.i4.2
0x5dc0b  ldarg.0
0x5dc0c  ldfld    string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::_serviceIdentifier
0x5dc11  stelem.ref
0x5dc12  dup
0x5dc13  ldc.i4.3
0x5dc14  ldloc.2
0x5dc15  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5dc1a  stelem.ref
0x5dc1b  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5dc20  leave.s  loc_5DC8E
0x5dc22  stloc.3
0x5dc23  ldloc.3
0x5dc24  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5dc29  ldc.i4.s 0x14
0x5dc2b  ldstr    aOneOrMoreValue// "One or more values in the {0} object fr"...
0x5dc30  ldc.i4.4
0x5dc31  newarr   [mscorlib]System.Object
0x5dc36  dup
0x5dc37  ldc.i4.0
0x5dc38  ldstr    aLocatorcachese// "LocatorCacheSettings"
0x5dc3d  stelem.ref
0x5dc3e  dup
0x5dc3f  ldc.i4.1
0x5dc40  ldstr    aLocatorcachesy_3// "LocatorCacheSyncEnabled"
0x5dc45  stelem.ref
0x5dc46  dup
0x5dc47  ldc.i4.2
0x5dc48  ldarg.0
0x5dc49  ldfld    string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::_serviceIdentifier
0x5dc4e  stelem.ref
0x5dc4f  dup
0x5dc50  ldc.i4.3
0x5dc51  ldloc.3
0x5dc52  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5dc57  stelem.ref
0x5dc58  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5dc5d  leave.s  loc_5DC8E
0x5dc5f  ldarg.0
0x5dc60  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::_logger
0x5dc65  ldstr    aCouldNotFind0V// "Could not find {0} value registry key '"...
0x5dc6a  ldc.i4.3
0x5dc6b  newarr   [mscorlib]System.Object
0x5dc70  dup
0x5dc71  ldc.i4.0
0x5dc72  ldstr    aLocatorcachese// "LocatorCacheSettings"
0x5dc77  stelem.ref
0x5dc78  dup
0x5dc79  ldc.i4.1
0x5dc7a  ldstr    aLocatorcachesy_3// "LocatorCacheSyncEnabled"
0x5dc7f  stelem.ref
0x5dc80  dup
0x5dc81  ldc.i4.2
0x5dc82  ldarg.0
0x5dc83  ldfld    string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::_serviceIdentifier
0x5dc88  stelem.ref
0x5dc89  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5dc8e  ldsfld   class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::DefaultLocatorCacheSettings
0x5dc93  ret
0x5dc94  ldloc.1
0x5dc95  ret
```
