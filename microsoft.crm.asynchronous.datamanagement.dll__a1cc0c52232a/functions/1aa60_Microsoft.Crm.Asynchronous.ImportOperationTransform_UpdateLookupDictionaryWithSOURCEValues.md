# Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateLookupDictionaryWithSOURCEValues

- ea: `0x1aa60`
- end: `0x1ab00`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateLookupDictionaryWithSOURCEValues`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19ee0`
- `0x1a2a0`

## callees

- `0x58b0`
- `0x5990`
- `0x5a60`
- `0xaab0`
- `0x1a260`
- `0x1aa60`

## pseudocode

```c

```

## disassembly

```asm
0x1aa60  ldarg.1
0x1aa61  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::GetEnumerator()
0x1aa66  stloc.0
0x1aa67  br.s     loc_1AAE3
0x1aa69  ldloca.s 0
0x1aa6b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Current()
0x1aa70  stloc.1
0x1aa71  ldloc.1
0x1aa72  ldarg.s  4
0x1aa74  callvirt instance class Microsoft.Crm.Asynchronous.ParsedDataObject Microsoft.Crm.Asynchronous.ParsedDataRow::get_Item(string columnName)
0x1aa79  callvirt instance string Microsoft.Crm.Asynchronous.ParsedDataObject::get_ColumnValue()
0x1aa7e  stloc.2
0x1aa7f  ldloc.2
0x1aa80  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1aa85  ldc.i4.0
0x1aa86  ble.s    loc_1AAD8
0x1aa88  ldarg.2
0x1aa89  ldloc.2
0x1aa8a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::ContainsKey(var<u1>)
0x1aa8f  brfalse.s loc_1AAD8
0x1aa91  ldarg.2
0x1aa92  ldloc.2
0x1aa93  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Item(void)
0x1aa98  brtrue.s loc_1AAAF
0x1aa9a  ldarg.2
0x1aa9b  ldloc.2
0x1aa9c  ldarg.3
0x1aa9d  ldloc.1
0x1aa9e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ParsedDataRow::get_RecordId()
0x1aaa3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1aaa8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::set_Item(var<u1>, !!T0)
0x1aaad  br.s     loc_1AAD8
0x1aaaf  ldarg.2
0x1aab0  ldloc.2
0x1aab1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Item(void)
0x1aab6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1aabb  ldloc.1
0x1aabc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ParsedDataRow::get_RecordId()
0x1aac1  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1aac6  brfalse.s loc_1AAD8
0x1aac8  ldarg.3
0x1aac9  call     bool Microsoft.Crm.Asynchronous.ImportOperationTransform::BypassDuplicateForSpecificEntities(string entityName)
0x1aace  brtrue.s loc_1AAD8
0x1aad0  ldarg.2
0x1aad1  ldloc.2
0x1aad2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::Remove(var<u1>)
0x1aad7  pop
0x1aad8  ldarg.0
0x1aad9  ldfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.ImportOperation::_throughputCounter
0x1aade  call     void Microsoft.Crm.Asynchronous.ImportOperation::IncrementPerfCounter(class [System]System.Diagnostics.PerformanceCounter pc)
0x1aae3  ldloca.s 0
0x1aae5  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.ParsedDataRow>::MoveNext()
0x1aaea  brtrue   loc_1AA69
0x1aaef  leave.s  loc_1AAFF
0x1aaf1  ldloca.s 0
0x1aaf3  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.ParsedDataRow>
0x1aaf9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1aafe  endfinally
0x1aaff  ret
```
