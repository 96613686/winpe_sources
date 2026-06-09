# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateEntity

- ea: `0xb050`
- end: `0xb072`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateEntity`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x10`
- `0x3450`
- `0xb050`

## pseudocode

```c

```

## disassembly

```asm
0xb050  ldarg.0
0xb051  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb056  ldarg.1
0xb057  ldstr    aEntity// "entity"
0xb05c  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xb061  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0xb066  leave.s  loc_B071
0xb068  stloc.0
0xb069  ldarg.0
0xb06a  ldloc.0
0xb06b  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb070  throw
0xb071  ret
```
