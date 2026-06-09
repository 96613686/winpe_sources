# Microsoft.Crm.Application.WebServices.WorkflowWebService::InvokeProcessAction

- ea: `0x8370`
- end: `0x83b3`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InvokeProcessAction`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1c0`
- `0x8370`

## pseudocode

```c

```

## disassembly

```asm
0x8370  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::.ctor()
0x8375  dup
0x8376  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter>::.ctor()
0x837b  dup
0x837c  newobj   instance void Microsoft.Crm.Application.WebServices.ProcessActionParameterConverter::.ctor()
0x8381  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter>::Add(var<u1>)
0x8386  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_Converters(class [mscorlib]System.Collections.Generic.IList`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter>)
0x838b  stloc.0
0x838c  ldarg.2
0x838d  ldloc.0
0x838e  call     T0x2B00000A
0x8393  stloc.1
0x8394  ldarg.1
0x8395  ldloc.1
0x8396  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x839b  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::InvokeProcessAction(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x83a0  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x83a5  stloc.2
0x83a6  leave.s  loc_83B1
0x83a8  stloc.3
0x83a9  ldarg.0
0x83aa  ldloc.3
0x83ab  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x83b0  throw
0x83b1  ldloc.2
0x83b2  ret
```
