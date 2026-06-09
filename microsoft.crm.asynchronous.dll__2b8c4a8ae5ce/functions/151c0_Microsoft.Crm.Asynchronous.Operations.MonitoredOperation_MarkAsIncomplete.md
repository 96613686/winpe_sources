# Microsoft.Crm.Asynchronous.Operations.MonitoredOperation::MarkAsIncomplete

- ea: `0x151c0`
- end: `0x15244`
- name: `Microsoft.Crm.Asynchronous.Operations.MonitoredOperation::MarkAsIncomplete`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x15180`
- `0x15190`
- `0x151c0`
- `0x15270`
- `0x155a0`
- `0x155b0`
- `0x17fe0`
- `0x18000`

## pseudocode

```c

```

## disassembly

```asm
0x151c0  ldarg.0
0x151c1  ldarg.1
0x151c2  callvirt instance bool Microsoft.Crm.Asynchronous.Operations.MonitoredOperation::SetErrorState(class [mscorlib]System.Exception exception)
0x151c7  brtrue.s loc_15235
0x151c9  ldarg.0
0x151ca  ldarg.1
0x151cb  callvirt instance class EventLogEntryDetails Microsoft.Crm.Asynchronous.Operations.MonitoredOperation::GetEventDetails(class [mscorlib]System.Exception ex)
0x151d0  stloc.0
0x151d1  ldloc.0
0x151d2  ldnull
0x151d3  cgt.un
0x151d5  ldstr    aEventDetailsMu// "Event details must not be null"
0x151da  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x151df  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x151e4  ldc.i4.s 0x15
0x151e6  ldstr    a0_0// "{0}"
0x151eb  ldc.i4.1
0x151ec  newarr   [mscorlib]System.Object
0x151f1  dup
0x151f2  ldc.i4.0
0x151f3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x151f8  ldstr    aUnexpectedExce// "Unexpected exception when trying to exe"...
0x151fd  ldc.i4.2
0x151fe  newarr   [mscorlib]System.Object
0x15203  dup
0x15204  ldc.i4.0
0x15205  ldarg.0
0x15206  call     instance string Microsoft.Crm.Asynchronous.Operations.IsolatedOperation::get_Name()
0x1520b  stelem.ref
0x1520c  dup
0x1520d  ldc.i4.1
0x1520e  ldarg.1
0x1520f  stelem.ref
0x15210  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15215  stelem.ref
0x15216  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1521b  ldarg.0
0x1521c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.Operations.MonitoredOperation::get_EventLog()
0x15221  ldc.i4.1
0x15222  ldloc.0
0x15223  callvirt instance int64 EventLogEntryDetails::get_EventId()
0x15228  ldc.i4.0
0x15229  ldloc.0
0x1522a  callvirt instance object[] EventLogEntryDetails::get_EventParameters()
0x1522f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog::WriteEntry(valuetype [System]System.Diagnostics.EventLogEntryType, int64, bool, object[])
0x15234  pop
0x15235  ldarg.0
0x15236  ldc.i4.1
0x15237  call     instance void Microsoft.Crm.Asynchronous.Operations.IsolatedOperation::set_HasBeenExecuted(bool value)
0x1523c  ldarg.0
0x1523d  ldc.i4.1
0x1523e  stfld    bool Microsoft.Crm.Asynchronous.Operations.MonitoredOperation::_executionFailed
0x15243  ret
```
