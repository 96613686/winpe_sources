# Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::Run

- ea: `0x530`
- end: `0x5ce`
- name: `Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::Run`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x4f0`
- `0x500`
- `0x530`
- `0x5d0`
- `0x5e0`
- `0x5f0`
- `0x610`

## string_xrefs

- `0x538`: `Task PreRunCheck Started`
- `0x550`: `Task Execute Started`
- `0x568`: `Task Post Execute Started`
- `0x580`: `Task successfuly ran`
- `0x5a9`: `Anomaly Detection Task {0} failed with ex: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x530  ldarg.0
0x531  ldarg.0
0x532  ldfld    class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::taskRunStatus
0x537  ldc.i4.1
0x538  ldstr    aTaskPrerunchec// "Task PreRunCheck Started"
0x53d  call     instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::SetTaskRunStatus(class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus taskStatus, valuetype Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType statusType, string statusMessage)
0x542  ldarg.0
0x543  callvirt instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::PreRunCheck()
0x548  ldarg.0
0x549  ldarg.0
0x54a  ldfld    class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::taskRunStatus
0x54f  ldc.i4.2
0x550  ldstr    aTaskExecuteSta// "Task Execute Started"
0x555  call     instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::SetTaskRunStatus(class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus taskStatus, valuetype Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType statusType, string statusMessage)
0x55a  ldarg.0
0x55b  callvirt instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::Execute()
0x560  ldarg.0
0x561  ldarg.0
0x562  ldfld    class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::taskRunStatus
0x567  ldc.i4.3
0x568  ldstr    aTaskPostExecut// "Task Post Execute Started"
0x56d  call     instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::SetTaskRunStatus(class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus taskStatus, valuetype Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType statusType, string statusMessage)
0x572  ldarg.0
0x573  callvirt instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::PostExecute()
0x578  ldarg.0
0x579  ldarg.0
0x57a  ldfld    class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::taskRunStatus
0x57f  ldc.i4.4
0x580  ldstr    aTaskSuccessful// "Task successfuly ran"
0x585  call     instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::SetTaskRunStatus(class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus taskStatus, valuetype Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType statusType, string statusMessage)
0x58a  leave.s  loc_5CD
0x58c  stloc.0
0x58d  ldarg.0
0x58e  ldarg.0
0x58f  ldfld    class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::taskRunStatus
0x594  ldc.i4.5
0x595  ldloc.0
0x596  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x59b  call     instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::SetTaskRunStatus(class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus taskStatus, valuetype Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType statusType, string statusMessage)
0x5a0  ldloc.0
0x5a1  ldarg.0
0x5a2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_OrganizationId()
0x5a7  ldc.i4.s 0x15
0x5a9  ldstr    aAnomalyDetecti// "Anomaly Detection Task {0} failed with "...
0x5ae  ldc.i4.2
0x5af  newarr   [mscorlib]System.Object
0x5b4  dup
0x5b5  ldc.i4.0
0x5b6  ldarg.0
0x5b7  call     instance string Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::get_TaskName()
0x5bc  stelem.ref
0x5bd  dup
0x5be  ldc.i4.1
0x5bf  ldloc.0
0x5c0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5c5  stelem.ref
0x5c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5cb  leave.s  loc_5CD
0x5cd  ret
```
