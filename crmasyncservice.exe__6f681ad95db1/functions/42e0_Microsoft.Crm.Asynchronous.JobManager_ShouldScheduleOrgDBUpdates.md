# Microsoft.Crm.Asynchronous.JobManager::ShouldScheduleOrgDBUpdates

- ea: `0x42e0`
- end: `0x4314`
- name: `Microsoft.Crm.Asynchronous.JobManager::ShouldScheduleOrgDBUpdates`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3410`

## callees

- `0x42e0`

## string_xrefs

- `0x42fe`: `Failed to identify if Org DB updates should be scheduled. Defaulting to true.`

## pseudocode

```c

```

## disassembly

```asm
0x42e0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x42e5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x42ea  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_DBUpdateScheduling()
0x42ef  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsNonOrgFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail)
0x42f4  stloc.0
0x42f5  leave.s  loc_4312
0x42f7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x42fc  ldc.i4.s 0x15
0x42fe  ldstr    aFailedToIdenti_0// "Failed to identify if Org DB updates sh"...
0x4303  ldc.i4.0
0x4304  newarr   [mscorlib]System.Object
0x4309  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x430e  leave.s  loc_4310
0x4310  ldc.i4.1
0x4311  ret
0x4312  ldloc.0
0x4313  ret
```
