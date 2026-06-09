# Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetOpenIdProvider

- ea: `0x6f90`
- end: `0x705b`
- name: `Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetOpenIdProvider`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xbba0`

## callees

- `0x6f90`
- `0x7190`

## string_xrefs

- `0x6fac`: `{0}/.well-known/openid-configuration`
- `0x7033`: `Get Open Id provider failed with {0}. Service endpoint:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x6f90  ldarg.1
0x6f91  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x6f96  ldc.i4.1
0x6f97  newarr   [mscorlib]System.Char
0x6f9c  dup
0x6f9d  ldc.i4.0
0x6f9e  ldc.i4.s 0x2F
0x6fa0  stelem.i2
0x6fa1  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x6fa6  stloc.0
0x6fa7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6fac  ldstr    a0WellKnownOpen// "{0}/.well-known/openid-configuration"
0x6fb1  ldc.i4.1
0x6fb2  newarr   [mscorlib]System.Object
0x6fb7  dup
0x6fb8  ldc.i4.0
0x6fb9  ldloc.0
0x6fba  stelem.ref
0x6fbb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6fc0  stloc.1
0x6fc1  ldloc.1
0x6fc2  newobj   instance void [System]System.Uri::.ctor(string)
0x6fc7  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x6fcc  castclass [System]System.Net.HttpWebRequest
0x6fd1  dup
0x6fd2  ldstr    aGet// "GET"
0x6fd7  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0x6fdc  ldnull
0x6fdd  stloc.2
0x6fde  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0x6fe3  castclass [System]System.Net.HttpWebResponse
0x6fe8  stloc.3
0x6fe9  ldloc.3
0x6fea  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x6fef  stloc.s  4
0x6ff1  ldtoken  Microsoft.Crm.Authentication.OpenId.OpenIdConfigurationResponse
0x6ff6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6ffb  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer::.ctor(class [mscorlib]System.Type)
0x7000  ldloc.s  4
0x7002  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [mscorlib]System.IO.Stream)
0x7007  isinst   Microsoft.Crm.Authentication.OpenId.OpenIdConfigurationResponse
0x700c  stloc.2
0x700d  leave.s  loc_701B
0x700f  ldloc.s  4
0x7011  brfalse.s loc_701A
0x7013  ldloc.s  4
0x7015  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x701a  endfinally
0x701b  leave.s  loc_7027
0x701d  ldloc.3
0x701e  brfalse.s loc_7026
0x7020  ldloc.3
0x7021  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7026  endfinally
0x7027  ldloc.2
0x7028  stloc.s  5
0x702a  leave.s  loc_7058
0x702c  stloc.s  6
0x702e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7033  ldstr    aGetOpenIdProvi// "Get Open Id provider failed with {0}. S"...
0x7038  ldc.i4.2
0x7039  newarr   [mscorlib]System.Object
0x703e  dup
0x703f  ldc.i4.0
0x7040  ldarg.0
0x7041  ldloc.s  6
0x7043  call     instance string Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetWebException(class [System]System.Net.WebException exception)
0x7048  stelem.ref
0x7049  dup
0x704a  ldc.i4.1
0x704b  ldloc.1
0x704c  stelem.ref
0x704d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7052  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x7057  throw
0x7058  ldloc.s  5
0x705a  ret
```
