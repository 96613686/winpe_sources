# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateAttributeMap

- ea: `0xb260`
- end: `0xb272`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateAttributeMap`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2050`
- `0xb260`

## pseudocode

```c

```

## disassembly

```asm
0xb260  ldarg.1
0xb261  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapCreate::Execute(class [System.Xml]System.Xml.XmlNode data)
0xb266  leave.s  loc_B271
0xb268  stloc.0
0xb269  ldarg.0
0xb26a  ldloc.0
0xb26b  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb270  throw
0xb271  ret
```
