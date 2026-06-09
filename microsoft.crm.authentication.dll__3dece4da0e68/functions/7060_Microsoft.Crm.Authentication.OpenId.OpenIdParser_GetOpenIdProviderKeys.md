# Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetOpenIdProviderKeys

- ea: `0x7060`
- end: `0x7107`
- name: `Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetOpenIdProviderKeys`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xbba0`

## callees

- `0x7060`
- `0x7190`

## string_xrefs

- `0x70db`: `Get Open Id provider keys failed with {0}. Uri:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x7060  ldarg.1
0x7061  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x7066  castclass [System]System.Net.HttpWebRequest
0x706b  dup
0x706c  ldstr    aGet// "GET"
0x7071  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0x7076  ldnull
0x7077  stloc.0
0x7078  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0x707d  castclass [System]System.Net.HttpWebResponse
0x7082  stloc.1
0x7083  ldloc.1
0x7084  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x7089  stloc.2
0x708a  ldtoken  Microsoft.Crm.Authentication.OpenId.JsonWebKeys
0x708f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7094  ldc.i4.1
0x7095  newarr   [mscorlib]System.Type
0x709a  dup
0x709b  ldc.i4.0
0x709c  ldtoken  Microsoft.Crm.Authentication.OpenId.JsonWebKeys
0x70a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x70a6  stelem.ref
0x70a7  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer::.ctor(class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>)
0x70ac  ldloc.2
0x70ad  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [mscorlib]System.IO.Stream)
0x70b2  isinst   Microsoft.Crm.Authentication.OpenId.JsonWebKeys
0x70b7  stloc.0
0x70b8  leave.s  loc_70C4
0x70ba  ldloc.2
0x70bb  brfalse.s loc_70C3
0x70bd  ldloc.2
0x70be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70c3  endfinally
0x70c4  leave.s  loc_70D0
0x70c6  ldloc.1
0x70c7  brfalse.s loc_70CF
0x70c9  ldloc.1
0x70ca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70cf  endfinally
0x70d0  ldloc.0
0x70d1  stloc.3
0x70d2  leave.s  loc_7105
0x70d4  stloc.s  4
0x70d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x70db  ldstr    aGetOpenIdProvi_0// "Get Open Id provider keys failed with {"...
0x70e0  ldc.i4.2
0x70e1  newarr   [mscorlib]System.Object
0x70e6  dup
0x70e7  ldc.i4.0
0x70e8  ldarg.0
0x70e9  ldloc.s  4
0x70eb  call     instance string Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetWebException(class [System]System.Net.WebException exception)
0x70f0  stelem.ref
0x70f1  dup
0x70f2  ldc.i4.1
0x70f3  ldarg.1
0x70f4  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x70f9  stelem.ref
0x70fa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x70ff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x7104  throw
0x7105  ldloc.3
0x7106  ret
```
