# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteAttribute

- ea: `0xb000`
- end: `0xb018`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteAttribute`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1fe0`
- `0xb000`

## pseudocode

```c

```

## disassembly

```asm
0xb000  ldarg.1
0xb001  ldarg.0
0xb002  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb007  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeDelete::Execute(valuetype [mscorlib]System.Guid attributeId, valuetype [mscorlib]System.Guid solutionId)
0xb00c  leave.s  loc_B017
0xb00e  stloc.0
0xb00f  ldarg.0
0xb010  ldloc.0
0xb011  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb016  throw
0xb017  ret
```
