# Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::ExecuteJob

- ea: `0x64c0`
- end: `0x65e1`
- name: `Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::ExecuteJob`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x64c0`
- `0x65f0`
- `0x6ac0`
- `0x6e60`
- `0x6e80`
- `0x6f80`
- `0x7030`
- `0x7040`
- `0x70a0`
- `0x7100`
- `0x7240`
- `0x7260`
- `0x7280`
- `0x7320`

## string_xrefs

- `0x65b0`: `Exception while calling UpdateJobToCompleted for job id : {0}, ex: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x64c0  newobj   instance void Microsoft.Crm.Asynchronous.EventTimeTracker::.ctor()
0x64c5  stloc.0
0x64c6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Diagnostics.Tracing.EventSource::get_CurrentThreadActivityId()
0x64cb  stloc.1
0x64cc  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x64d1  call     void [mscorlib]System.Diagnostics.Tracing.EventSource::SetCurrentThreadActivityId(valuetype [mscorlib]System.Guid)
0x64d6  ldnull
0x64d7  stloc.2
0x64d8  ldnull
0x64d9  stloc.3
0x64da  ldnull
0x64db  stloc.s  4
0x64dd  ldarg.1
0x64de  castclass Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData
0x64e3  stloc.2
0x64e4  ldloc.2
0x64e5  callvirt instance valuetype Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobOperationType Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::get_OperationType()
0x64ea  ldloc.2
0x64eb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::get_Id()
0x64f0  call     class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJob Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsFactory::GetJob(valuetype Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobOperationType operationType, valuetype [mscorlib]System.Guid jobId)
0x64f5  stloc.3
0x64f6  ldloc.0
0x64f7  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EventTimeTracker::MarkEventStart()
0x64fc  pop
0x64fd  call     class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource::get_Instance()
0x6502  ldloc.3
0x6503  ldloc.0
0x6504  callvirt instance void Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource::JobStart(class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJob job, class Microsoft.Crm.Asynchronous.EventTimeTracker timeTracker)
0x6509  ldloc.3
0x650a  callvirt instance string Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJob::Execute()
0x650f  stloc.s  4
0x6511  leave    loc_65E0
0x6516  stloc.s  5
0x6518  ldloc.s  5
0x651a  callvirt instance string [mscorlib]System.Object::ToString()
0x651f  stloc.s  4
0x6521  ldloc.s  5
0x6523  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6528  ldc.i4.s 0x15
0x652a  ldstr    aExceptionWhile_8// "Exception while calling AsychronouslyEx"...
0x652f  ldc.i4.2
0x6530  newarr   [mscorlib]System.Object
0x6535  dup
0x6536  ldc.i4.0
0x6537  ldloc.2
0x6538  brtrue.s loc_6541
0x653a  ldstr    asc_13392// "{}"
0x653f  br.s     loc_6556
0x6541  ldloc.2
0x6542  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::get_Id()
0x6547  stloc.s  6
0x6549  ldloca.s 6
0x654b  constrained. [mscorlib]System.Guid
0x6551  callvirt instance string [mscorlib]System.Object::ToString()
0x6556  stelem.ref
0x6557  dup
0x6558  ldc.i4.1
0x6559  ldloc.s  5
0x655b  stelem.ref
0x655c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6561  ldloc.3
0x6562  brfalse.s loc_6579
0x6564  ldloc.0
0x6565  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EventTimeTracker::MarkEventError()
0x656a  pop
0x656b  call     class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource::get_Instance()
0x6570  ldloc.3
0x6571  ldloc.0
0x6572  ldloc.s  5
0x6574  callvirt instance void Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource::JobErrorDiagnostics(class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJob job, class Microsoft.Crm.Asynchronous.EventTimeTracker timeTracker, class [mscorlib]System.Exception exception)
0x6579  leave.s  loc_65E0
0x657b  ldloc.3
0x657c  brfalse.s loc_6591
0x657e  ldloc.0
0x657f  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EventTimeTracker::MarkEventFinish()
0x6584  pop
0x6585  call     class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource::get_Instance()
0x658a  ldloc.3
0x658b  ldloc.0
0x658c  callvirt instance void Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource::JobFinish(class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJob job, class Microsoft.Crm.Asynchronous.EventTimeTracker timeTracker)
0x6591  ldloc.1
0x6592  call     void [mscorlib]System.Diagnostics.Tracing.EventSource::SetCurrentThreadActivityId(valuetype [mscorlib]System.Guid)
0x6597  ldloc.2
0x6598  brfalse.s loc_65DF
0x659a  ldarg.0
0x659b  ldloc.2
0x659c  ldloc.s  4
0x659e  call     instance void Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::UpdateJobToCompleted(class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData jobData, string message)
0x65a3  leave.s  loc_65DF
0x65a5  stloc.s  7
0x65a7  ldloc.s  7
0x65a9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x65ae  ldc.i4.s 0x15
0x65b0  ldstr    aExceptionWhile_9// "Exception while calling UpdateJobToComp"...
0x65b5  ldc.i4.2
0x65b6  newarr   [mscorlib]System.Object
0x65bb  dup
0x65bc  ldc.i4.0
0x65bd  ldloc.2
0x65be  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::get_Id()
0x65c3  stloc.s  6
0x65c5  ldloca.s 6
0x65c7  constrained. [mscorlib]System.Guid
0x65cd  callvirt instance string [mscorlib]System.Object::ToString()
0x65d2  stelem.ref
0x65d3  dup
0x65d4  ldc.i4.1
0x65d5  ldloc.s  7
0x65d7  stelem.ref
0x65d8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x65dd  leave.s  loc_65DF
0x65df  endfinally
0x65e0  ret
```
