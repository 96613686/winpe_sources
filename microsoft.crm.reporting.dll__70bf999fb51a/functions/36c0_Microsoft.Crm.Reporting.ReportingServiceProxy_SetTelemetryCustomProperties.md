# Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties

- ea: `0x36c0`
- end: `0x36dc`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties`
- size: `28`
- prototype: ``
- caller_count: `27`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x89c0`
- `0x8a20`
- `0x8a70`
- `0x8ac0`
- `0x8b10`
- `0x8b60`
- `0x8bb0`
- `0x8c00`
- `0x8c50`
- `0x8cb0`
- `0x8d00`
- `0x8d60`
- `0x8db0`
- `0x8e10`
- `0x8e60`
- `0x8eb0`
- `0x8f00`
- `0x8f50`
- `0x8fa0`
- `0x8ff0`
- `0x9040`
- `0x9090`
- `0x9100`
- `0x9150`
- `0x91a0`
- `0x9200`
- `0x9250`

## callees

- `0x2f90`

## pseudocode

```c

```

## disassembly

```asm
0x36c0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x36c5  dup
0x36c6  ldstr    aReportserverur// "reportServerUrl"
0x36cb  ldarg.0
0x36cc  call     instance string Microsoft.Crm.Reporting.ReportingServiceProxy::get_Url()
0x36d1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x36d6  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x36db  ret
```
