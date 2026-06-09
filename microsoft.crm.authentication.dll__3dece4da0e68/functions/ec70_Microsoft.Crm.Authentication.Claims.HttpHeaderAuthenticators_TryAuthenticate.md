# Microsoft.Crm.Authentication.Claims.HttpHeaderAuthenticators::TryAuthenticate

- ea: `0xec70`
- end: `0xedd7`
- name: `Microsoft.Crm.Authentication.Claims.HttpHeaderAuthenticators::TryAuthenticate`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xebd0`

## callees

- `0x7780`
- `0xec50`
- `0xec70`
- `0xf700`
- `0xf710`
- `0xf770`
- `0xf940`

## string_xrefs

- `0xecbc`: `HttpHeaderAuthenticators.TryAuthenticate: failed. TryReadAndValidateToken returned false.`
- `0xecc8`: `HttpHeaderAuthenticators.TryAuthenticate: failed. AccessToken is null.`
- `0xecdd`: `HttpHeaderAuthenticators.TryAuthenticate: SecurityTokenNotYetValidException encountered validating token: {0}, {1}`
- `0xecfb`: `invalid_token`
- `0xed38`: `invalid_token`
- `0xed75`: `invalid_token`
- `0xedaf`: `invalid_token`
- `0xed00`: `Security Token Not Yet Valid!`
- `0xed19`: `HttpHeaderAuthenticators.TryAuthenticate: SecurityTokenExpiredException encountered validating token: {0}, {1}`
- `0xed3d`: `Security Token Expired!`
- `0xed56`: `HttpHeaderAuthenticators.TryAuthenticate: SecurityTokenValidationException encountered validating token: {0}, {1}`
- `0xed7a`: `Security Token Validation Failed!`
- `0xed90`: `HttpHeaderAuthenticators.TryAuthenticate: Exception encountered validating token: {0}, {1}`
- `0xedb4`: `Error during token validation!`

## pseudocode

```c

