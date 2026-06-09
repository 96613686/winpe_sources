# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CheckSavedQuery

- ea: `0xb410`
- end: `0xb422`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CheckSavedQuery`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xabd0`
- `0xb410`

## pseudocode

```c

```

## disassembly

```asm
0xb410  ldarg.1
0xb411  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.SavedQueryCheck::Execute(valuetype [mscorlib]System.Guid savedQueryId)
0xb416  leave.s  loc_B421
0xb418  stloc.0
0xb419  ldarg.0
0xb41a  ldloc.0
0xb41b  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb420  throw
0xb421  ret
```
