# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateEntityKey

- ea: `0xbac0`
- end: `0xbae4`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateEntityKey`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x10`
- `0x3140`
- `0xbac0`

## pseudocode

```c

```

## disassembly

```asm
0xbac0  ldarg.0
0xbac1  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xbac6  ldarg.1
0xbac7  ldstr    aEntitykey// "entitykey"
0xbacc  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xbad1  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.EntityKeyCreate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag parameterBag)
0xbad6  stloc.0
0xbad7  leave.s  loc_BAE2
0xbad9  stloc.1
0xbada  ldarg.0
0xbadb  ldloc.1
0xbadc  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xbae1  throw
0xbae2  ldloc.0
0xbae3  ret
```
