# Microsoft.Crm.Asynchronous.AsyncService::StartComponents

- ea: `0x1650`
- end: `0x16a0`
- name: `Microsoft.Crm.Asynchronous.AsyncService::StartComponents`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`
- `0x1240`

## callees

- `0xc40`
- `0x1650`
- `0x1720`
- `0x1760`

## string_xrefs

- `0x1680`: `Exception while starting components: {0} - {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1650  ldarg.0
0x1651  ldfld    class Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine Microsoft.Crm.Asynchronous.AsyncService::_asyncManagerGroup
0x1656  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ServiceOperationExecutionEngine::StartOperation()
0x165b  ldarg.0
0x165c  call     instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x1661  ldc.i4.1
0x1662  bne.un.s loc_1675
0x1664  call     void [Microsoft.Crm.Core]Microsoft.Crm.RegControl::SetInAsyncServiceMaintenanceContext()
0x1669  ldarg.0
0x166a  call     instance void Microsoft.Crm.Asynchronous.AsyncService::StartKeyManager()
0x166f  ldarg.0
0x1670  call     instance void Microsoft.Crm.Asynchronous.AsyncService::StartScalegroupMaintenanceJobsMonitor()
0x1675  leave.s  loc_169F
0x1677  stloc.0
0x1678  ldloc.0
0x1679  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x167e  ldc.i4.s 0x15
0x1680  ldstr    aExceptionWhile_2// "Exception while starting components: {0"...
0x1685  ldc.i4.2
0x1686  newarr   [mscorlib]System.Object
0x168b  dup
0x168c  ldc.i4.0
0x168d  ldarg.0
0x168e  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0x1693  stelem.ref
0x1694  dup
0x1695  ldc.i4.1
0x1696  ldloc.0
0x1697  stelem.ref
0x1698  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x169d  rethrow
0x169f  ret
```
