# Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::ReadTokenInternal

- ea: `0xa020`
- end: `0xa0d6`
- name: `Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::ReadTokenInternal`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xa0e0`

## callees

- `0xa020`

## string_xrefs

- `0xa023`: `token`
- `0xa043`: `IDX10209: token has length: '{0}' which is larger than the MaximumTokenSizeInBytes: '{1}'.`
- `0xa083`: `IDX10708: '{0}' cannot read this string: '{1}'.\nThe string needs to be in compact JSON format, which is of the form: '<Base64UrlEncodedHeader>.<Base64UrlEndcodedPayload>.<OPTIONAL, Base64UrlEncodedSignature>'.`

## pseudocode

```c

```

## disassembly

```asm
0xa020  ldarg.1
0xa021  brtrue.s loc_A02E
0xa023  ldstr    aToken// "token"
0xa028  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa02d  throw
0xa02e  ldarg.1
0xa02f  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa034  ldc.i4.2
0xa035  mul
0xa036  ldarg.0
0xa037  call     instance int32 [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityTokenHandler::get_MaximumTokenSizeInBytes()
0xa03c  ble.s    loc_A075
0xa03e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa043  ldstr    aIdx10209TokenH// "IDX10209: token has length: '{0}' which"...
0xa048  ldc.i4.2
0xa049  newarr   [mscorlib]System.Object
0xa04e  dup
0xa04f  ldc.i4.0
0xa050  ldarg.1
0xa051  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa056  box      [mscorlib]System.Int32
0xa05b  stelem.ref
0xa05c  dup
0xa05d  ldc.i4.1
0xa05e  ldarg.0
0xa05f  call     instance int32 [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityTokenHandler::get_MaximumTokenSizeInBytes()
0xa064  box      [mscorlib]System.Int32
0xa069  stelem.ref
0xa06a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa06f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa074  throw
0xa075  ldarg.0
0xa076  ldarg.1
0xa077  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler::CanReadToken(string)
0xa07c  brtrue.s loc_A0A6
0xa07e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa083  ldstr    aIdx107080Canno// "IDX10708: '{0}' cannot read this string"...
0xa088  ldc.i4.2
0xa089  newarr   [mscorlib]System.Object
0xa08e  dup
0xa08f  ldc.i4.0
0xa090  ldarg.0
0xa091  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xa096  stelem.ref
0xa097  dup
0xa098  ldc.i4.1
0xa099  ldarg.1
0xa09a  stelem.ref
0xa09b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa0a0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa0a5  throw
0xa0a6  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::JsonCompactSerializationRegex
0xa0ab  ldarg.1
0xa0ac  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0xa0b1  brfalse.s loc_A0BA
0xa0b3  ldarg.1
0xa0b4  newobj   instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::.ctor(string)
0xa0b9  ret
0xa0ba  ldarg.0
0xa0bb  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xa0c0  ldarg.1
0xa0c1  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0xa0c6  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0xa0cb  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream)
0xa0d0  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler::ReadToken(class [System.Xml]System.Xml.XmlReader)
0xa0d5  ret
```
