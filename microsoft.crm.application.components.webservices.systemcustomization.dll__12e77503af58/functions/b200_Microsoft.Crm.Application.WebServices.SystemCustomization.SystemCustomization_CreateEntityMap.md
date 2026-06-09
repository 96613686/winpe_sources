# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateEntityMap

- ea: `0xb200`
- end: `0xb212`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateEntityMap`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x33b0`
- `0xb200`

## pseudocode

```c

```

## disassembly

```asm
0xb200  ldarg.1
0xb201  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityMapCreate::Execute(class [System.Xml]System.Xml.XmlNode data)
0xb206  leave.s  loc_B211
0xb208  stloc.0
0xb209  ldarg.0
0xb20a  ldloc.0
0xb20b  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb210  throw
0xb211  ret
```
