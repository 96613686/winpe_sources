# Microsoft.Crm.Sandbox.SandboxTracker::WriteEvent

- ea: `0x7630`
- end: `0x76fc`
- name: `Microsoft.Crm.Sandbox.SandboxTracker::WriteEvent`
- size: `204`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x72c0`
- `0x7330`
- `0x7380`
- `0x7410`
- `0x7440`
- `0x7480`

## callees

- `0x1450`
- `0x3080`
- `0x30f0`
- `0x7560`
- `0x7630`

## string_xrefs

- `0x7670`: `SandboxTracker.WriteEvent: enter`
- `0x76eb`: `SandboxTracker.WriteEvent: exit`

## pseudocode

```c

```

## disassembly

```asm
0x7630  ldarg.0
0x7631  call     instance void Microsoft.Crm.Sandbox.SandboxTracker::FormatFields()
0x7636  ldc.i4   0x80004F0E
0x763b  conv.u8
0x763c  ldarg.2
0x763d  ceq
0x763f  stloc.0
0x7640  ldloc.0
0x7641  ldc.i4   0x80004F0B
0x7646  conv.u8
0x7647  ldarg.2
0x7648  ceq
0x764a  or
0x764b  stloc.0
0x764c  ldc.i4.4
0x764d  ldc.i4.0
0x764e  call     T0x2B000008
0x7653  stloc.1
0x7654  ldloc.1
0x7655  ldc.i4.2
0x7656  clt
0x7658  ldc.i4.0
0x7659  ceq
0x765b  ldloc.0
0x765c  and
0x765d  ldloc.1
0x765e  ldc.i4.3
0x765f  clt
0x7661  ldc.i4.0
0x7662  ceq
0x7664  or
0x7665  brtrue.s loc_7668
0x7667  ret
0x7668  ldarg.0
0x7669  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTracker::_organizationId
0x766e  ldc.i4.s 0x27
0x7670  ldstr    aSandboxtracker// "SandboxTracker.WriteEvent: enter"
0x7675  ldc.i4.0
0x7676  newarr   [mscorlib]System.Object
0x767b  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x7680  ldarg.0
0x7681  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_origin
0x7686  brtrue.s loc_7690
0x7688  ldarg.0
0x7689  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_destination
0x768e  br.s     loc_7696
0x7690  ldarg.0
0x7691  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_origin
0x7696  stloc.2
0x7697  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x769c  stloc.3
0x769d  ldloc.3
0x769e  call     string Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0x76a3  ldarg.1
0x76a4  ldarg.2
0x76a5  ldc.i4.5
0x76a6  newarr   [mscorlib]System.Object
0x76ab  dup
0x76ac  ldc.i4.0
0x76ad  ldarg.0
0x76ae  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_trackingIdText
0x76b3  stelem.ref
0x76b4  dup
0x76b5  ldc.i4.1
0x76b6  call     string Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x76bb  stelem.ref
0x76bc  dup
0x76bd  ldc.i4.2
0x76be  ldarg.0
0x76bf  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_function
0x76c4  stelem.ref
0x76c5  dup
0x76c6  ldc.i4.3
0x76c7  ldloc.2
0x76c8  stelem.ref
0x76c9  dup
0x76ca  ldc.i4.4
0x76cb  ldarg.0
0x76cc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Sandbox.SandboxTracker::_additionalData
0x76d1  stelem.ref
0x76d2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x76d7  leave.s  loc_76E3
0x76d9  ldloc.3
0x76da  brfalse.s loc_76E2
0x76dc  ldloc.3
0x76dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x76e2  endfinally
0x76e3  ldarg.0
0x76e4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTracker::_organizationId
0x76e9  ldc.i4.s 0x27
0x76eb  ldstr    aSandboxtracker_0// "SandboxTracker.WriteEvent: exit"
0x76f0  ldc.i4.0
0x76f1  newarr   [mscorlib]System.Object
0x76f6  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x76fb  ret
```
