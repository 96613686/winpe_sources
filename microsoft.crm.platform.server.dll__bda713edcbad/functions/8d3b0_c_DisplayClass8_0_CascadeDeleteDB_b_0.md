# <>c__DisplayClass8_0::<CascadeDeleteDB>b__0

- ea: `0x8d3b0`
- end: `0x8d588`
- name: `<>c__DisplayClass8_0::<CascadeDeleteDB>b__0`
- size: `472`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x5ed50`
- `0x5ee00`
- `0x5eed0`
- `0x5fcb0`
- `0x5fdd0`
- `0x5fe10`
- `0x5fe50`
- `0x60ff0`
- `0x67090`
- `0x67cf0`
- `0x8d3b0`

## string_xrefs

- `0x8d4e3`: `CascadeDeleteBulkOM`
- `0x8d44c`: `Delete Cascade Collect execution time`
- `0x8d4bf`: `Delete Cascade Collect entites count`
- `0x8d4c9`: `Delete Cascade Execute execution time`

## pseudocode

```c

```

## disassembly

```asm
0x8d3b0  ldc.i4.0
0x8d3b1  stloc.1
0x8d3b2  ldarg.0
0x8d3b3  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass8_0::context
0x8d3b8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x8d3bd  ldarg.0
0x8d3be  ldfld    int32 <>c__DisplayClass8_0::parentEntityObjectTypeCode
0x8d3c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x8d3c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesTo()
0x8d3cd  call     T0x2B0000CF
0x8d3d2  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship, bool> <>c::<>9__8_1
0x8d3d7  dup
0x8d3d8  brtrue.s loc_8D3F1
0x8d3da  pop
0x8d3db  ldsfld   class <>c <>c::<>9
0x8d3e0  ldftn    instance bool <>c::<CascadeDeleteDB>b__8_1(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship r)
0x8d3e6  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship, bool>::.ctor(object, native int)
0x8d3eb  dup
0x8d3ec  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship, bool> <>c::<>9__8_1
0x8d3f1  call     T0x2B0000D0
0x8d3f6  brfalse.s loc_8D44C
0x8d3f8  newobj   instance void Microsoft.Crm.BusinessEntities.CascadeRecordSet::.ctor()
0x8d3fd  stloc.0
0x8d3fe  ldarg.0
0x8d3ff  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass8_0::parentEntityIds
0x8d404  brfalse  loc_8D4AD
0x8d409  ldarg.0
0x8d40a  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass8_0::parentEntityIds
0x8d40f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x8d414  stloc.2
0x8d415  br.s     loc_8D438
0x8d417  ldloc.2
0x8d418  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x8d41d  stloc.3
0x8d41e  ldc.i4.4
0x8d41f  ldloc.3
0x8d420  ldarg.0
0x8d421  ldfld    int32 <>c__DisplayClass8_0::parentEntityObjectTypeCode
0x8d426  ldc.i4.0
0x8d427  ldc.i4.0
0x8d428  newobj   instance void Microsoft.Crm.BusinessEntities.CascadeRecord::.ctor(valuetype Microsoft.Crm.BusinessEntities.CascadeDeleteActionType actionType, valuetype [mscorlib]System.Guid id, int32 objectTypeCode, int32 columnNumber, int32 solutionComponentState)
0x8d42d  stloc.s  4
0x8d42f  ldloc.0
0x8d430  ldloc.s  4
0x8d432  callvirt instance class Microsoft.Crm.BusinessEntities.CascadeRecordSet Microsoft.Crm.BusinessEntities.CascadeRecordSet::Add(class Microsoft.Crm.BusinessEntities.CascadeRecord record)
0x8d437  pop
0x8d438  ldloc.2
0x8d439  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8d43e  brtrue.s loc_8D417
0x8d440  leave.s  loc_8D4AD
0x8d442  ldloc.2
0x8d443  brfalse.s loc_8D44B
0x8d445  ldloc.2
0x8d446  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d44b  endfinally
0x8d44c  ldstr    aDeleteCascadeC// "Delete Cascade Collect execution time"
0x8d451  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterExecutionTimeContext::.ctor(string)
0x8d456  stloc.s  5
0x8d458  ldarg.0
0x8d459  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass8_0::parentEntityIds
0x8d45e  ldarg.0
0x8d45f  ldfld    int32 <>c__DisplayClass8_0::parentEntityObjectTypeCode
0x8d464  ldarg.0
0x8d465  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass8_0::context
0x8d46a  call     class Microsoft.Crm.BusinessEntities.CascadeRecordSet Microsoft.Crm.BusinessEntities.CrmCascadeDBHandler::CollectForDelete(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> entityIds, int32 entityOtc, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8d46f  stloc.0
0x8d470  ldloc.0
0x8d471  brfalse.s loc_8D490
0x8d473  ldarg.0
0x8d474  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass8_0::parentEntityIds
0x8d479  brfalse.s loc_8D490
0x8d47b  ldloc.0
0x8d47c  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecordSet::get_Count()
0x8d481  ldarg.0
0x8d482  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass8_0::parentEntityIds
0x8d487  call     T0x2B000039
0x8d48c  cgt
0x8d48e  br.s     loc_8D491
0x8d490  ldc.i4.0
0x8d491  stloc.1
0x8d492  leave.s  loc_8D4AD
0x8d494  stloc.s  6
0x8d496  ldloc.s  5
0x8d498  ldloc.s  6
0x8d49a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterExecutionTimeContext::set_Error(class [mscorlib]System.Exception)
0x8d49f  rethrow
0x8d4a1  ldloc.s  5
0x8d4a3  brfalse.s loc_8D4AC
0x8d4a5  ldloc.s  5
0x8d4a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d4ac  endfinally
0x8d4ad  ldloc.0
0x8d4ae  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecordSet::get_Count()
0x8d4b3  ldarg.0
0x8d4b4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass8_0::parentEntityIds
0x8d4b9  ldarg.0
0x8d4ba  ldfld    int32 <>c__DisplayClass8_0::parentEntityObjectTypeCode
0x8d4bf  ldstr    aDeleteCascadeC_0// "Delete Cascade Collect entites count"
0x8d4c4  call     void Microsoft.Crm.BusinessEntities.CascadeEngine::LogRecordSetCount(int32 count, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> entityIds, int32 parentEntityObjectTypeCode, string perfCounterName)
0x8d4c9  ldstr    aDeleteCascadeE// "Delete Cascade Execute execution time"
0x8d4ce  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterExecutionTimeContext::.ctor(string)
0x8d4d3  stloc.s  7
0x8d4d5  ldarg.0
0x8d4d6  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass8_0::context
0x8d4db  ldc.i4.1
0x8d4dc  newobj   instance void Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool switchAuditingInfo)
0x8d4e1  stloc.s  8
0x8d4e3  ldstr    aCascadedeleteb// "CascadeDeleteBulkOM"
0x8d4e8  ldc.r8   30000.0
0x8d4f1  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::CreateAndStart(string, float64)
0x8d4f6  stloc.s  9
0x8d4f8  ldloc.0
0x8d4f9  ldarg.0
0x8d4fa  ldfld    int32 <>c__DisplayClass8_0::parentEntityObjectTypeCode
0x8d4ff  ldarg.0
0x8d500  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass8_0::context
0x8d505  ldloc.1
0x8d506  ldarg.0
0x8d507  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass8_0::parentEntityIds
0x8d50c  call     void Microsoft.Crm.BusinessEntities.CascadeEngine::CascadeDeleteBulkOM(class Microsoft.Crm.BusinessEntities.CascadeRecordSet collection, int32 parentEntityObjectTypeCode, class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool cascadeDeleteChildEntityRecords, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> parentEntityIds)
0x8d511  ldloc.0
0x8d512  brfalse.s loc_8D555
0x8d514  ldloc.0
0x8d515  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecordSet::get_Count()
0x8d51a  ldc.i4.0
0x8d51b  ble.s    loc_8D555
0x8d51d  ldloc.s  9
0x8d51f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d524  ldstr    aParententityob_0// "parentEntityObjectTypeCode: {0}; Number"...
0x8d529  ldc.i4.2
0x8d52a  newarr   [mscorlib]System.Object
0x8d52f  dup
0x8d530  ldc.i4.0
0x8d531  ldarg.0
0x8d532  ldfld    int32 <>c__DisplayClass8_0::parentEntityObjectTypeCode
0x8d537  box      [mscorlib]System.Int32
0x8d53c  stelem.ref
0x8d53d  dup
0x8d53e  ldc.i4.1
0x8d53f  ldloc.0
0x8d540  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecordSet::get_Count()
0x8d545  box      [mscorlib]System.Int32
0x8d54a  stelem.ref
0x8d54b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d550  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CounterList::set_TraceText(string)
0x8d555  leave.s  loc_8D587
0x8d557  ldarg.0
0x8d558  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass8_0::context
0x8d55d  call     void Microsoft.Crm.BusinessEntities.CascadeEngine::ClearIsCascadeDeleteForChildEntityRecords(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8d562  endfinally
0x8d563  ldloc.s  9
0x8d565  brfalse.s loc_8D56E
0x8d567  ldloc.s  9
0x8d569  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d56e  endfinally
0x8d56f  ldloc.s  8
0x8d571  brfalse.s loc_8D57A
0x8d573  ldloc.s  8
0x8d575  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d57a  endfinally
0x8d57b  ldloc.s  7
0x8d57d  brfalse.s loc_8D586
0x8d57f  ldloc.s  7
0x8d581  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d586  endfinally
0x8d587  ret
```
