# Microsoft.Crm.Asynchronous.AsyncService::CreatePerformanceCounters

- ea: `0x1570`
- end: `0x1615`
- name: `Microsoft.Crm.Asynchronous.AsyncService::CreatePerformanceCounters`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`

## callees

- `0x1570`
- `0x1830`
- `0x1850`

## pseudocode

```c

```

## disassembly

```asm
0x1570  ldarg.0
0x1571  ldarg.1
0x1572  ldarg.0
0x1573  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::_context
0x1578  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.PerformanceCounters [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.PerformanceCounters::Create(string, valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext)
0x157d  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePerformanceCounters Microsoft.Crm.Asynchronous.AsyncService::_counters
0x1582  leave.s  loc_15E2
0x1584  stloc.0
0x1585  ldarg.0
0x1586  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmptyPerformanceCounters::.ctor()
0x158b  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePerformanceCounters Microsoft.Crm.Asynchronous.AsyncService::_counters
0x1590  ldarg.0
0x1591  ldc.i4.1
0x1592  ldc.i4   0xC0004324
0x1597  conv.u8
0x1598  ldc.i4.1
0x1599  newarr   [mscorlib]System.Object
0x159e  dup
0x159f  ldc.i4.0
0x15a0  call     string Microsoft.Crm.Asynchronous.AsyncService::get_HostName()
0x15a5  ldstr    aException// ". Exception: "
0x15aa  ldloc.0
0x15ab  callvirt instance string [mscorlib]System.Object::ToString()
0x15b0  call     string [mscorlib]System.String::Concat(string, string, string)
0x15b5  stelem.ref
0x15b6  call     instance void Microsoft.Crm.Asynchronous.AsyncService::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventLogId, object[] parameters)
0x15bb  ldloc.0
0x15bc  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x15c1  ldc.i4.s 0x15
0x15c3  ldstr    aExceptionIniti// "Exception initializing performance coun"...
0x15c8  ldc.i4.2
0x15c9  newarr   [mscorlib]System.Object
0x15ce  dup
0x15cf  ldc.i4.0
0x15d0  ldarg.0
0x15d1  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0x15d6  stelem.ref
0x15d7  dup
0x15d8  ldc.i4.1
0x15d9  ldloc.0
0x15da  stelem.ref
0x15db  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x15e0  leave.s  loc_15E2
0x15e2  ldarg.0
0x15e3  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::_context
0x15e8  brfalse.s loc_15F3
0x15ea  ldarg.0
0x15eb  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::_context
0x15f0  ldc.i4.3
0x15f1  bne.un.s loc_1609
0x15f3  ldc.i4.1
0x15f4  ldstr    aPlatform// "Platform"
0x15f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterFactory::LoadCounters(valuetype [Microsoft.Crm.Core]Microsoft.Crm.PerformanceCounterLoadSetting, string)
0x15fe  ldc.i4.1
0x15ff  ldstr    aOutlooksync// "OutlookSync"
0x1604  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterFactory::LoadCounters(valuetype [Microsoft.Crm.Core]Microsoft.Crm.PerformanceCounterLoadSetting, string)
0x1609  ldc.i4.1
0x160a  ldstr    aServer// "Server"
0x160f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterFactory::LoadCounters(valuetype [Microsoft.Crm.Core]Microsoft.Crm.PerformanceCounterLoadSetting, string)
0x1614  ret
```
