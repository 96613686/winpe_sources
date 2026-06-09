# Microsoft.Crm.CrmEventLog::WriteEntry_1

- ea: `0x17de0`
- end: `0x17f43`
- name: `Microsoft.Crm.CrmEventLog::WriteEntry_1`
- size: `355`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x17d80`
- `0x17d90`
- `0x1e9b0`

## callees

- `0x17de0`
- `0x1eaa0`
- `0x1f510`
- `0x352e0`

## string_xrefs

- `0x17e75`: `Failed to write the following event message to the Event Log.{0}EventType:{1:G}{0}EventId={2}{0}Contents:{3}{0}The exception information is:{0}{4}`
- `0x17ee4`: `Failed to write the following event message to the Event Log.{0}EventType:{1:G}{0}EventId={2}{0}Contents:{3}{0}The exception information is:{0}{4}`

## pseudocode

```c

```

## disassembly

```asm
0x17de0  ldarg.0
0x17de1  ldfld    class [System]System.Diagnostics.EventLog Microsoft.Crm.CrmEventLog::eventLog
0x17de6  brtrue.s loc_17E03
0x17de8  ldarg.0
0x17de9  newobj   instance void [System]System.Diagnostics.EventLog::.ctor()
0x17dee  stfld    class [System]System.Diagnostics.EventLog Microsoft.Crm.CrmEventLog::eventLog
0x17df3  ldarg.0
0x17df4  ldfld    class [System]System.Diagnostics.EventLog Microsoft.Crm.CrmEventLog::eventLog
0x17df9  ldstr    aApplication// "Application"
0x17dfe  callvirt instance void [System]System.Diagnostics.EventLog::set_Log(string)
0x17e03  ldc.i4.1
0x17e04  stloc.0
0x17e05  ldc.i4.0
0x17e06  stloc.1
0x17e07  ldc.i4.0
0x17e08  stloc.2
0x17e09  ldarg.2
0x17e0a  ldloc.2
0x17e0b  ldarg.1
0x17e0c  newobj   instance void [System]System.Diagnostics.EventInstance::.ctor(int64, int32, valuetype [System]System.Diagnostics.EventLogEntryType)
0x17e11  stloc.3
0x17e12  newobj   instance void Microsoft.Crm.AutoReimpersonator::.ctor()
0x17e17  stloc.s  4
0x17e19  ldarg.0
0x17e1a  ldfld    class [System]System.Diagnostics.EventLog Microsoft.Crm.CrmEventLog::eventLog
0x17e1f  ldloc.3
0x17e20  ldarg.s  4
0x17e22  callvirt instance void [System]System.Diagnostics.EventLog::WriteEvent(class [System]System.Diagnostics.EventInstance, object[])
0x17e27  leave.s  loc_17E35
0x17e29  ldloc.s  4
0x17e2b  brfalse.s loc_17E34
0x17e2d  ldloc.s  4
0x17e2f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17e34  endfinally
0x17e35  leave.s  loc_17EAB
0x17e37  pop
0x17e38  ldarg.0
0x17e39  ldfld    class [System]System.Diagnostics.EventLog Microsoft.Crm.CrmEventLog::eventLog
0x17e3e  callvirt instance string [System]System.Diagnostics.EventLog::get_Log()
0x17e43  ldstr    aApplication// "Application"
0x17e48  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x17e4d  brfalse.s loc_17E61
0x17e4f  ldc.i4.1
0x17e50  stloc.1
0x17e51  ldarg.0
0x17e52  ldfld    class [System]System.Diagnostics.EventLog Microsoft.Crm.CrmEventLog::eventLog
0x17e57  ldstr    aApplication// "Application"
0x17e5c  callvirt instance void [System]System.Diagnostics.EventLog::set_Log(string)
0x17e61  leave.s  loc_17EAB
0x17e63  stloc.s  5
0x17e65  ldloc.1
0x17e66  brtrue.s loc_17EA9
0x17e68  ldarg.3
0x17e69  brfalse.s loc_17EA9
0x17e6b  ldc.i4.0
0x17e6c  stloc.0
0x17e6d  ldloc.s  5
0x17e6f  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x17e74  ldc.i4.6
0x17e75  ldstr    aFailedToWriteT// "Failed to write the following event mes"...
0x17e7a  ldc.i4.5
0x17e7b  newarr   [mscorlib]System.Object
0x17e80  dup
0x17e81  ldc.i4.0
0x17e82  call     string [mscorlib]System.Environment::get_NewLine()
0x17e87  stelem.ref
0x17e88  dup
0x17e89  ldc.i4.1
0x17e8a  ldarg.1
0x17e8b  box      [System]System.Diagnostics.EventLogEntryType
0x17e90  stelem.ref
0x17e91  dup
0x17e92  ldc.i4.2
0x17e93  ldarg.2
0x17e94  box      [mscorlib]System.Int64
0x17e99  stelem.ref
0x17e9a  dup
0x17e9b  ldc.i4.3
0x17e9c  ldarg.s  4
0x17e9e  stelem.ref
0x17e9f  dup
0x17ea0  ldc.i4.4
0x17ea1  ldloc.s  5
0x17ea3  stelem.ref
0x17ea4  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x17ea9  leave.s  loc_17EAB
0x17eab  ldloc.1
0x17eac  brfalse.s loc_17F1A
0x17eae  ldc.i4.1
0x17eaf  stloc.0
0x17eb0  newobj   instance void Microsoft.Crm.AutoReimpersonator::.ctor()
0x17eb5  stloc.s  4
0x17eb7  ldarg.0
0x17eb8  ldfld    class [System]System.Diagnostics.EventLog Microsoft.Crm.CrmEventLog::eventLog
0x17ebd  ldloc.3
0x17ebe  ldarg.s  4
0x17ec0  callvirt instance void [System]System.Diagnostics.EventLog::WriteEvent(class [System]System.Diagnostics.EventInstance, object[])
0x17ec5  leave.s  loc_17ED3
0x17ec7  ldloc.s  4
0x17ec9  brfalse.s loc_17ED2
0x17ecb  ldloc.s  4
0x17ecd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17ed2  endfinally
0x17ed3  leave.s  loc_17F1A
0x17ed5  stloc.s  6
0x17ed7  ldarg.3
0x17ed8  brfalse.s loc_17F18
0x17eda  ldc.i4.0
0x17edb  stloc.0
0x17edc  ldloc.s  6
0x17ede  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x17ee3  ldc.i4.6
0x17ee4  ldstr    aFailedToWriteT// "Failed to write the following event mes"...
0x17ee9  ldc.i4.5
0x17eea  newarr   [mscorlib]System.Object
0x17eef  dup
0x17ef0  ldc.i4.0
0x17ef1  call     string [mscorlib]System.Environment::get_NewLine()
0x17ef6  stelem.ref
0x17ef7  dup
0x17ef8  ldc.i4.1
0x17ef9  ldarg.1
0x17efa  box      [System]System.Diagnostics.EventLogEntryType
0x17eff  stelem.ref
0x17f00  dup
0x17f01  ldc.i4.2
0x17f02  ldarg.2
0x17f03  box      [mscorlib]System.Int64
0x17f08  stelem.ref
0x17f09  dup
0x17f0a  ldc.i4.3
0x17f0b  ldarg.s  4
0x17f0d  stelem.ref
0x17f0e  dup
0x17f0f  ldc.i4.4
0x17f10  ldloc.s  6
0x17f12  stelem.ref
0x17f13  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x17f18  leave.s  loc_17F1A
0x17f1a  nop
0x17f1b  leave.s  loc_17F41
0x17f1d  stloc.s  7
0x17f1f  ldarg.3
0x17f20  brfalse.s loc_17F3F
0x17f22  ldloc.s  7
0x17f24  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x17f29  ldc.i4.6
0x17f2a  ldstr    aFailedToPostEv// "Failed to post Event Log failure to Mic"...
0x17f2f  ldc.i4.1
0x17f30  newarr   [mscorlib]System.Object
0x17f35  dup
0x17f36  ldc.i4.0
0x17f37  ldloc.s  7
0x17f39  stelem.ref
0x17f3a  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x17f3f  leave.s  loc_17F41
0x17f41  ldloc.0
0x17f42  ret
```
