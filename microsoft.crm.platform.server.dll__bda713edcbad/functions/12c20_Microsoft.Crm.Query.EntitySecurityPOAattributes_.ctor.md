# Microsoft.Crm.Query.EntitySecurityPOAattributes::.ctor

- ea: `0x12c20`
- end: `0x12d89`
- name: `Microsoft.Crm.Query.EntitySecurityPOAattributes::.ctor`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x74870`

## callees

- `0x170`
- `0x180`
- `0x190`
- `0x1a0`
- `0x1b0`
- `0x12c20`
- `0x66b70`
- `0x66ff0`
- `0x68390`
- `0x81070`
- `0x810a0`

## string_xrefs

- `0x12c7a`: `EntitySecurityPOAattributesContext`
- `0x12c88`: `EntitySecurityPOAattributesContext`

## pseudocode

```c

```

## disassembly

```asm
0x12c20  ldarg.0
0x12c21  call     bool EntitySecurityPOAdefaults::get_DefaultForceseekEnabled()
0x12c26  stfld    bool Microsoft.Crm.Query.EntitySecurityPOAattributes::forceseekEnabled
0x12c2b  ldarg.0
0x12c2c  call     int32 EntitySecurityPOAdefaults::get_DefaultForceseekMaxRecordCount()
0x12c31  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::forceseekMaxRecordCount
0x12c36  ldarg.0
0x12c37  call     int32 EntitySecurityPOAdefaults::get_DefaultForceseekMaxRecordPercent()
0x12c3c  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::forceseekMaxRecordPercent
0x12c41  ldarg.0
0x12c42  call     int32 EntitySecurityPOAdefaults::get_DefaultQueryMinBucketThreshold()
0x12c47  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::queryMinBucketThreshold
0x12c4c  ldarg.0
0x12c4d  call     int32 EntitySecurityPOAdefaults::get_DefaultQueryBucketCount()
0x12c52  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::queryBucketCount
0x12c57  ldarg.0
0x12c58  call     instance void [mscorlib]System.Object::.ctor()
0x12c5d  call     bool [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::get_IsOffline()
0x12c62  brtrue.s loc_12C6B
0x12c64  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x12c69  brfalse.s loc_12C6C
0x12c6b  ret
0x12c6c  ldarg.1
0x12c6d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x12c72  brfalse.s loc_12C87
0x12c74  ldarg.1
0x12c75  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x12c7a  ldstr    aEntitysecurity// "EntitySecurityPOAattributesContext"
0x12c7f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x12c84  brfalse.s loc_12C87
0x12c86  ret
0x12c87  ldarg.1
0x12c88  ldstr    aEntitysecurity// "EntitySecurityPOAattributesContext"
0x12c8d  ldc.i4.1
0x12c8e  box      [mscorlib]System.Boolean
0x12c93  newobj   instance void Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context, string key, object value)
0x12c98  stloc.0
0x12c99  ldarg.0
0x12c9a  ldstr    aRetrievemultip// "RetrieveMultipleSecQryFORCESEEKHintEnab"...
0x12c9f  call     bool EntitySecurityPOAdefaults::get_DefaultForceseekEnabled()
0x12ca4  ldarg.1
0x12ca5  call     bool Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSettingWithOrgOverride(string settingName, bool defaultValue, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x12caa  stfld    bool Microsoft.Crm.Query.EntitySecurityPOAattributes::forceseekEnabled
0x12caf  ldarg.0
0x12cb0  ldstr    aRetrievemultip_0// "RetrieveMultipleSecQryFORCESEEKMaxRecor"...
0x12cb5  call     int32 EntitySecurityPOAdefaults::get_DefaultForceseekMaxRecordCount()
0x12cba  ldarg.1
0x12cbb  call     int32 Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSettingWithOrgOverride(string settingName, int32 defaultValue, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x12cc0  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::forceseekMaxRecordCount
0x12cc5  ldarg.0
0x12cc6  ldstr    aRetrievemultip_1// "RetrieveMultipleSecQryFORCESEEKMaxRecor"...
0x12ccb  call     int32 EntitySecurityPOAdefaults::get_DefaultForceseekMaxRecordPercent()
0x12cd0  ldarg.1
0x12cd1  call     int32 Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSettingWithOrgOverride(string settingName, int32 defaultValue, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x12cd6  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::forceseekMaxRecordPercent
0x12cdb  ldarg.0
0x12cdc  ldstr    aRetrievemultip_2// "RetrieveMultipleSecQryMinBucketThreshol"...
0x12ce1  call     int32 EntitySecurityPOAdefaults::get_DefaultQueryMinBucketThreshold()
0x12ce6  ldarg.1
0x12ce7  call     int32 Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSettingWithOrgOverride(string settingName, int32 defaultValue, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x12cec  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::queryMinBucketThreshold
0x12cf1  ldarg.0
0x12cf2  ldstr    aRetrievemultip_3// "RetrieveMultipleSecQryBucketCount"
0x12cf7  call     int32 EntitySecurityPOAdefaults::get_DefaultQueryBucketCount()
0x12cfc  ldarg.1
0x12cfd  call     int32 Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSettingWithOrgOverride(string settingName, int32 defaultValue, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x12d02  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::queryBucketCount
0x12d07  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotCache::Instance()
0x12d0c  ldarg.1
0x12d0d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_UserId()
0x12d12  ldarg.1
0x12d13  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotDictionary>::LookupEntry(void, var<u1>)
0x12d18  stloc.1
0x12d19  ldloc.1
0x12d1a  brfalse.s loc_12D7C
0x12d1c  ldloc.1
0x12d1d  ldarg.2
0x12d1e  ldloca.s 2
0x12d20  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue>::TryGetValue(var<u1>, !!T0)
0x12d25  brfalse.s loc_12D7C
0x12d27  ldarg.0
0x12d28  ldloca.s 2
0x12d2a  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_ShareCount()
0x12d2f  stfld    int64 Microsoft.Crm.Query.EntitySecurityPOAattributes::poaShareCount
0x12d34  ldarg.0
0x12d35  ldloca.s 2
0x12d37  call     instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_ShareCountPercentOfTotalRows()
0x12d3c  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::poaShareCountPercent
0x12d41  ldarg.0
0x12d42  ldloca.s 2
0x12d44  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_RecordCountForOwnerID()
0x12d49  stfld    int64 Microsoft.Crm.Query.EntitySecurityPOAattributes::poaRecordCountForOwnerID
0x12d4e  ldarg.0
0x12d4f  ldloca.s 2
0x12d51  call     instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_RecordCountForOwnerIDPercentOfTotalRows()
0x12d56  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::poaRecordCountForOwnerIDPercent
0x12d5b  ldarg.0
0x12d5c  ldloca.s 2
0x12d5e  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_RecordCountForOwningBU()
0x12d63  stfld    int64 Microsoft.Crm.Query.EntitySecurityPOAattributes::poaRecordCountForOwningBU
0x12d68  ldarg.0
0x12d69  ldloca.s 2
0x12d6b  call     instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_RecordCountForOwningBUPercentOfTotalRows()
0x12d70  stfld    int32 Microsoft.Crm.Query.EntitySecurityPOAattributes::poaRecordCountForOwningBUPercent
0x12d75  ldarg.0
0x12d76  ldc.i4.1
0x12d77  stfld    bool Microsoft.Crm.Query.EntitySecurityPOAattributes::settingInitialized
0x12d7c  leave.s  loc_12D88
0x12d7e  ldloc.0
0x12d7f  brfalse.s loc_12D87
0x12d81  ldloc.0
0x12d82  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12d87  endfinally
0x12d88  ret
```
