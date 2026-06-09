# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::AddRequestInfoToTelemetry

- ea: `0x21a30`
- end: `0x21a65`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::AddRequestInfoToTelemetry`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x218d0`

## string_xrefs

- `0x21a35`: `CrmODataMetadataServiceDataProvider`

## pseudocode

```c

```

## disassembly

```asm
0x21a30  ldstr    aClassname// "className"
0x21a35  ldstr    aCrmodatametada// "CrmODataMetadataServiceDataProvider"
0x21a3a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x21a3f  ldstr    aMethodname// "methodName"
0x21a44  ldstr    aRetrieveedment// "RetrieveEdmEntityCollection"
0x21a49  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x21a4e  ldstr    aEntitysetname// "entitySetName"
0x21a53  ldarg.0
0x21a54  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x21a59  ldstr    aCastedentityna// "castedEntityName"
0x21a5e  ldarg.1
0x21a5f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x21a64  ret
```
