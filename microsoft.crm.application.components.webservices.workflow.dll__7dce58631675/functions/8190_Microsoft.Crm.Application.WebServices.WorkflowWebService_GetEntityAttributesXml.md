# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetEntityAttributesXml

- ea: `0x8190`
- end: `0x81a4`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetEntityAttributesXml`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8190`

## pseudocode

```c

```

## disassembly

```asm
0x8190  ldarg.1
0x8191  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl::GetAttributeXmlValueByEntityLogicalName(string)
0x8196  stloc.0
0x8197  leave.s  loc_81A2
0x8199  stloc.1
0x819a  ldarg.0
0x819b  ldloc.1
0x819c  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x81a1  throw
0x81a2  ldloc.0
0x81a3  ret
```
