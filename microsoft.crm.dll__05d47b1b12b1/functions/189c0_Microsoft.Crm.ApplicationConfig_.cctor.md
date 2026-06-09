# Microsoft.Crm.ApplicationConfig::.cctor

- ea: `0x189c0`
- end: `0x18b29`
- name: `Microsoft.Crm.ApplicationConfig::.cctor`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x189c0`: `UserRootPath`
- `0x18a15`: `IgnoreTokenCheck`
- `0x18a1a`: `IgnoreTokenCheck`
- `0x18a51`: `SchedulingCacheTimeout`
- `0x18a56`: `SchedulingEngine.CacheTimeout`
- `0x18a6a`: `SchedulingEngine.NumberOfTimeSlotsToConsider`
- `0x18ab5`: `SchedulingNumOfResInService`
- `0x18aba`: `SchedulingEngine.NumberOfResourcesInService`
- `0x18af1`: `SchedulingCacheConfiguration`
- `0x18af6`: `SchedulingEngine.CacheConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x189c0  ldstr    aUserrootpath// "UserRootPath"
0x189c5  stsfld   string Microsoft.Crm.ApplicationConfig::_userRootPath
0x189ca  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x189cf  stsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x189d4  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x189d9  ldstr    aAllowrdlupload// "AllowRDLUpload"
0x189de  ldstr    aAllowrdlupload// "AllowRDLUpload"
0x189e3  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x189e8  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x189ed  ldstr    aAlternateexpor// "AlternateExportSqlServerName"
0x189f2  ldstr    aAlternateexpor// "AlternateExportSqlServerName"
0x189f7  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x189fc  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18a01  ldstr    aUsewebqueryfor// "UseWebQueryForLiveExport"
0x18a06  ldstr    aUsewebqueryfor// "UseWebQueryForLiveExport"
0x18a0b  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18a10  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18a15  ldstr    aIgnoretokenche// "IgnoreTokenCheck"
0x18a1a  ldstr    aIgnoretokenche// "IgnoreTokenCheck"
0x18a1f  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18a24  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18a29  ldstr    aIisallowcachin// "IIsAllowCaching"
0x18a2e  ldstr    aIisallowcachin// "IIsAllowCaching"
0x18a33  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18a38  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18a3d  ldstr    aParametersuffi// "ParameterSufficiency"
0x18a42  ldstr    aParametersuffi// "ParameterSufficiency"
0x18a47  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18a4c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18a51  ldstr    aSchedulingcach// "SchedulingCacheTimeout"
0x18a56  ldstr    aSchedulingengi// "SchedulingEngine.CacheTimeout"
0x18a5b  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18a60  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18a65  ldstr    aSchedulingnumo// "SchedulingNumOfTimeSlots"
0x18a6a  ldstr    aSchedulingengi_0// "SchedulingEngine.NumberOfTimeSlotsToCon"...
0x18a6f  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18a74  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18a79  ldstr    aSchedulingnumo_0// "SchedulingNumOfProposal"
0x18a7e  ldstr    aSchedulingengi_1// "SchedulingEngine.NumberOfProposals"
0x18a83  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18a88  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18a8d  ldstr    aSchedulingnumo_1// "SchedulingNumOfRecurrIterations"
0x18a92  ldstr    aSchedulingengi_2// "SchedulingEngine.NumberOfRecurrenceIter"...
0x18a97  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18a9c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18aa1  ldstr    aSchedulingnumo_2// "SchedulingNumOfScndToSearch"
0x18aa6  ldstr    aSchedulingengi_3// "SchedulingEngine.NumberOfSecondsToSearc"...
0x18aab  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18ab0  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18ab5  ldstr    aSchedulingnumo_3// "SchedulingNumOfResInService"
0x18aba  ldstr    aSchedulingengi_4// "SchedulingEngine.NumberOfResourcesInSer"...
0x18abf  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18ac4  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18ac9  ldstr    aSchedulingnumo_4// "SchedulingNumOfResInActivity"
0x18ace  ldstr    aSchedulingengi_5// "SchedulingEngine.NumberOfResourcesInAct"...
0x18ad3  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18ad8  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18add  ldstr    aSchedulingmaxr// "SchedulingMaxResSpecTreeDepth"
0x18ae2  ldstr    aSchedulingengi_6// "SchedulingEngine.MaxResourceSpecTreeDep"...
0x18ae7  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18aec  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18af1  ldstr    aSchedulingcach_0// "SchedulingCacheConfiguration"
0x18af6  ldstr    aSchedulingengi_7// "SchedulingEngine.CacheConfiguration"
0x18afb  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18b00  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18b05  ldstr    aSrsurl// "SrsUrl"
0x18b0a  ldstr    aSrsurl// "SrsUrl"
0x18b0f  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18b14  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Crm.ApplicationConfig::_mapPropertyName
0x18b19  ldstr    aHelpcontentser// "HelpContentServerUrl"
0x18b1e  ldstr    aHelpcontentser// "HelpContentServerUrl"
0x18b23  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x18b28  ret
```
