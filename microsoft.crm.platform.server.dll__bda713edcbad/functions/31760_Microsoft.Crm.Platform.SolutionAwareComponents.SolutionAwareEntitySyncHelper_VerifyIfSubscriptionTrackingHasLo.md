# Microsoft.Crm.Platform.SolutionAwareComponents.SolutionAwareEntitySyncHelper::VerifyIfSubscriptionTrackingHasLogicalDeleteField

- ea: `0x31760`
- end: `0x3178e`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.SolutionAwareEntitySyncHelper::VerifyIfSubscriptionTrackingHasLogicalDeleteField`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x315b0`
- `0x31670`

## callees

- `0x31760`
- `0x67090`

## string_xrefs

- `0x31769`: `SubscriptionTrackingDeletedObject`
- `0x3177e`: `islogicaldelete`

## pseudocode

```c

```

## disassembly

```asm
0x31760  ldarg.0
0x31761  brfalse.s loc_3178C
0x31763  ldarg.0
0x31764  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x31769  ldstr    aSubscriptiontr// "SubscriptionTrackingDeletedObject"
0x3176e  ldc.i4.0
0x3176f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x31774  stloc.0
0x31775  ldloc.0
0x31776  brfalse.s loc_3178C
0x31778  ldloc.0
0x31779  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x3177e  ldstr    aIslogicaldelet// "islogicaldelete"
0x31783  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x31788  brfalse.s loc_3178C
0x3178a  ldc.i4.1
0x3178b  ret
0x3178c  ldc.i4.0
0x3178d  ret
```
