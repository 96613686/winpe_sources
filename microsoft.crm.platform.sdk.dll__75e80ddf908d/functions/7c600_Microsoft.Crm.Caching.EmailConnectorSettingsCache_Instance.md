# Microsoft.Crm.Caching.EmailConnectorSettingsCache::Instance

- ea: `0x7c600`
- end: `0x7c65b`
- name: `Microsoft.Crm.Caching.EmailConnectorSettingsCache::Instance`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7c570`
- `0x7c600`

## string_xrefs

- `0x7c607`: `EmailConnectorSettingsCacheLoader only works in server context`
- `0x7c63d`: `Microsoft.Crm.Caching.EmailConnectorSettingsCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x7c600  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x7c605  brfalse.s loc_7C612
0x7c607  ldstr    aEmailconnector_0// "EmailConnectorSettingsCacheLoader only "...
0x7c60c  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x7c611  throw
0x7c612  ldsfld   object Microsoft.Crm.Caching.EmailConnectorSettingsCache::lockObj
0x7c617  stloc.0
0x7c618  ldc.i4.0
0x7c619  stloc.1
0x7c61a  ldloc.0
0x7c61b  ldloca.s 1
0x7c61d  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x7c622  ldsfld   class Microsoft.Crm.Caching.EmailConnectorSettingsCache Microsoft.Crm.Caching.EmailConnectorSettingsCache::instance
0x7c627  brtrue.s loc_7C647
0x7c629  newobj   instance void Microsoft.Crm.Caching.EmailConnectorSettingsCache::.ctor()
0x7c62e  stsfld   class Microsoft.Crm.Caching.EmailConnectorSettingsCache Microsoft.Crm.Caching.EmailConnectorSettingsCache::instance
0x7c633  ldsfld   class Microsoft.Crm.Caching.EmailConnectorSettingsCache Microsoft.Crm.Caching.EmailConnectorSettingsCache::instance
0x7c638  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x7c63d  ldstr    aMicrosoftCrmCa_6// "Microsoft.Crm.Caching.EmailConnectorSet"...
0x7c642  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.EmailConnectorSettings>::SetLoader(string, string)
0x7c647  ldsfld   class Microsoft.Crm.Caching.EmailConnectorSettingsCache Microsoft.Crm.Caching.EmailConnectorSettingsCache::instance
0x7c64c  stloc.2
0x7c64d  leave.s  loc_7C659
0x7c64f  ldloc.1
0x7c650  brfalse.s loc_7C658
0x7c652  ldloc.0
0x7c653  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7c658  endfinally
0x7c659  ldloc.2
0x7c65a  ret
```
