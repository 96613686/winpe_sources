# Microsoft.Crm.SearchUtility::GetSearchInfo

- ea: `0x10`
- end: `0x5a`
- name: `Microsoft.Crm.SearchUtility::GetSearchInfo`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10`

## string_xrefs

- `0x15`: `globalsearchconfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x10  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.GlobalSearchConfigurationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.GlobalSearchConfigurationCache::Instance()
0x15  ldstr    aGlobalsearchco// "globalsearchconfiguration"
0x1a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurationCollection>::LookupEntry(void, var<u1>)
0x24  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations>::GetEnumerator()
0x29  stloc.0
0x2a  br.s     loc_42
0x2c  ldloc.0
0x2d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations>::get_Current()
0x32  stloc.1
0x33  ldloc.1
0x34  brfalse.s loc_42
0x36  ldloc.1
0x37  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations::get_SearchProviderName()
0x3c  brfalse.s loc_42
0x3e  ldloc.1
0x3f  stloc.2
0x40  leave.s  loc_58
0x42  ldloc.0
0x43  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x48  brtrue.s loc_2C
0x4a  leave.s  loc_56
0x4c  ldloc.0
0x4d  brfalse.s loc_55
0x4f  ldloc.0
0x50  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55  endfinally
0x56  ldnull
0x57  ret
0x58  ldloc.2
0x59  ret
```
