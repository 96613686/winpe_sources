# Microsoft.Crm.Asynchronous.AsyncService::StartScalegroupMaintenanceJobsMonitor

- ea: `0x1720`
- end: `0x173e`
- name: `Microsoft.Crm.Asynchronous.AsyncService::StartScalegroupMaintenanceJobsMonitor`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1650`

## callees

- `0x6300`
- `0x6310`

## pseudocode

```c

```

## disassembly

```asm
0x1720  ldarg.0
0x1721  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::_context
0x1726  ldc.i4.1
0x1727  ceq
0x1729  ldstr    aInMaintenanceC// "In maintenance context"
0x172e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1733  call     class Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::get_Instance()
0x1738  callvirt instance void Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::Start()
0x173d  ret
```
