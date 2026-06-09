# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::GetOptionSetDataXml

- ea: `0xb460`
- end: `0xb49c`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::GetOptionSetDataXml`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x9350`
- `0xb460`

## pseudocode

```c

```

## disassembly

```asm
0xb460  ldarg.1
0xb461  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb466  brfalse.s loc_B47C
0xb468  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb46d  ldarg.0
0xb46e  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb473  ldarg.2
0xb474  call     string Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetDataXml(valuetype [mscorlib]System.Guid optionSetId, valuetype [mscorlib]System.Guid solutionId, bool useLocalAndGlobal)
0xb479  stloc.0
0xb47a  leave.s  loc_B49A
0xb47c  ldarg.1
0xb47d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb482  ldarg.0
0xb483  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xb488  ldarg.2
0xb489  call     string Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetDataXml(valuetype [mscorlib]System.Guid optionSetId, valuetype [mscorlib]System.Guid solutionId, bool useLocalAndGlobal)
0xb48e  stloc.0
0xb48f  leave.s  loc_B49A
0xb491  stloc.1
0xb492  ldarg.0
0xb493  ldloc.1
0xb494  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb499  throw
0xb49a  ldloc.0
0xb49b  ret
```
