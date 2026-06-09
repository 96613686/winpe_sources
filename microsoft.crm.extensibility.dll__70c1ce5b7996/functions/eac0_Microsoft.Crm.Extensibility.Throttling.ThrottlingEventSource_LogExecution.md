# Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::LogExecution

- ea: `0xeac0`
- end: `0xeb5f`
- name: `Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::LogExecution`
- size: `159`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf210`
- `0xf2b0`
- `0x34940`
- `0x34be0`

## callees

- `0xeac0`
- `0xeb70`

## string_xrefs

- `0xeaf8`: `Exception occured during ThrottlingEventSource Telemetry WriteEvent for organizationId:{0},userId: {1}, endpointType:{2}, category:{3}, path:{4}, attempted:{5}, passed:{6}, threshold:{7}, retryAfter:{8}, enabled{9}`

## pseudocode

```c

```

## disassembly

```asm
0xeac0  ldarg.0
0xeac1  ldc.i4.1
0xeac2  ldarg.1
0xeac3  ldarg.2
0xeac4  ldarg.3
0xeac5  dup
0xeac6  brtrue.s loc_EACE
0xeac8  pop
0xeac9  ldsfld   string [mscorlib]System.String::Empty
0xeace  ldarg.s  4
0xead0  dup
0xead1  brtrue.s loc_EAD9
0xead3  pop
0xead4  ldsfld   string [mscorlib]System.String::Empty
0xead9  ldarg.s  5
0xeadb  dup
0xeadc  brtrue.s loc_EAE4
0xeade  pop
0xeadf  ldsfld   string [mscorlib]System.String::Empty
0xeae4  ldarg.s  6
0xeae6  ldarg.s  7
0xeae8  ldarg.s  8
0xeaea  ldarg.s  9
0xeaec  ldarg.s  0xA
0xeaee  call     instance void Microsoft.Crm.Extensibility.Throttling.ThrottlingEventSource::WriteEventFast(int32 eventId, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, string endpointType, string throttleType, string path, int64 attempted, int64 passed, int64 threshold, float64 retryAfter, bool enabled)
0xeaf3  leave.s  loc_EB5E
0xeaf5  ldarg.1
0xeaf6  ldc.i4.s 0x14
0xeaf8  ldstr    aExceptionOccur// "Exception occured during ThrottlingEven"...
0xeafd  ldc.i4.s 0xA
0xeaff  newarr   [mscorlib]System.Object
0xeb04  dup
0xeb05  ldc.i4.0
0xeb06  ldarg.1
0xeb07  box      [mscorlib]System.Guid
0xeb0c  stelem.ref
0xeb0d  dup
0xeb0e  ldc.i4.1
0xeb0f  ldarg.2
0xeb10  box      [mscorlib]System.Guid
0xeb15  stelem.ref
0xeb16  dup
0xeb17  ldc.i4.2
0xeb18  ldarg.3
0xeb19  stelem.ref
0xeb1a  dup
0xeb1b  ldc.i4.3
0xeb1c  ldarg.s  4
0xeb1e  stelem.ref
0xeb1f  dup
0xeb20  ldc.i4.4
0xeb21  ldarg.s  5
0xeb23  stelem.ref
0xeb24  dup
0xeb25  ldc.i4.5
0xeb26  ldarg.s  6
0xeb28  box      [mscorlib]System.Int64
0xeb2d  stelem.ref
0xeb2e  dup
0xeb2f  ldc.i4.6
0xeb30  ldarg.s  7
0xeb32  box      [mscorlib]System.Int64
0xeb37  stelem.ref
0xeb38  dup
0xeb39  ldc.i4.7
0xeb3a  ldarg.s  8
0xeb3c  box      [mscorlib]System.Int64
0xeb41  stelem.ref
0xeb42  dup
0xeb43  ldc.i4.8
0xeb44  ldarg.s  9
0xeb46  box      [mscorlib]System.Double
0xeb4b  stelem.ref
0xeb4c  dup
0xeb4d  ldc.i4.s 9
0xeb4f  ldarg.s  0xA
0xeb51  box      [mscorlib]System.Boolean
0xeb56  stelem.ref
0xeb57  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeb5c  leave.s  loc_EB5E
0xeb5e  ret
```
