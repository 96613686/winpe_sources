# Microsoft.Crm.Asynchronous.AsyncService::StopScalegroupMaintenanceJobsMonitor

- ea: `0x1740`
- end: `0x175e`
- name: `Microsoft.Crm.Asynchronous.AsyncService::StopScalegroupMaintenanceJobsMonitor`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x16a0`

## callees

- `0x6300`
- `0x6360`

## pseudocode

```c

```

## disassembly

```asm
0x1740  ldarg.0
0x1741  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::_context
0x1746  ldc.i4.1
0x1747  ceq
0x1749  ldstr    aInMaintenanceC// "In maintenance context"
0x174e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1753  call     class Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::get_Instance()
0x1758  callvirt instance void Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::Stop()
0x175d  ret
```
