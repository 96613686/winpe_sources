# Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::CanReadToken

- ea: `0x9ce0`
- end: `0x9d2b`
- name: `Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::CanReadToken`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x9ce0`

## string_xrefs

- `0x9ce3`: `tokenString`

## pseudocode

```c

```

## disassembly

```asm
0x9ce0  ldarg.1
0x9ce1  brtrue.s loc_9CEE
0x9ce3  ldstr    aTokenstring// "tokenString"
0x9ce8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9ced  throw
0x9cee  ldarg.1
0x9cef  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9cf4  ldc.i4.2
0x9cf5  mul
0x9cf6  ldarg.0
0x9cf7  call     instance int32 [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityTokenHandler::get_MaximumTokenSizeInBytes()
0x9cfc  ble.s    loc_9D00
0x9cfe  ldc.i4.0
0x9cff  ret
0x9d00  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::JsonCompactSerializationRegex
0x9d05  ldarg.1
0x9d06  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x9d0b  brtrue.s loc_9D29
0x9d0d  ldarg.0
0x9d0e  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x9d13  ldarg.1
0x9d14  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x9d19  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x9d1e  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream)
0x9d23  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler::CanReadToken(class [System.Xml]System.Xml.XmlReader)
0x9d28  ret
0x9d29  ldc.i4.1
0x9d2a  ret
```
