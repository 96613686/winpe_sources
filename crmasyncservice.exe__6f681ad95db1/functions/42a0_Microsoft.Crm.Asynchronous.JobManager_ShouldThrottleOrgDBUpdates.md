# Microsoft.Crm.Asynchronous.JobManager::ShouldThrottleOrgDBUpdates

- ea: `0x42a0`
- end: `0x42d4`
- name: `Microsoft.Crm.Asynchronous.JobManager::ShouldThrottleOrgDBUpdates`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x33a0`
- `0x3410`

## callees

- `0x42a0`

## string_xrefs

- `0x42be`: `Failed to identify if Org DB updates should be throttled. Defaulting to true.`

## pseudocode

```c

```

## disassembly

```asm
0x42a0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x42a5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x42aa  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_DBUpdateThrottling()
0x42af  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsNonOrgFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail)
0x42b4  stloc.0
0x42b5  leave.s  loc_42D2
0x42b7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x42bc  ldc.i4.s 0x15
0x42be  ldstr    aFailedToIdenti// "Failed to identify if Org DB updates sh"...
0x42c3  ldc.i4.0
0x42c4  newarr   [mscorlib]System.Object
0x42c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x42ce  leave.s  loc_42D0
0x42d0  ldc.i4.1
0x42d1  ret
0x42d2  ldloc.0
0x42d3  ret
```
