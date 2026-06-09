# Microsoft.Crm.Workflow.WorkflowTracingService::.cctor

- ea: `0x9250`
- end: `0x9274`
- name: `Microsoft.Crm.Workflow.WorkflowTracingService::.cctor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9250`: `urn:schemas-microsoft-com:Microsoft.Crm.Workflow/WorkflowExecutionProperties/WorkflowTracingService`

## pseudocode

```c

```

## disassembly

```asm
0x9250  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:Microsoft.Crm"...
0x9255  call     class [System.Xml.Linq]System.Xml.Linq.XNamespace [System.Xml.Linq]System.Xml.Linq.XNamespace::Get(string)
0x925a  stsfld   class [System.Xml.Linq]System.Xml.Linq.XNamespace Microsoft.Crm.Workflow.WorkflowTracingService::traceInfoNamespace
0x925f  ldsfld   class [System.Xml.Linq]System.Xml.Linq.XNamespace Microsoft.Crm.Workflow.WorkflowTracingService::traceInfoNamespace
0x9264  ldstr    aTraceinfo// "TraceInfo"
0x9269  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XNamespace::GetName(string)
0x926e  stsfld   class [System.Xml.Linq]System.Xml.Linq.XName Microsoft.Crm.Workflow.WorkflowTracingService::traceInfoName
0x9273  ret
```
