# Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::ValidateAudience

- ea: `0x9d30`
- end: `0x9f2a`
- name: `Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::ValidateAudience`
- size: `506`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x9d30`
- `0x9f30`
- `0x9f40`
- `0xdd40`

## pseudocode

```c

```

## disassembly

```asm
0x9d30  ldnull
0x9d31  stloc.0
0x9d32  ldc.i4.0
0x9d33  stloc.1
0x9d34  ldarg.2
0x9d35  isinst   [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken
0x9d3a  stloc.2
0x9d3b  ldarg.3
0x9d3c  brfalse  loc_9ED5
0x9d41  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9d46  stloc.s  4
0x9d48  ldloc.2
0x9d49  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_Claims()
0x9d4e  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__3_1
0x9d53  dup
0x9d54  brtrue.s loc_9D6D
0x9d56  pop
0x9d57  ldsfld   class <>c <>c::<>9
0x9d5c  ldftn    instance bool <>c::<ValidateAudience>b__3_1(class [mscorlib]System.Security.Claims.Claim c)
0x9d62  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x9d67  dup
0x9d68  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__3_1
0x9d6d  call     T0x2B00000D
0x9d72  stloc.s  5
0x9d74  ldloc.s  5
0x9d76  brfalse.s loc_9D86
0x9d78  ldloca.s 4
0x9d7a  ldloc.s  5
0x9d7c  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x9d81  call     instance void [mscorlib]System.Guid::.ctor(string)
0x9d86  ldsfld   valuetype [mscorlib]System.Guid[] Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::ApplicationsUsingRestrictedAudienceSecurity
0x9d8b  ldloc.s  4
0x9d8d  call     T0x2B000016
0x9d92  brfalse  loc_9ECE
0x9d97  ldc.i4.1
0x9d98  stloc.1
0x9d99  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x9d9e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x9da3  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x9da8  stloc.s  6
0x9daa  ldarg.3
0x9dab  callvirt instance class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::Clone()
0x9db0  starg.s  3
0x9db2  ldarg.3
0x9db3  ldc.i4.8
0x9db4  newarr   [mscorlib]System.String
0x9db9  dup
0x9dba  ldc.i4.0
0x9dbb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9dc0  ldstr    aHttps0// "https://{0}"
0x9dc5  ldc.i4.1
0x9dc6  newarr   [mscorlib]System.Object
0x9dcb  dup
0x9dcc  ldc.i4.0
0x9dcd  ldloc.s  6
0x9dcf  callvirt instance string [System]System.Uri::get_Host()
0x9dd4  stelem.ref
0x9dd5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9dda  stelem.ref
0x9ddb  dup
0x9ddc  ldc.i4.1
0x9ddd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9de2  ldstr    aHttps0_0// "https://{0}/"
0x9de7  ldc.i4.1
0x9de8  newarr   [mscorlib]System.Object
0x9ded  dup
0x9dee  ldc.i4.0
0x9def  ldloc.s  6
0x9df1  callvirt instance string [System]System.Uri::get_Host()
0x9df6  stelem.ref
0x9df7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9dfc  stelem.ref
0x9dfd  dup
0x9dfe  ldc.i4.2
0x9dff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e04  ldstr    aHttps0// "https://{0}"
0x9e09  ldc.i4.1
0x9e0a  newarr   [mscorlib]System.Object
0x9e0f  dup
0x9e10  ldc.i4.0
0x9e11  ldloc.s  6
0x9e13  callvirt instance string [System]System.Uri::get_Authority()
0x9e18  stelem.ref
0x9e19  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9e1e  stelem.ref
0x9e1f  dup
0x9e20  ldc.i4.3
0x9e21  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e26  ldstr    aHttps0_0// "https://{0}/"
0x9e2b  ldc.i4.1
0x9e2c  newarr   [mscorlib]System.Object
0x9e31  dup
0x9e32  ldc.i4.0
0x9e33  ldloc.s  6
0x9e35  callvirt instance string [System]System.Uri::get_Authority()
0x9e3a  stelem.ref
0x9e3b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9e40  stelem.ref
0x9e41  dup
0x9e42  ldc.i4.4
0x9e43  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e48  ldstr    aHttp0// "http://{0}"
0x9e4d  ldc.i4.1
0x9e4e  newarr   [mscorlib]System.Object
0x9e53  dup
0x9e54  ldc.i4.0
0x9e55  ldloc.s  6
0x9e57  callvirt instance string [System]System.Uri::get_Host()
0x9e5c  stelem.ref
0x9e5d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9e62  stelem.ref
0x9e63  dup
0x9e64  ldc.i4.5
0x9e65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e6a  ldstr    aHttp0_0// "http://{0}/"
0x9e6f  ldc.i4.1
0x9e70  newarr   [mscorlib]System.Object
0x9e75  dup
0x9e76  ldc.i4.0
0x9e77  ldloc.s  6
0x9e79  callvirt instance string [System]System.Uri::get_Host()
0x9e7e  stelem.ref
0x9e7f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9e84  stelem.ref
0x9e85  dup
0x9e86  ldc.i4.6
0x9e87  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e8c  ldstr    aHttp0// "http://{0}"
0x9e91  ldc.i4.1
0x9e92  newarr   [mscorlib]System.Object
0x9e97  dup
0x9e98  ldc.i4.0
0x9e99  ldloc.s  6
0x9e9b  callvirt instance string [System]System.Uri::get_Authority()
0x9ea0  stelem.ref
0x9ea1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9ea6  stelem.ref
0x9ea7  dup
0x9ea8  ldc.i4.7
0x9ea9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9eae  ldstr    aHttp0_0// "http://{0}/"
0x9eb3  ldc.i4.1
0x9eb4  newarr   [mscorlib]System.Object
0x9eb9  dup
0x9eba  ldc.i4.0
0x9ebb  ldloc.s  6
0x9ebd  callvirt instance string [System]System.Uri::get_Authority()
0x9ec2  stelem.ref
0x9ec3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9ec8  stelem.ref
0x9ec9  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::set_ValidAudiences(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x9ece  ldarg.3
0x9ecf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::get_ValidAudiences()
0x9ed4  stloc.0
0x9ed5  ldarg.0
0x9ed6  ldloc.2
0x9ed7  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::AddCustomTokenAudiences(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken jwt)
0x9edc  stloc.3
0x9edd  ldloc.3
0x9ede  ldarg.1
0x9edf  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__3_0
0x9ee4  dup
0x9ee5  brtrue.s loc_9EFE
0x9ee7  pop
0x9ee8  ldsfld   class <>c <>c::<>9
0x9eed  ldftn    instance string <>c::<ValidateAudience>b__3_0(string a)
0x9ef3  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x9ef8  dup
0x9ef9  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__3_0
0x9efe  call     T0x2B000017
0x9f03  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9f08  ldarg.0
0x9f09  ldloc.2
0x9f0a  ldloc.3
0x9f0b  ldloc.0
0x9f0c  callvirt instance bool Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::ValidateCustomAudience(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken jwt, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> tokenAudiences, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> audiences)
0x9f11  brfalse.s loc_9F14
0x9f13  ret
0x9f14  ldloc.1
0x9f15  brtrue.s loc_9F20
0x9f17  ldloc.3
0x9f18  ldloc.0
0x9f19  call     bool Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateAudience(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> urlsToCheck, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> allowedAudienceUris)
0x9f1e  brtrue.s loc_9F29
0x9f20  ldarg.0
0x9f21  ldloc.3
0x9f22  ldarg.2
0x9f23  ldarg.3
0x9f24  call     instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityTokenHandler::ValidateAudience(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken, class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters)
0x9f29  ret
```
