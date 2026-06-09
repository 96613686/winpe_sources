# Microsoft.Crm.Authentication.Azure.AuthenticationTokenRetriever::GetAuthorizationToken

- ea: `0x3de90`
- end: `0x3e08e`
- name: `Microsoft.Crm.Authentication.Azure.AuthenticationTokenRetriever::GetAuthorizationToken`
- size: `510`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1a860`
- `0x1c060`
- `0x1eaa0`
- `0x1f510`
- `0x36100`
- `0x3dc80`
- `0x3dca0`
- `0x3dce0`
- `0x3dd10`
- `0x3de90`
- `0x3e200`

## string_xrefs

- `0x3de91`: `azureAdStsUrl`
- `0x3decd`: `AzureAdTokenOverride`
- `0x3e052`: `Exception when attempting to retrieve Azure Authentication Token: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3de90  ldarg.0
0x3de91  ldstr    aAzureadstsurl// "azureAdStsUrl"
0x3de96  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0x3de9b  ldarg.1
0x3de9c  ldstr    aTenantname// "tenantName"
0x3dea1  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0x3dea6  ldarg.2
0x3dea7  ldstr    aAppprincipalid// "appPrincipalId"
0x3deac  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0x3deb1  ldarg.3
0x3deb2  ldstr    aPassword// "password"
0x3deb7  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0x3debc  ldarg.s  4
0x3debe  ldstr    aResource_1// "resource"
0x3dec3  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0x3dec8  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0x3decd  ldstr    aAzureadtokenov// "AzureAdTokenOverride"
0x3ded2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3ded7  stloc.0
0x3ded8  ldloc.0
0x3ded9  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3dede  brtrue.s loc_3DF1F
0x3dee0  ldloc.0
0x3dee1  ldc.i4.s 0x20
0x3dee3  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x3dee8  stloc.s  5
0x3deea  ldloc.0
0x3deeb  ldc.i4.0
0x3deec  ldloc.s  5
0x3deee  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x3def3  stloc.s  6
0x3def5  ldloc.0
0x3def6  ldloc.s  5
0x3def8  ldc.i4.1
0x3def9  add
0x3defa  callvirt instance string [mscorlib]System.String::Substring(int32)
0x3deff  stloc.s  7
0x3df01  newobj   instance void Microsoft.Crm.Authentication.Azure.AuthenticationToken::.ctor()
0x3df06  dup
0x3df07  ldloc.s  6
0x3df09  callvirt instance void Microsoft.Crm.Authentication.Azure.AuthenticationToken::set_TokenType(string value)
0x3df0e  dup
0x3df0f  ldloc.s  7
0x3df11  callvirt instance void Microsoft.Crm.Authentication.Azure.AuthenticationToken::set_AccessToken(string value)
0x3df16  dup
0x3df17  ldc.i4.m1
0x3df18  conv.i8
0x3df19  callvirt instance void Microsoft.Crm.Authentication.Azure.AuthenticationToken::set_ExpiresOn(unsigned int64 value)
0x3df1e  ret
0x3df1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3df24  ldarg.0
0x3df25  ldc.i4.1
0x3df26  newarr   [mscorlib]System.Object
0x3df2b  dup
0x3df2c  ldc.i4.0
0x3df2d  ldarg.1
0x3df2e  call     string Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string input)
0x3df33  stelem.ref
0x3df34  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3df39  newobj   instance void [System]System.Uri::.ctor(string)
0x3df3e  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x3df43  castclass [System]System.Net.HttpWebRequest
0x3df48  stloc.1
0x3df49  newobj   instance void [mscorlib]System.Text.ASCIIEncoding::.ctor()
0x3df4e  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3df53  stloc.2
0x3df54  ldloc.2
0x3df55  ldstr    aGrantTypeClien// "grant_type=client_credentials"
0x3df5a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3df5f  pop
0x3df60  ldloc.2
0x3df61  ldstr    aResource_2// "&resource="
0x3df66  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3df6b  pop
0x3df6c  ldloc.2
0x3df6d  ldarg.s  4
0x3df6f  call     string Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string input)
0x3df74  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3df79  pop
0x3df7a  ldloc.2
0x3df7b  ldstr    aClientId// "&client_id="
0x3df80  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3df85  pop
0x3df86  ldloc.2
0x3df87  ldarg.2
0x3df88  call     string Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string input)
0x3df8d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3df92  pop
0x3df93  ldloc.2
0x3df94  ldstr    aClientSecret// "&client_secret="
0x3df99  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3df9e  pop
0x3df9f  ldloc.2
0x3dfa0  ldarg.3
0x3dfa1  call     string Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string input)
0x3dfa6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3dfab  pop
0x3dfac  ldloc.2
0x3dfad  callvirt instance string [mscorlib]System.Object::ToString()
0x3dfb2  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x3dfb7  stloc.3
0x3dfb8  ldloc.1
0x3dfb9  ldstr    aPost// "POST"
0x3dfbe  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0x3dfc3  ldloc.1
0x3dfc4  ldstr    aApplicationXWw// "application/x-www-form-urlencoded"
0x3dfc9  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0x3dfce  ldloc.1
0x3dfcf  ldloc.3
0x3dfd0  ldlen
0x3dfd1  conv.i4
0x3dfd2  conv.i8
0x3dfd3  callvirt instance void [System]System.Net.WebRequest::set_ContentLength(int64)
0x3dfd8  ldnull
0x3dfd9  stloc.s  4
0x3dfdb  ldloc.1
0x3dfdc  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0x3dfe1  stloc.s  8
0x3dfe3  ldloc.s  8
0x3dfe5  ldloc.3
0x3dfe6  ldc.i4.0
0x3dfe7  ldloc.3
0x3dfe8  ldlen
0x3dfe9  conv.i4
0x3dfea  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x3dfef  ldloc.1
0x3dff0  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0x3dff5  stloc.s  9
0x3dff7  ldloc.s  9
0x3dff9  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x3dffe  stloc.s  0xA
0x3e000  ldtoken  Microsoft.Crm.Authentication.Azure.AuthenticationToken
0x3e005  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e00a  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer::.ctor(class [mscorlib]System.Type)
0x3e00f  stloc.s  0xB
0x3e011  ldloc.s  0xA
0x3e013  brfalse.s loc_3E025
0x3e015  ldloc.s  0xB
0x3e017  ldloc.s  0xA
0x3e019  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [mscorlib]System.IO.Stream)
0x3e01e  castclass Microsoft.Crm.Authentication.Azure.AuthenticationToken
0x3e023  stloc.s  4
0x3e025  leave.s  loc_3E033
0x3e027  ldloc.s  0xA
0x3e029  brfalse.s loc_3E032
0x3e02b  ldloc.s  0xA
0x3e02d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e032  endfinally
0x3e033  leave.s  loc_3E041
0x3e035  ldloc.s  9
0x3e037  brfalse.s loc_3E040
0x3e039  ldloc.s  9
0x3e03b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e040  endfinally
0x3e041  leave.s  loc_3E08B
0x3e043  dup
0x3e044  call     string Microsoft.Crm.Authentication.Azure.AuthenticationTokenRetriever::GetWebException(class [System]System.Net.WebException exception)
0x3e049  stloc.s  0xC
0x3e04b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3e050  ldc.i4.s 0x14
0x3e052  ldstr    aExceptionWhenA// "Exception when attempting to retrieve A"...
0x3e057  ldc.i4.1
0x3e058  newarr   [mscorlib]System.Object
0x3e05d  dup
0x3e05e  ldc.i4.0
0x3e05f  ldloc.s  0xC
0x3e061  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3e066  brtrue.s loc_3E06C
0x3e068  ldloc.s  0xC
0x3e06a  br.s     loc_3E071
0x3e06c  ldsfld   string [mscorlib]System.String::Empty
0x3e071  stelem.ref
0x3e072  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x3e077  ldloc.s  0xC
0x3e079  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message)
0x3e07e  throw
0x3e07f  ldloc.s  8
0x3e081  brfalse.s loc_3E08A
0x3e083  ldloc.s  8
0x3e085  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e08a  endfinally
0x3e08b  ldloc.s  4
0x3e08d  ret
```
