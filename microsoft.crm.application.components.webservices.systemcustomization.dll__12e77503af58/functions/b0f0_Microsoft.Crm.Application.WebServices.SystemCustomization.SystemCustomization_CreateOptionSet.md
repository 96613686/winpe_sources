# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateOptionSet

- ea: `0xb0f0`
- end: `0xb121`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateOptionSet`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x10`
- `0x9260`
- `0xb0f0`

## pseudocode

```c

```

## disassembly

```asm
0xb0f0  ldarg.0
0xb0f1  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb0f6  ldarg.1
0xb0f7  ldstr    aOptionset// "optionset"
0xb0fc  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xb101  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::Create(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0xb106  stloc.0
0xb107  ldloca.s 0
0xb109  ldstr    aB// "B"
0xb10e  call     instance string [mscorlib]System.Guid::ToString(string)
0xb113  stloc.1
0xb114  leave.s  loc_B11F
0xb116  stloc.2
0xb117  ldarg.0
0xb118  ldloc.2
0xb119  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb11e  throw
0xb11f  ldloc.1
0xb120  ret
```
