# Microsoft.Xrm.Sdk.Client.IdentityProviderLookup::GetIdentityProvider

- ea: `0x17b10`
- end: `0x17c98`
- name: `Microsoft.Xrm.Sdk.Client.IdentityProviderLookup::GetIdentityProvider`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x171b0`

## callees

- `0x7ca0`
- `0x7cb0`
- `0x17af0`
- `0x17b10`
- `0x17ca0`

## string_xrefs

- `0x17b1c`: `orgIdServiceRoot`
- `0x17b51`: `login={0}&xml=1`

## pseudocode

```c

```

## disassembly

```asm
0x17b10  ldarg.1
0x17b11  ldstr    aHost// "host"
0x17b16  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x17b1b  ldarg.2
0x17b1c  ldstr    aOrgidservicero// "orgIdServiceRoot"
0x17b21  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x17b26  ldarg.3
0x17b27  ldstr    aUserprincipaln// "userPrincipalName"
0x17b2c  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNullOrEmpty(string parameter, string name)
0x17b31  ldarg.0
0x17b32  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderDictionary Microsoft.Xrm.Sdk.Client.IdentityProviderLookup::get_IdentityProviderDictionary()
0x17b37  ldarg.3
0x17b38  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IdentityProvider>::ContainsKey(var<u1>)
0x17b3d  brfalse.s loc_17B4C
0x17b3f  ldarg.0
0x17b40  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderDictionary Microsoft.Xrm.Sdk.Client.IdentityProviderLookup::get_IdentityProviderDictionary()
0x17b45  ldarg.3
0x17b46  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IdentityProvider>::get_Item(void)
0x17b4b  ret
0x17b4c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17b51  ldstr    aLogin0Xml1// "login={0}&xml=1"
0x17b56  ldc.i4.1
0x17b57  newarr   [mscorlib]System.Object
0x17b5c  dup
0x17b5d  ldc.i4.0
0x17b5e  ldarg.3
0x17b5f  call     string [System.Web]System.Web.HttpUtility::UrlEncode(string)
0x17b64  stelem.ref
0x17b65  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17b6a  stloc.0
0x17b6b  ldarg.1
0x17b6c  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x17b71  ldc.i4.1
0x17b72  newarr   [mscorlib]System.Char
0x17b77  dup
0x17b78  ldc.i4.0
0x17b79  ldc.i4.s 0x2F
0x17b7b  stelem.i2
0x17b7c  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x17b81  stloc.1
0x17b82  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17b87  ldstr    a0GetuserrealmS// "{0}/GetUserRealm.srf"
0x17b8c  ldc.i4.1
0x17b8d  newarr   [mscorlib]System.Object
0x17b92  dup
0x17b93  ldc.i4.0
0x17b94  ldloc.1
0x17b95  stelem.ref
0x17b96  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17b9b  stloc.2
0x17b9c  ldloc.2
0x17b9d  newobj   instance void [System]System.Uri::.ctor(string)
0x17ba2  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x17ba7  castclass [System]System.Net.HttpWebRequest
0x17bac  stloc.3
0x17bad  ldloc.3
0x17bae  ldstr    aPost// "POST"
0x17bb3  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0x17bb8  ldloc.3
0x17bb9  ldloc.0
0x17bba  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17bbf  conv.i8
0x17bc0  callvirt instance void [System]System.Net.WebRequest::set_ContentLength(int64)
0x17bc5  ldloc.3
0x17bc6  ldstr    aApplicationXWw// "application/x-www-form-urlencoded"
0x17bcb  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0x17bd0  ldnull
0x17bd1  stloc.s  4
0x17bd3  ldloc.3
0x17bd4  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0x17bd9  stloc.s  5
0x17bdb  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x17be0  ldloc.0
0x17be1  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x17be6  stloc.s  6
0x17be8  ldloc.s  5
0x17bea  ldloc.s  6
0x17bec  ldc.i4.0
0x17bed  ldloc.0
0x17bee  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17bf3  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x17bf8  leave.s  loc_17C06
0x17bfa  ldloc.s  5
0x17bfc  brfalse.s loc_17C05
0x17bfe  ldloc.s  5
0x17c00  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17c05  endfinally
0x17c06  ldloc.3
0x17c07  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0x17c0c  castclass [System]System.Net.HttpWebResponse
0x17c11  stloc.s  7
0x17c13  ldloc.s  7
0x17c15  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x17c1a  stloc.s  8
0x17c1c  ldloc.s  8
0x17c1e  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x17c23  stloc.s  9
0x17c25  ldtoken  Microsoft.Xrm.Sdk.Client.RealmInfo
0x17c2a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17c2f  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x17c34  ldloc.s  9
0x17c36  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x17c3b  isinst   Microsoft.Xrm.Sdk.Client.RealmInfo
0x17c40  stloc.s  4
0x17c42  leave.s  loc_17C50
0x17c44  ldloc.s  9
0x17c46  brfalse.s loc_17C4F
0x17c48  ldloc.s  9
0x17c4a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17c4f  endfinally
0x17c50  leave.s  loc_17C5E
0x17c52  ldloc.s  8
0x17c54  brfalse.s loc_17C5D
0x17c56  ldloc.s  8
0x17c58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17c5d  endfinally
0x17c5e  leave.s  loc_17C6C
0x17c60  ldloc.s  7
0x17c62  brfalse.s loc_17C6B
0x17c64  ldloc.s  7
0x17c66  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17c6b  endfinally
0x17c6c  ldloc.s  4
0x17c6e  brfalse.s loc_17C8E
0x17c70  ldarg.2
0x17c71  ldloc.s  4
0x17c73  call     class Microsoft.Xrm.Sdk.Client.IdentityProvider Microsoft.Xrm.Sdk.Client.IdentityProviderLookup::ExtractIdentityProvider(class [System]System.Uri orgIdServiceRoot, class Microsoft.Xrm.Sdk.Client.RealmInfo realmInfo)
0x17c78  stloc.s  0xA
0x17c7a  ldarg.0
0x17c7b  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderDictionary Microsoft.Xrm.Sdk.Client.IdentityProviderLookup::get_IdentityProviderDictionary()
0x17c80  ldarg.3
0x17c81  ldloc.s  0xA
0x17c83  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IdentityProvider>::set_Item(var<u1>, !!T0)
0x17c88  ldloc.s  0xA
0x17c8a  stloc.s  0xB
0x17c8c  leave.s  loc_17C95
0x17c8e  leave.s  loc_17C93
0x17c90  pop
0x17c91  leave.s  loc_17C93
0x17c93  ldnull
0x17c94  ret
0x17c95  ldloc.s  0xB
0x17c97  ret
```
