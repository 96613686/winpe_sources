# Microsoft.Crm.Asynchronous.SqlTraceManager::Initialize

- ea: `0x6100`
- end: `0x61e3`
- name: `Microsoft.Crm.Asynchronous.SqlTraceManager::Initialize`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x5c20`
- `0x5c50`

## callees

- `0x5f00`
- `0x5f20`
- `0x6100`
- `0x61f0`

## string_xrefs

- `0x610c`: `traceDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x6100  ldarg.1
0x6101  ldstr    aConnection// "connection"
0x6106  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x610b  ldarg.2
0x610c  ldstr    aTracedirectory// "traceDirectory"
0x6111  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6116  ldarg.3
0x6117  ldstr    aTracefilename// "traceFileName"
0x611c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6121  ldarg.s  4
0x6123  ldc.i4.5
0x6124  ldc.i4.s 0x78
0x6126  ldstr    aTracedurationm// "traceDurationMinutes"
0x612b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfOutOfRange(int32, int32, int32, string)
0x6130  ldarg.s  6
0x6132  ldstr    aTraceevents// "traceEvents"
0x6137  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x613c  ldarg.s  6
0x613e  ldlen
0x613f  ldc.i4.0
0x6140  cgt.un
0x6142  ldstr    aNoTraceEventsS// "No trace events specified"
0x6147  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x614c  ldarg.s  7
0x614e  ldstr    aTracecolumns// "traceColumns"
0x6153  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6158  ldarg.s  7
0x615a  ldlen
0x615b  ldc.i4.0
0x615c  cgt.un
0x615e  ldstr    aNoTraceColumns// "No trace columns specified"
0x6163  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x6168  ldarg.0
0x6169  ldarg.1
0x616a  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.SqlTraceManager::_connection
0x616f  ldarg.0
0x6170  ldarg.2
0x6171  stfld    string Microsoft.Crm.Asynchronous.SqlTraceManager::_traceDirectory
0x6176  ldarg.0
0x6177  ldarg.3
0x6178  stfld    string Microsoft.Crm.Asynchronous.SqlTraceManager::_traceFileName
0x617d  ldarg.0
0x617e  ldarg.s  4
0x6180  stfld    int32 Microsoft.Crm.Asynchronous.SqlTraceManager::_traceDurationMinutes
0x6185  ldarg.0
0x6186  ldarg.s  5
0x6188  stfld    int32 Microsoft.Crm.Asynchronous.SqlTraceManager::_traceMaxFileSize
0x618d  ldarg.0
0x618e  call     instance void Microsoft.Crm.Asynchronous.SqlTraceManager::SetFullPath()
0x6193  ldarg.0
0x6194  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x6199  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Asynchronous.SqlTraceManager::_traceEvents
0x619e  ldc.i4.0
0x619f  stloc.0
0x61a0  br.s     loc_61B0
0x61a2  ldarg.0
0x61a3  ldarg.s  6
0x61a5  ldloc.0
0x61a6  ldelem.i4
0x61a7  call     instance void Microsoft.Crm.Asynchronous.SqlTraceManager::AddTraceEvent(int32 traceEvent)
0x61ac  ldloc.0
0x61ad  ldc.i4.1
0x61ae  add
0x61af  stloc.0
0x61b0  ldloc.0
0x61b1  ldarg.s  6
0x61b3  ldlen
0x61b4  conv.i4
0x61b5  blt.s    loc_61A2
0x61b7  ldarg.0
0x61b8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x61bd  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Asynchronous.SqlTraceManager::_traceColumns
0x61c2  ldc.i4.0
0x61c3  stloc.1
0x61c4  br.s     loc_61D4
0x61c6  ldarg.0
0x61c7  ldarg.s  7
0x61c9  ldloc.1
0x61ca  ldelem.i4
0x61cb  call     instance void Microsoft.Crm.Asynchronous.SqlTraceManager::AddTraceColumn(int32 traceColumn)
0x61d0  ldloc.1
0x61d1  ldc.i4.1
0x61d2  add
0x61d3  stloc.1
0x61d4  ldloc.1
0x61d5  ldarg.s  7
0x61d7  ldlen
0x61d8  conv.i4
0x61d9  blt.s    loc_61C6
0x61db  ldarg.0
0x61dc  ldc.i4.0
0x61dd  stfld    int32 Microsoft.Crm.Asynchronous.SqlTraceManager::_currentTraceStatus
0x61e2  ret
```
