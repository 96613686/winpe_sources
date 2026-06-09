# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::CreateOrUpdateDateTimeConversionTrackerEntry

- ea: `0x2900`
- end: `0x298b`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::CreateOrUpdateDateTimeConversionTrackerEntry`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2760`

## callees

- `0x22c0`
- `0x2900`
- `0x2990`
- `0x13aa0`
- `0x13ab0`
- `0x13ac0`

## pseudocode

```c

```

## disassembly

```asm
0x2900  ldarg.1
0x2901  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x2906  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x290b  stloc.0
0x290c  ldarg.1
0x290d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata> EntityAttributeMetadataMap::get_DateTimeAttributeMetadata()
0x2912  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata>::GetEnumerator()
0x2917  stloc.1
0x2918  br.s     loc_2976
0x291a  ldloc.1
0x291b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata>::get_Current()
0x2920  stloc.2
0x2921  ldloc.2
0x2922  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x2927  stloc.3
0x2928  ldarg.1
0x2929  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32> EntityAttributeMetadataMap::get_AttributeConversionTrackerStatusMap()
0x292e  ldloc.3
0x292f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::get_Item(void)
0x2934  stloc.s  4
0x2936  ldloc.s  4
0x2938  brtrue.s loc_2956
0x293a  ldarg.0
0x293b  ldarg.1
0x293c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x2941  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x2946  ldarg.2
0x2947  ldloc.0
0x2948  ldloc.2
0x2949  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x294e  ldloc.3
0x294f  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::CreateDateTimeConversionTrackerEntryInternal(string entityLogicalName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid entityId, string attributeLogicalName, valuetype [mscorlib]System.Guid attributeId)
0x2954  br.s     loc_2976
0x2956  ldloc.s  4
0x2958  ldc.i4.3
0x2959  bne.un.s loc_2976
0x295b  ldarg.0
0x295c  ldarg.2
0x295d  ldarg.1
0x295e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x2963  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x2968  ldloc.0
0x2969  ldloc.2
0x296a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x296f  ldloc.3
0x2970  ldc.i4.2
0x2971  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateDateTimeConversionTrackerInternal(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string entityLogicalName, valuetype [mscorlib]System.Guid entityId, string attributeLogicalName, valuetype [mscorlib]System.Guid attributeId, int32 status)
0x2976  ldloc.1
0x2977  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x297c  brtrue.s loc_291A
0x297e  leave.s  loc_298A
0x2980  ldloc.1
0x2981  brfalse.s loc_2989
0x2983  ldloc.1
0x2984  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2989  endfinally
0x298a  ret
```
