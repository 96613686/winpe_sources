# <>c::<InitializeApplication>b__8_0

- ea: `0x148c0`
- end: `0x1492a`
- name: `<>c::<InitializeApplication>b__8_0`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0xa440`

## string_xrefs

- `0x148c0`: `Forcing Initialization of Service Configuration:\n`

## pseudocode

```c

```

## disassembly

```asm
0x148c0  ldstr    aForcingInitial// "Forcing Initialization of Service Confi"...
0x148c5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x148ca  stloc.0
0x148cb  ldloc.0
0x148cc  ldstr    aHost0// "Host: {0}\n"
0x148d1  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x148d6  call     string [Microsoft.Crm.Core]Microsoft.Crm.AuthenticationContextExtensions::CurrentHost(class [System.Web]System.Web.HttpContext)
0x148db  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x148e0  pop
0x148e1  ldloc.0
0x148e2  ldstr    aRequestUrl0// "Request Url: {0}\n"
0x148e7  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x148ec  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x148f1  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x148f6  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x148fb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x14900  pop
0x14901  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14906  ldc.i4.s 0x16
0x14908  ldloc.0
0x14909  callvirt instance string [mscorlib]System.Object::ToString()
0x1490e  ldc.i4.0
0x1490f  newarr   [mscorlib]System.Object
0x14914  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14919  ldarg.2
0x1491a  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs::get_FederationConfiguration()
0x1491f  call     class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::GetIdentityConfiguration()
0x14924  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration::set_IdentityConfiguration(class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration)
0x14929  ret
```