```

## disassembly

```asm
0xec70  ldarg.2
0xec71  ldnull
0xec72  stind.ref
0xec73  ldarg.1
0xec74  brfalse  loc_EDC3
0xec79  ldarg.0
0xec7a  ldarg.1
0xec7b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xec80  call     instance class Microsoft.Crm.Authentication.Claims.IHttpHeaderAuthenticatorInstance Microsoft.Crm.Authentication.Claims.HttpHeaderAuthenticators::GetAuthenticator(class [System.Web]System.Web.HttpRequest request)
0xec85  stloc.0
0xec86  ldloc.0
0xec87  brtrue.s loc_EC95
0xec89  ldstr    aHttpheaderauth// "HttpHeaderAuthenticators.TryAuthenticat"...
0xec8e  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xec93  ldc.i4.0
0xec94  ret
0xec95  nop
0xec96  ldloc.0
0xec97  ldarg.1
0xec98  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xec9d  callvirt instance string Microsoft.Crm.Authentication.Claims.IHttpHeaderAuthenticatorInstance::GetTokenFromAuthorizationHeader(class [System.Web]System.Web.HttpRequest request)
0xeca2  stloc.1
0xeca3  ldloc.1
0xeca4  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xeca9  brtrue.s loc_ECC8
0xecab  ldloc.0
0xecac  ldloc.1
0xecad  ldarg.2
0xecae  callvirt instance bool Microsoft.Crm.Authentication.Claims.IHttpHeaderAuthenticatorInstance::TryReadAndValidateToken(string accessToken, [out] class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken& sessionSecurityToken)
0xecb3  brfalse.s loc_ECBC
0xecb5  ldc.i4.1
0xecb6  stloc.2
0xecb7  leave    loc_EDD5
0xecbc  ldstr    aHttpheaderauth_0// "HttpHeaderAuthenticators.TryAuthenticat"...
0xecc1  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xecc6  br.s     loc_ECD2
0xecc8  ldstr    aHttpheaderauth_1// "HttpHeaderAuthenticators.TryAuthenticat"...
0xeccd  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xecd2  leave    loc_EDCD
0xecd7  stloc.3
0xecd8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xecdd  ldstr    aHttpheaderauth_2// "HttpHeaderAuthenticators.TryAuthenticat"...
0xece2  ldc.i4.2
0xece3  newarr   [mscorlib]System.Object
0xece8  dup
0xece9  ldc.i4.0
0xecea  ldarg.0
0xeceb  stelem.ref
0xecec  dup
0xeced  ldc.i4.1
0xecee  ldloc.3
0xecef  stelem.ref
0xecf0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xecf5  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xecfa  ldarg.1
0xecfb  ldstr    aInvalidToken// "invalid_token"
0xed00  ldstr    aSecurityTokenN// "Security Token Not Yet Valid!"
0xed05  ldc.i4.1
0xed06  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendErrorResponse(class [System.Web]System.Web.HttpContext context, string errorCode, string errorDescription, bool sendAuthRequired)
0xed0b  ldc.i4.0
0xed0c  stloc.2
0xed0d  leave    loc_EDD5
0xed12  stloc.s  4
0xed14  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xed19  ldstr    aHttpheaderauth_3// "HttpHeaderAuthenticators.TryAuthenticat"...
0xed1e  ldc.i4.2
0xed1f  newarr   [mscorlib]System.Object
0xed24  dup
0xed25  ldc.i4.0
0xed26  ldarg.0
0xed27  stelem.ref
0xed28  dup
0xed29  ldc.i4.1
0xed2a  ldloc.s  4
0xed2c  stelem.ref
0xed2d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xed32  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xed37  ldarg.1
0xed38  ldstr    aInvalidToken// "invalid_token"
0xed3d  ldstr    aSecurityTokenE// "Security Token Expired!"
0xed42  ldc.i4.1
0xed43  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendErrorResponse(class [System.Web]System.Web.HttpContext context, string errorCode, string errorDescription, bool sendAuthRequired)
0xed48  ldc.i4.0
0xed49  stloc.2
0xed4a  leave    loc_EDD5
0xed4f  stloc.s  5
0xed51  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xed56  ldstr    aHttpheaderauth_4// "HttpHeaderAuthenticators.TryAuthenticat"...
0xed5b  ldc.i4.2
0xed5c  newarr   [mscorlib]System.Object
0xed61  dup
0xed62  ldc.i4.0
0xed63  ldarg.0
0xed64  stelem.ref
0xed65  dup
0xed66  ldc.i4.1
0xed67  ldloc.s  5
0xed69  stelem.ref
0xed6a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xed6f  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xed74  ldarg.1
0xed75  ldstr    aInvalidToken// "invalid_token"
0xed7a  ldstr    aSecurityTokenV// "Security Token Validation Failed!"
0xed7f  ldc.i4.1
0xed80  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendErrorResponse(class [System.Web]System.Web.HttpContext context, string errorCode, string errorDescription, bool sendAuthRequired)
0xed85  ldc.i4.0
0xed86  stloc.2
0xed87  leave.s  loc_EDD5
0xed89  stloc.s  6
0xed8b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xed90  ldstr    aHttpheaderauth_5// "HttpHeaderAuthenticators.TryAuthenticat"...
0xed95  ldc.i4.2
0xed96  newarr   [mscorlib]System.Object
0xed9b  dup
0xed9c  ldc.i4.0
0xed9d  ldarg.0
0xed9e  stelem.ref
0xed9f  dup
0xeda0  ldc.i4.1
0xeda1  ldloc.s  6
0xeda3  stelem.ref
0xeda4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xeda9  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xedae  ldarg.1
0xedaf  ldstr    aInvalidToken// "invalid_token"
0xedb4  ldstr    aErrorDuringTok// "Error during token validation!"
0xedb9  ldc.i4.1
0xedba  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendErrorResponse(class [System.Web]System.Web.HttpContext context, string errorCode, string errorDescription, bool sendAuthRequired)
0xedbf  ldc.i4.0
0xedc0  stloc.2
0xedc1  leave.s  loc_EDD5
0xedc3  ldstr    aHttpheaderauth_6// "HttpHeaderAuthenticators.TryAuthenticat"...
0xedc8  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xedcd  ldarg.1
0xedce  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendAuthRequiredResponse(class [System.Web]System.Web.HttpContext context)
0xedd3  ldc.i4.0
0xedd4  ret
0xedd5  ldloc.2
0xedd6  ret
```
