# Microsoft.Crm.Tools.Admin.EventLogHelper::Write

- ea: `0x45a0`
- end: `0x45e7`
- name: `Microsoft.Crm.Tools.Admin.EventLogHelper::Write`
- size: `71`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7870`
- `0x7ca0`
- `0x14630`
- `0x14c00`
- `0x14d30`
- `0x161f0`
- `0x16330`
- `0x163d0`
- `0x172f0`
- `0x17340`
- `0x17af0`

## callees

- `0x45a0`

## pseudocode

```c

```

## disassembly

```asm
0x45a0  newobj   instance void [System]System.Diagnostics.EventLog::.ctor()
0x45a5  stloc.0
0x45a6  ldloc.0
0x45a7  ldsfld   string Microsoft.Crm.Tools.Admin.EventLogHelper::EventLogSourceName
0x45ac  callvirt instance void [System]System.Diagnostics.EventLog::set_Source(string)
0x45b1  ldloc.0
0x45b2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor(class [System]System.Diagnostics.EventLog)
0x45b7  stloc.1
0x45b8  ldloc.1
0x45b9  ldsfld   class EventLogMessageDictionary Microsoft.Crm.Tools.Admin.EventLogHelper::EventLogMessageDict
0x45be  ldarg.0
0x45bf  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.KeyedCollection`2<int64, class EventLogMessage>::get_Item(void)
0x45c4  ldfld    valuetype [System]System.Diagnostics.EventLogEntryType EventLogMessage::Type
0x45c9  ldarg.0
0x45ca  ldarg.1
0x45cb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x45d0  leave.s  loc_45E6
0x45d2  ldloc.1
0x45d3  brfalse.s loc_45DB
0x45d5  ldloc.1
0x45d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45db  endfinally
0x45dc  ldloc.0
0x45dd  brfalse.s loc_45E5
0x45df  ldloc.0
0x45e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45e5  endfinally
0x45e6  ret
```
