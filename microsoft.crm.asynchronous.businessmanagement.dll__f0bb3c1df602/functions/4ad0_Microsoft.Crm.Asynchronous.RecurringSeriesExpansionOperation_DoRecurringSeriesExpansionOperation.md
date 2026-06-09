# Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::DoRecurringSeriesExpansionOperation

- ea: `0x4ad0`
- end: `0x4b27`
- name: `Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::DoRecurringSeriesExpansionOperation`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x48b0`

## callees

- `0x4ad0`
- `0x4b30`
- `0x4da0`
- `0x4fa0`
- `0x5120`

## string_xrefs

- `0x4afa`: `Master SeriesId Guid must not be null or empty.`

## pseudocode

```c

```

## disassembly

```asm
0x4ad0  ldarg.0
0x4ad1  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4ad6  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x4adb  brfalse.s loc_4B17
0x4add  ldloca.s 0
0x4adf  ldarg.0
0x4ae0  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::_asyncEvent
0x4ae5  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x4aea  call     instance void [mscorlib]System.Guid::.ctor(string)
0x4aef  ldloc.0
0x4af0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4af5  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4afa  ldstr    aMasterSeriesid// "Master SeriesId Guid must not be null o"...
0x4aff  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x4b04  ldarg.0
0x4b05  ldloc.0
0x4b06  ldc.i4.1
0x4b07  call     instance valuetype RecurringSeriesExpansionResult Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::ExpandSingleSeries(valuetype [mscorlib]System.Guid seriesId, bool isOnDemandJob)
0x4b0c  dup
0x4b0d  brtrue.s loc_4B16
0x4b0f  ldarg.0
0x4b10  ldloc.0
0x4b11  call     instance void Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::PreponeRecurringSeriesExpansionJobNextRunDate(valuetype [mscorlib]System.Guid seriesId)
0x4b16  ret
0x4b17  ldarg.0
0x4b18  call     instance bool Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::ExpandAllQualifiedSeries()
0x4b1d  brtrue.s loc_4B25
0x4b1f  ldarg.0
0x4b20  call     instance void Microsoft.Crm.Asynchronous.RecurringSeriesExpansionOperation::PostponeRecurringSeriesExpansionJobNextRunDate()
0x4b25  ldc.i4.0
0x4b26  ret
```
