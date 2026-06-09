# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateOptionSet

- ea: `0xb130`
- end: `0xb152`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateOptionSet`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x10`
- `0x92a0`
- `0xb130`

## pseudocode

```c

```

## disassembly

```asm
0xb130  ldarg.0
0xb131  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb136  ldarg.1
0xb137  ldstr    aOptionset// "optionset"
0xb13c  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xb141  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::Update(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0xb146  leave.s  loc_B151
0xb148  stloc.0
0xb149  ldarg.0
0xb14a  ldloc.0
0xb14b  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb150  throw
0xb151  ret
```
