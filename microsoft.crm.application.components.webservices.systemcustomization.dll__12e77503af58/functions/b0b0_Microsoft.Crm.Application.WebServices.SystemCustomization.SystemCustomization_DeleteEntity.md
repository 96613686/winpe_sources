# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteEntity

- ea: `0xb0b0`
- end: `0xb0c8`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteEntity`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x3040`
- `0xb0b0`

## pseudocode

```c

```

## disassembly

```asm
0xb0b0  ldarg.0
0xb0b1  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb0b6  ldarg.1
0xb0b7  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityDelete::Execute(valuetype [mscorlib]System.Guid solutionId, valuetype [mscorlib]System.Guid entityId)
0xb0bc  leave.s  loc_B0C7
0xb0be  stloc.0
0xb0bf  ldarg.0
0xb0c0  ldloc.0
0xb0c1  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb0c6  throw
0xb0c7  ret
```
