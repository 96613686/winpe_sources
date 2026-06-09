# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetEntityUniqueKeyAttributesXml

- ea: `0x81b0`
- end: `0x81c4`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetEntityUniqueKeyAttributesXml`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x81b0`

## pseudocode

```c

```

## disassembly

```asm
0x81b0  ldarg.1
0x81b1  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl::GetUniqueKeyAttributeXmlValueByEntityLogicalName(string)
0x81b6  stloc.0
0x81b7  leave.s  loc_81C2
0x81b9  stloc.1
0x81ba  ldarg.0
0x81bb  ldloc.1
0x81bc  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x81c1  throw
0x81c2  ldloc.0
0x81c3  ret
```
