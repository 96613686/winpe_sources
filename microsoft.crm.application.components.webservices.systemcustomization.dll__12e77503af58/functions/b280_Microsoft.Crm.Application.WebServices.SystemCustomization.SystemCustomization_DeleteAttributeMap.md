# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteAttributeMap

- ea: `0xb280`
- end: `0xb292`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteAttributeMap`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2090`
- `0xb280`

## pseudocode

```c

```

## disassembly

```asm
0xb280  ldarg.1
0xb281  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapDelete::Execute(valuetype [mscorlib]System.Guid attributeMapId)
0xb286  leave.s  loc_B291
0xb288  stloc.0
0xb289  ldarg.0
0xb28a  ldloc.0
0xb28b  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb290  throw
0xb291  ret
```
