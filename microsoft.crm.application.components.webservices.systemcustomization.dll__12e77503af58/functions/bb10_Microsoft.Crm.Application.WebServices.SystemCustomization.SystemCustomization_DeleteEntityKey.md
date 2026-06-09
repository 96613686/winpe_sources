# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteEntityKey

- ea: `0xbb10`
- end: `0xbb28`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteEntityKey`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x32e0`
- `0xbb10`

## pseudocode

```c

```

## disassembly

```asm
0xbb10  ldarg.1
0xbb11  ldarg.0
0xbb12  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xbb17  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityKeyDelete::Execute(valuetype [mscorlib]System.Guid entityKeyId, valuetype [mscorlib]System.Guid solutionId)
0xbb1c  leave.s  loc_BB27
0xbb1e  stloc.0
0xbb1f  ldarg.0
0xbb20  ldloc.0
0xbb21  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xbb26  throw
0xbb27  ret
```
