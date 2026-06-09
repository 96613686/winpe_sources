# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateAttribute

- ea: `0xafd0`
- end: `0xaff2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateAttribute`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x10`
- `0x20e0`
- `0xafd0`

## pseudocode

```c

```

## disassembly

```asm
0xafd0  ldarg.0
0xafd1  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xafd6  ldarg.1
0xafd7  ldstr    aAttribute// "attribute"
0xafdc  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xafe1  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeUpdate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0xafe6  leave.s  loc_AFF1
0xafe8  stloc.0
0xafe9  ldarg.0
0xafea  ldloc.0
0xafeb  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xaff0  throw
0xaff1  ret
```
