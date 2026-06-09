# Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::PushTelemetry

- ea: `0x1aa30`
- end: `0x1aa44`
- name: `Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::PushTelemetry`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a730`
- `0x1a860`
- `0x1a920`

## callees

- `0x1aaa0`
- `0x1aab0`

## pseudocode

```c

```

## disassembly

```asm
0x1aa30  call     class Microsoft.Crm.Service.ObjectModel.Telemetry.ServiceManagementEventSource Microsoft.Crm.Service.ObjectModel.Telemetry.ServiceManagementEventSource::get_Instance()
0x1aa35  ldarg.0
0x1aa36  ldarg.1
0x1aa37  ldarg.2
0x1aa38  ldarg.3
0x1aa39  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x1aa3e  callvirt instance void Microsoft.Crm.Service.ObjectModel.Telemetry.ServiceManagementEventSource::ServiceEntityOperationCompleted(string EntityLogicalName, string RecordId, string Operation, string AdditionalData)
0x1aa43  ret
```
