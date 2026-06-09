# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::AddRequestInfoToTelemetry

- ea: `0x1da40`
- end: `0x1da75`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::AddRequestInfoToTelemetry`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d750`

## string_xrefs

- `0x1da45`: `CrmODataServiceDataProvider`

## pseudocode

```c

```

## disassembly

```asm
0x1da40  ldstr    aClassname// "className"
0x1da45  ldstr    aCrmodataservic// "CrmODataServiceDataProvider"
0x1da4a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x1da4f  ldstr    aMethodname// "methodName"
0x1da54  ldstr    aRetrieveedment// "RetrieveEdmEntityCollection"
0x1da59  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x1da5e  ldstr    aEntitycollecti_0// "entityCollectionName"
0x1da63  ldarg.0
0x1da64  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x1da69  ldstr    aCastedentityna// "castedEntityName"
0x1da6e  ldarg.1
0x1da6f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x1da74  ret
```
