# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::PublishCustomizations

- ea: `0xb2a0`
- end: `0xb2b2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::PublishCustomizations`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2520`
- `0xb2a0`

## pseudocode

```c

```

## disassembly

```asm
0xb2a0  ldarg.1
0xb2a1  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.CustomizationsPublish::Execute(class [System.Xml]System.Xml.XmlNode data)
0xb2a6  leave.s  loc_B2B1
0xb2a8  stloc.0
0xb2a9  ldarg.0
0xb2aa  ldloc.0
0xb2ab  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb2b0  throw
0xb2b1  ret
```
