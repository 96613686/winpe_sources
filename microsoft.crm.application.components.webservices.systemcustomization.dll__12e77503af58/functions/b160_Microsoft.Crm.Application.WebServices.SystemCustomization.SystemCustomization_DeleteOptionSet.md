# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteOptionSet

- ea: `0xb160`
- end: `0xb178`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::DeleteOptionSet`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x92f0`
- `0xb160`

## pseudocode

```c

```

## disassembly

```asm
0xb160  ldarg.1
0xb161  ldarg.0
0xb162  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb167  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::Delete(valuetype [mscorlib]System.Guid optionSetId, valuetype [mscorlib]System.Guid solutionId)
0xb16c  leave.s  loc_B177
0xb16e  stloc.0
0xb16f  ldarg.0
0xb170  ldloc.0
0xb171  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb176  throw
0xb177  ret
```
