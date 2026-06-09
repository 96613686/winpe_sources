# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateEntityEnforceStateTransitions

- ea: `0xb930`
- end: `0xb952`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateEntityEnforceStateTransitions`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x10`
- `0x3880`
- `0xb930`

## pseudocode

```c

```

## disassembly

```asm
0xb930  ldarg.0
0xb931  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb936  ldarg.1
0xb937  ldstr    aEntity// "entity"
0xb93c  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xb941  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdateEnforceStateTransitions(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag parameterBag)
0xb946  leave.s  loc_B951
0xb948  stloc.0
0xb949  ldarg.0
0xb94a  ldloc.0
0xb94b  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb950  throw
0xb951  ret
```
