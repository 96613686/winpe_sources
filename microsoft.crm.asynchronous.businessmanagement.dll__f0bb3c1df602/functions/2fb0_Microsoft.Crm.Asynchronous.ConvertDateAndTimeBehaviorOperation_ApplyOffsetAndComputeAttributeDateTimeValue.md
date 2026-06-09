# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::ApplyOffsetAndComputeAttributeDateTimeValue

- ea: `0x2fb0`
- end: `0x302a`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::ApplyOffsetAndComputeAttributeDateTimeValue`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x2ae0`

## callees

- `0x2fb0`
- `0x3030`
- `0x3060`
- `0x3c60`
- `0x3cc0`

## pseudocode

```c

```

## disassembly

```asm
0x2fb0  ldarg.s  4
0x2fb2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::get_Keys()
0x2fb7  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, valuetype [mscorlib]System.DateTime>::GetEnumerator()
0x2fbc  stloc.0
0x2fbd  br.s     loc_3010
0x2fbf  ldloca.s 0
0x2fc1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, valuetype [mscorlib]System.DateTime>::get_Current()
0x2fc6  stloc.1
0x2fc7  ldarg.s  4
0x2fc9  ldloc.1
0x2fca  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::get_Item(void)
0x2fcf  stloc.2
0x2fd0  ldarg.1
0x2fd1  brfalse.s loc_2FFA
0x2fd3  ldloc.2
0x2fd4  call     bool Microsoft.Crm.Asynchronous.DateTimeConversionHelper::CanBeAutoConverted(valuetype [mscorlib]System.DateTime value)
0x2fd9  brfalse.s loc_2FFA
0x2fdb  ldloc.2
0x2fdc  call     float64 Microsoft.Crm.Asynchronous.DateTimeConversionHelper::GetOffset(valuetype [mscorlib]System.DateTime value)
0x2fe1  ldc.r8   0.0
0x2fea  beq.s    loc_2FFA
0x2fec  ldarg.0
0x2fed  ldarg.s  7
0x2fef  ldloc.1
0x2ff0  ldloc.2
0x2ff1  ldarg.s  0xA
0x2ff3  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::AutoConvert(class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime> attributeDateTimeMap, string attribute, valuetype [mscorlib]System.DateTime value, class [mscorlib]System.Collections.Generic.List`1<string> canBeAutoConvertedAttributeNames)
0x2ff8  br.s     loc_3010
0x2ffa  ldarg.0
0x2ffb  ldarg.3
0x2ffc  ldarg.2
0x2ffd  ldarg.s  5
0x2fff  ldarg.s  6
0x3001  ldloc.1
0x3002  ldloc.2
0x3003  ldarg.s  7
0x3005  ldarg.s  8
0x3007  ldarg.s  9
0x3009  ldarg.s  0xB
0x300b  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::ApplySpecifiedConversionRule(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule conversionRule, valuetype [mscorlib]System.Nullable`1<int32> timeZoneCode, valuetype [mscorlib]System.Guid UserIdForConversion, int32 ownerIdType, string attribute, valuetype [mscorlib]System.DateTime dateTimeVal, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime> attributeDateTimeMap, string entityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Collections.Generic.List`1<string> canBeConvertedUsingRuleAttributeNames)
0x3010  ldloca.s 0
0x3012  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, valuetype [mscorlib]System.DateTime>::MoveNext()
0x3017  brtrue.s loc_2FBF
0x3019  leave.s  loc_3029
0x301b  ldloca.s 0
0x301d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, valuetype [mscorlib]System.DateTime>
0x3023  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3028  endfinally
0x3029  ret
```
