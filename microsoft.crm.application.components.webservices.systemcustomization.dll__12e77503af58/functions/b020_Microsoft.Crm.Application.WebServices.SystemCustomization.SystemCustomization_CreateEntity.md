# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateEntity

- ea: `0xb020`
- end: `0xb044`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateEntity`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x10`
- `0x26f0`
- `0xb020`

## pseudocode

```c

```

## disassembly

```asm
0xb020  ldarg.0
0xb021  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb026  ldarg.1
0xb027  ldstr    aEntity// "entity"
0xb02c  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xb031  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0xb036  stloc.0
0xb037  leave.s  loc_B042
0xb039  stloc.1
0xb03a  ldarg.0
0xb03b  ldloc.1
0xb03c  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb041  throw
0xb042  ldloc.0
0xb043  ret
```
