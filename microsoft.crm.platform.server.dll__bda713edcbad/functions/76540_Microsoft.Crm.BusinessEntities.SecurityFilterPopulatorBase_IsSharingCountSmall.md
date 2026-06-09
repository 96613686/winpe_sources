# Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::IsSharingCountSmall

- ea: `0x76540`
- end: `0x7671b`
- name: `Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::IsSharingCountSmall`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x764e0`

## callees

- `0x12d90`
- `0x13020`
- `0x13030`
- `0x13080`
- `0x679e0`
- `0x72ea0`
- `0x76100`
- `0x76540`
- `0x77580`

## string_xrefs

- `0x76580`: `securityQueryDetails`
- `0x7659c`: `securityQueryDetails`
- `0x765b8`: `securityQueryDetails`
- `0x765d4`: `securityQueryDetails`
- `0x765f0`: `securityQueryDetails`
- `0x7660c`: `securityQueryDetails`
- `0x76628`: `securityQueryDetails`
- `0x76644`: `securityQueryDetails`
- `0x76660`: `securityQueryDetails`
- `0x76675`: `securityQueryDetails`

## pseudocode

```c

```

## disassembly

```asm
0x76540  ldarg.3
0x76541  call     int32 Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::RetrieveMultipleSharingCountThreshold(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x76546  stloc.0
0x76547  ldarg.s  4
0x76549  brfalse.s loc_76553
0x7654b  ldarg.s  4
0x7654d  ldc.i4.1
0x7654e  callvirt instance void Microsoft.Crm.Query.EntitySecurityPOAattributes::set_POAShareCountToUseInForceSeek(bool value)
0x76553  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotCache::Instance()
0x76558  ldarg.1
0x76559  ldarg.3
0x7655a  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotDictionary>::LookupEntry(void, var<u1>)
0x7655f  stloc.1
0x76560  ldloc.1
0x76561  brfalse  loc_76719
0x76566  ldloc.1
0x76567  ldarg.2
0x76568  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x7656d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x76572  ldloca.s 2
0x76574  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue>::TryGetValue(var<u1>, !!T0)
0x76579  brfalse  loc_76719
0x7657e  ldarg.3
0x7657f  dup
0x76580  ldstr    aSecurityqueryd// "securityQueryDetails"
0x76585  ldstr    aPoachildusersc// "poaChildUsersCount"
0x7658a  ldloca.s 2
0x7658c  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_ChildUsersCount()
0x76591  box      [mscorlib]System.Int64
0x76596  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x7659b  dup
0x7659c  ldstr    aSecurityqueryd// "securityQueryDetails"
0x765a1  ldstr    aPoateamprincip// "poaTeamPrincipalsCount"
0x765a6  ldloca.s 2
0x765a8  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_TeamPrincipalsCount()
0x765ad  box      [mscorlib]System.Int64
0x765b2  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x765b7  dup
0x765b8  ldstr    aSecurityqueryd// "securityQueryDetails"
0x765bd  ldstr    aPoasharecount// "poaShareCount"
0x765c2  ldloca.s 2
0x765c4  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_ShareCount()
0x765c9  box      [mscorlib]System.Int64
0x765ce  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x765d3  dup
0x765d4  ldstr    aSecurityqueryd// "securityQueryDetails"
0x765d9  ldstr    aPoasharecountp// "poaShareCountPercentOfTotalRows"
0x765de  ldloca.s 2
0x765e0  call     instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_ShareCountPercentOfTotalRows()
0x765e5  box      [mscorlib]System.Int32
0x765ea  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x765ef  dup
0x765f0  ldstr    aSecurityqueryd// "securityQueryDetails"
0x765f5  ldstr    aPoarecordcount// "poaRecordCountForOwnerID"
0x765fa  ldloca.s 2
0x765fc  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_RecordCountForOwnerID()
0x76601  box      [mscorlib]System.Int64
0x76606  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x7660b  dup
0x7660c  ldstr    aSecurityqueryd// "securityQueryDetails"
0x76611  ldstr    aPoarecordcount_0// "poaRecordCountForOwnerIDPercentOfTotalR"...
0x76616  ldloca.s 2
0x76618  call     instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_RecordCountForOwnerIDPercentOfTotalRows()
0x7661d  box      [mscorlib]System.Int32
0x76622  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x76627  dup
0x76628  ldstr    aSecurityqueryd// "securityQueryDetails"
0x7662d  ldstr    aPoarecordcount_1// "poaRecordCountForOwningBU"
0x76632  ldloca.s 2
0x76634  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_RecordCountForOwningBU()
0x76639  box      [mscorlib]System.Int64
0x7663e  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x76643  dup
0x76644  ldstr    aSecurityqueryd// "securityQueryDetails"
0x76649  ldstr    aPoarecordcount_2// "poaRecordCountForOwningBUPercentOfTotal"...
0x7664e  ldloca.s 2
0x76650  call     instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_RecordCountForOwningBUPercentOfTotalRows()
0x76655  box      [mscorlib]System.Int32
0x7665a  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x7665f  dup
0x76660  ldstr    aSecurityqueryd// "securityQueryDetails"
0x76665  ldstr    aPrincipalid_0// "principalId"
0x7666a  ldarg.1
0x7666b  box      [mscorlib]System.Guid
0x76670  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x76675  ldstr    aSecurityqueryd// "securityQueryDetails"
0x7667a  ldstr    aObjecttypecode_83// "objectTypeCode"
0x7667f  ldarg.2
0x76680  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x76685  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7668a  box      [mscorlib]System.Int32
0x7668f  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x76694  ldarg.s  4
0x76696  brfalse.s loc_766B3
0x76698  ldarg.s  4
0x7669a  callvirt instance bool Microsoft.Crm.Query.EntitySecurityPOAattributes::get_SettingInitialized()
0x7669f  brfalse.s loc_766B3
0x766a1  ldarg.s  4
0x766a3  callvirt instance bool Microsoft.Crm.Query.EntitySecurityPOAattributes::get_ForceSeekEnabled()
0x766a8  brfalse.s loc_766B3
0x766aa  ldarg.s  4
0x766ac  ldc.i4.0
0x766ad  callvirt instance bool Microsoft.Crm.Query.EntitySecurityPOAattributes::IsRecordCountSmallForForceSeek(valuetype SecurityTypeAttribute securityTypeAttribute)
0x766b2  ret
0x766b3  ldloca.s 2
0x766b5  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_ShareCount()
0x766ba  ldloc.0
0x766bb  conv.i8
0x766bc  ble.s    loc_766C0
0x766be  ldc.i4.0
0x766bf  ret
0x766c0  ldarg.2
0x766c1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x766c6  call     bool Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::IsEntitySupportSharingToOrganization(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x766cb  brfalse.s loc_76719
0x766cd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotCache::Instance()
0x766d2  ldarg.3
0x766d3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x766d8  ldarg.3
0x766d9  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotDictionary>::LookupEntry(void, var<u1>)
0x766de  stloc.3
0x766df  ldloc.3
0x766e0  brfalse.s loc_76719
0x766e2  ldloc.3
0x766e3  ldarg.2
0x766e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x766e9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x766ee  ldloca.s 4
0x766f0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue>::TryGetValue(var<u1>, !!T0)
0x766f5  brfalse.s loc_76719
0x766f7  ldloca.s 2
0x766f9  dup
0x766fa  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_ShareCount()
0x766ff  ldloca.s 4
0x76701  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_ShareCount()
0x76706  add
0x76707  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::set_ShareCount(int64)
0x7670c  ldloca.s 2
0x7670e  call     instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotValue::get_ShareCount()
0x76713  ldloc.0
0x76714  conv.i8
0x76715  ble.s    loc_76719
0x76717  ldc.i4.0
0x76718  ret
0x76719  ldc.i4.1
0x7671a  ret
```
