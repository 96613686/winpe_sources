# Microsoft.Crm.Asynchronous.Rollups.RollupJob::.ctor

- ea: `0xddf0`
- end: `0xdee0`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJob::.ctor`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xd780`

## callees

- `0xdc30`
- `0xdc40`
- `0xdc50`
- `0xdc70`
- `0xdc90`
- `0xdcb0`
- `0xdcd0`
- `0xdcf0`
- `0xdd10`
- `0xdd30`
- `0xdde0`
- `0xe130`

## string_xrefs

- `0xde15`: `rolluppropertiesid`
- `0xdeaf`: `recordcreatedon`

## pseudocode

```c

```

## disassembly

```asm
0xddf0  ldarg.0
0xddf1  call     instance void [mscorlib]System.Object::.ctor()
0xddf6  ldarg.0
0xddf7  ldarg.2
0xddf8  stfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier Microsoft.Crm.Asynchronous.Rollups.RollupJob::_jobModifier
0xddfd  ldarg.0
0xddfe  ldarg.1
0xddff  ldstr    aRollupjobid// "rollupjobid"
0xde04  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0xde09  unbox.any [mscorlib]System.Int64
0xde0e  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_RollupJobId(int64 value)
0xde13  ldarg.0
0xde14  ldarg.1
0xde15  ldstr    aRollupproperti_1// "rolluppropertiesid"
0xde1a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0xde1f  unbox.any [mscorlib]System.Guid
0xde24  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_RollupPropertiesId(valuetype [mscorlib]System.Guid value)
0xde29  ldarg.0
0xde2a  ldarg.1
0xde2b  ldstr    aRegardingobjec// "regardingobjectid"
0xde30  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0xde35  unbox.any [mscorlib]System.Guid
0xde3a  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_RegardingObjectId(valuetype [mscorlib]System.Guid value)
0xde3f  ldarg.0
0xde40  ldarg.1
0xde41  ldstr    aRegardingobjec_0// "regardingobjecttypecode"
0xde46  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0xde4b  unbox.any [mscorlib]System.Int32
0xde50  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_RegardingObjectTypeCode(int32 value)
0xde55  ldarg.0
0xde56  ldarg.1
0xde57  ldstr    aSourceentityty_0// "sourceentitytypecode"
0xde5c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0xde61  unbox.any [mscorlib]System.Int32
0xde66  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_SourceEntityTypeCode(int32 value)
0xde6b  ldarg.0
0xde6c  ldarg.1
0xde6d  ldstr    aRetrycount_1// "retrycount"
0xde72  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0xde77  unbox.any [mscorlib]System.Int32
0xde7c  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_RetryCount(int32 value)
0xde81  ldarg.0
0xde82  ldarg.1
0xde83  ldstr    aPostponeuntil// "postponeuntil"
0xde88  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0xde8d  unbox.any [mscorlib]System.DateTime
0xde92  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_PostponeUntil(valuetype [mscorlib]System.DateTime value)
0xde97  ldarg.0
0xde98  ldarg.1
0xde99  ldstr    aDepthprocessed// "depthprocessed"
0xde9e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0xdea3  unbox.any [mscorlib]System.Int32
0xdea8  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_DepthProcessed(int32 value)
0xdead  ldarg.0
0xdeae  ldarg.1
0xdeaf  ldstr    aRecordcreatedo// "recordcreatedon"
0xdeb4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0xdeb9  unbox.any [mscorlib]System.DateTime
0xdebe  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_CreatedOn(valuetype [mscorlib]System.DateTime value)
0xdec3  ldarg.0
0xdec4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RollupPropertiesCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RollupPropertiesCache::Instance()
0xdec9  ldarg.0
0xdeca  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupPropertiesId()
0xdecf  ldarg.2
0xded0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::get_OrganizationContext()
0xded5  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData>::TryLookupEntry(void, var<u1>)
0xdeda  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_RollupProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData value)
0xdedf  ret
```
