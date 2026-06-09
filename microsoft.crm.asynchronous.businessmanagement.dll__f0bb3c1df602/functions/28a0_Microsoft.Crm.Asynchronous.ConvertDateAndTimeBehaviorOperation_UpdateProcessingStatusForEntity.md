# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateProcessingStatusForEntity

- ea: `0x28a0`
- end: `0x28f6`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateProcessingStatusForEntity`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2760`

## callees

- `0x28a0`
- `0x2ac0`
- `0x13aa0`
- `0x13ac0`
- `0x13b30`

## pseudocode

```c

```

## disassembly

```asm
0x28a0  ldarg.1
0x28a1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x28a6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x28ab  stloc.0
0x28ac  ldarg.1
0x28ad  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata> EntityAttributeMetadataMap::get_DateTimeAttributeMetadata()
0x28b2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata>::GetEnumerator()
0x28b7  stloc.1
0x28b8  br.s     loc_28E1
0x28ba  ldloc.1
0x28bb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata>::get_Current()
0x28c0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x28c5  stloc.2
0x28c6  ldarg.0
0x28c7  ldloc.0
0x28c8  ldloc.2
0x28c9  call     instance string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::GetEntityAttributeKey(string entityName, string attributeName)
0x28ce  stloc.3
0x28cf  ldarg.0
0x28d0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo> Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::jobSummaryItems
0x28d5  ldloc.3
0x28d6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RowLevelInfo>::get_Item(void)
0x28db  ldarg.2
0x28dc  callvirt instance void RowLevelInfo::set_IsProcessingComplete(bool value)
0x28e1  ldloc.1
0x28e2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x28e7  brtrue.s loc_28BA
0x28e9  leave.s  loc_28F5
0x28eb  ldloc.1
0x28ec  brfalse.s loc_28F4
0x28ee  ldloc.1
0x28ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28f4  endfinally
0x28f5  ret
```
