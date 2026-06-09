# Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::ProcessAssignedTask

- ea: `0x70730`
- end: `0x7080a`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::ProcessAssignedTask`
- size: `218`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x64910`
- `0x649b0`
- `0x649e0`
- `0x64a10`
- `0x64ba0`
- `0x64cb0`
- `0x6cdc0`
- `0x6ce20`
- `0x6ce40`

## callees

- `0x70120`
- `0x701d0`
- `0x70330`
- `0x70720`
- `0x70730`

## string_xrefs

- `0x7075e`: `crmtaskassigneduniqueid`
- `0x70770`: `crmtaskassigneduniqueid`
- `0x707aa`: `taskownership`
- `0x707bc`: `taskownership`
- `0x70784`: `crmtaskassigneeuserid`
- `0x70796`: `crmtaskassigneeuserid`

## pseudocode

```c

```

## disassembly

```asm
0x70730  ldarg.0
0x70731  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x70736  ldarg.0
0x70737  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x7073c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x70741  ldarg.0
0x70742  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x70747  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x7074c  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::IsAssignedTaskFeatureEnabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings orgSettings)
0x70751  brtrue.s loc_70755
0x70753  ldc.i4.0
0x70754  ret
0x70755  ldarg.0
0x70756  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x7075b  brtrue.s loc_7076A
0x7075d  ldarg.0
0x7075e  ldstr    aCrmtaskassigne// "crmtaskassigneduniqueid"
0x70763  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x70768  br.s     loc_7077A
0x7076a  ldarg.0
0x7076b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x70770  ldstr    aCrmtaskassigne// "crmtaskassigneduniqueid"
0x70775  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x7077a  stloc.0
0x7077b  ldarg.0
0x7077c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x70781  brtrue.s loc_70790
0x70783  ldarg.0
0x70784  ldstr    aCrmtaskassigne_0// "crmtaskassigneeuserid"
0x70789  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x7078e  br.s     loc_707A0
0x70790  ldarg.0
0x70791  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x70796  ldstr    aCrmtaskassigne_0// "crmtaskassigneeuserid"
0x7079b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x707a0  stloc.1
0x707a1  ldarg.0
0x707a2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x707a7  brtrue.s loc_707B6
0x707a9  ldarg.0
0x707aa  ldstr    aTaskownership// "taskownership"
0x707af  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x707b4  br.s     loc_707C6
0x707b6  ldarg.0
0x707b7  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x707bc  ldstr    aTaskownership// "taskownership"
0x707c1  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x707c6  stloc.2
0x707c7  ldc.i4.0
0x707c8  stloc.3
0x707c9  ldloc.2
0x707ca  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x707cf  brtrue.s loc_707E9
0x707d1  ldtoken  Microsoft.Crm.Asynchronous.EmailConnector.NonCrmTaskOwnership
0x707d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x707db  ldloc.2
0x707dc  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x707e1  unbox.any Microsoft.Crm.Asynchronous.EmailConnector.NonCrmTaskOwnership
0x707e6  stloc.3
0x707e7  br.s     loc_707FB
0x707e9  ldloc.1
0x707ea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x707ef  brfalse.s loc_707FB
0x707f1  ldloc.0
0x707f2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x707f7  brtrue.s loc_707FB
0x707f9  ldc.i4.1
0x707fa  ret
0x707fb  ldloc.3
0x707fc  brtrue.s loc_70806
0x707fe  ldloc.1
0x707ff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x70804  brtrue.s loc_70808
0x70806  ldc.i4.1
0x70807  ret
0x70808  ldc.i4.0
0x70809  ret
```
