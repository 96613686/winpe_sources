# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteCustomControl

- ea: `0xb0d0`
- end: `0xb0e2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteCustomControl`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x23e0`
- `0xb0d0`

## pseudocode

```c

```

## disassembly

```asm
0xb0d0  ldarg.1
0xb0d1  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.CustomControlDelete::Execute(valuetype [mscorlib]System.Guid customControlId)
0xb0d6  leave.s  loc_B0E1
0xb0d8  stloc.0
0xb0d9  ldarg.0
0xb0da  ldloc.0
0xb0db  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb0e0  throw
0xb0e1  ret
```
