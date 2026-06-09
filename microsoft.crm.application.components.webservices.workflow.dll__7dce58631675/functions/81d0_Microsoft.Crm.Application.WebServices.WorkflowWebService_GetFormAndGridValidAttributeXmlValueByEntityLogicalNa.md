# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetFormAndGridValidAttributeXmlValueByEntityLogicalName

- ea: `0x81d0`
- end: `0x81e4`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetFormAndGridValidAttributeXmlValueByEntityLogicalName`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x81d0`

## pseudocode

```c

```

## disassembly

```asm
0x81d0  ldarg.1
0x81d1  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityAttributeSelectionControl::GetFormAndGridValidAttributeXmlValueByEntityLogicalName(string)
0x81d6  stloc.0
0x81d7  leave.s  loc_81E2
0x81d9  stloc.1
0x81da  ldarg.0
0x81db  ldloc.1
0x81dc  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x81e1  throw
0x81e2  ldloc.0
0x81e3  ret
```
