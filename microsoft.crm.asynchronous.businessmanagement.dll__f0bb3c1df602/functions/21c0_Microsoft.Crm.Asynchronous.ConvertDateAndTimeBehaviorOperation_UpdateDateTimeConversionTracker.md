# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateDateTimeConversionTracker

- ea: `0x21c0`
- end: `0x22bd`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateDateTimeConversionTracker`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1fa0`

## callees

- `0x21c0`
- `0x22c0`
- `0x2ac0`
- `0x13aa0`
- `0x13ac0`
- `0x13b20`
- `0x13b80`

## pseudocode

```c

```

## disassembly

```asm
0x21c0  ldarg.1
0x21c1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class EntityAttributeMetadataMap>::GetEnumerator()
0x21c6  stloc.0
0x21c7  br       loc_22A5
0x21cc  ldloc.0
0x21cd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class EntityAttributeMetadataMap>::get_Current()
0x21d2  stloc.1
0x21d3  ldloc.1
0x21d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x21d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x21de  stloc.2
0x21df  ldloc.1
0x21e0  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata> EntityAttributeMetadataMap::get_DateTimeAttributeMetadata()
0x21e5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata>::GetEnumerator()
0x21ea  stloc.3
0x21eb  br       loc_228E
0x21f0  ldloc.3
0x21f1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata>::get_Current()
0x21f6  stloc.s  4
0x21f8  ldloc.s  4
0x21fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x21ff  stloc.s  5
0x2201  ldarg.0
0x2202  ldloc.1
0x2203  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x2208  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x220d  ldloc.s  4
0x220f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x2214  call     instance string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::GetEntityAttributeKey(string entityName, string attributeName)
0x2219  stloc.s  6
0x221b  ldarg.0
0x221c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo> Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::jobSummaryItems
0x2221  ldloc.s  6
0x2223  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo>::ContainsKey(var<u1>)
0x2228  brfalse.s loc_228E
0x222a  ldarg.0
0x222b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo> Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::jobSummaryItems
0x2230  ldloc.s  6
0x2232  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo>::get_Item(void)
0x2237  callvirt instance bool RowLevelInfo::get_IsProcessingComplete()
0x223c  brfalse.s loc_2271
0x223e  ldarg.0
0x223f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo> Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::jobSummaryItems
0x2244  ldloc.s  6
0x2246  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo>::get_Item(void)
0x224b  callvirt instance int32 RowLevelInfo::get_NotConvertedRows()
0x2250  brtrue.s loc_2271
0x2252  ldarg.0
0x2253  ldarg.2
0x2254  ldloc.1
0x2255  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x225a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x225f  ldloc.2
0x2260  ldloc.s  4
0x2262  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x2267  ldloc.s  5
0x2269  ldc.i4.1
0x226a  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateDateTimeConversionTrackerInternal(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string entityLogicalName, valuetype [mscorlib]System.Guid entityId, string attributeLogicalName, valuetype [mscorlib]System.Guid attributeId, int32 status)
0x226f  br.s     loc_228E
0x2271  ldarg.0
0x2272  ldarg.2
0x2273  ldloc.1
0x2274  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x2279  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x227e  ldloc.2
0x227f  ldloc.s  4
0x2281  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x2286  ldloc.s  5
0x2288  ldc.i4.3
0x2289  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateDateTimeConversionTrackerInternal(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string entityLogicalName, valuetype [mscorlib]System.Guid entityId, string attributeLogicalName, valuetype [mscorlib]System.Guid attributeId, int32 status)
0x228e  ldloc.3
0x228f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2294  brtrue   loc_21F0
0x2299  leave.s  loc_22A5
0x229b  ldloc.3
0x229c  brfalse.s loc_22A4
0x229e  ldloc.3
0x229f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22a4  endfinally
0x22a5  ldloc.0
0x22a6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22ab  brtrue   loc_21CC
0x22b0  leave.s  loc_22BC
0x22b2  ldloc.0
0x22b3  brfalse.s loc_22BB
0x22b5  ldloc.0
0x22b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22bb  endfinally
0x22bc  ret
```
