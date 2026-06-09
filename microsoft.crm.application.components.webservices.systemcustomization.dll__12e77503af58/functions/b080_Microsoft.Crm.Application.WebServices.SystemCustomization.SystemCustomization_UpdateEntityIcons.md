# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateEntityIcons

- ea: `0xb080`
- end: `0xb0a2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateEntityIcons`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x10`
- `0x37d0`
- `0xb080`

## pseudocode

```c

```

## disassembly

```asm
0xb080  ldarg.0
0xb081  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb086  ldarg.1
0xb087  ldstr    aEntity// "entity"
0xb08c  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xb091  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdateIcons(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag parameterBag)
0xb096  leave.s  loc_B0A1
0xb098  stloc.0
0xb099  ldarg.0
0xb09a  ldloc.0
0xb09b  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb0a0  throw
0xb0a1  ret
```
