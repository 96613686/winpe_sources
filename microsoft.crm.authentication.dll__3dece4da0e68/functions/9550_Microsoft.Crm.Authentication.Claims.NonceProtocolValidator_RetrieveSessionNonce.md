# Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::RetrieveSessionNonce

- ea: `0x9550`
- end: `0x95ba`
- name: `Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::RetrieveSessionNonce`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x9290`
- `0x93f0`

## callees

- `0x7780`
- `0x8ef0`
- `0x8f10`
- `0x94e0`
- `0x9550`
- `0x97e0`
- `0x9810`

## pseudocode

```c

```

## disassembly

```asm
0x9550  ldarg.0
0x9551  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x9556  ldarg.2
0x9557  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GetNonceKey(string nonce)
0x955c  stloc.0
0x955d  ldloc.0
0x955e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x9563  brfalse.s loc_9581
0x9565  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x956a  ldstr    aNoncevalidator_3// "NonceValidator.ValidateSessionNonce Una"...
0x956f  ldc.i4.0
0x9570  newarr   [mscorlib]System.Object
0x9575  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x957a  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x957f  ldnull
0x9580  ret
0x9581  ldloc.0
0x9582  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x9587  stloc.1
0x9588  ldarg.0
0x9589  callvirt instance class Microsoft.Crm.Authentication.Claims.INonceCookieHandler Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::get_NonceCookieHandler()
0x958e  ldloc.1
0x958f  ldarg.1
0x9590  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceCookieHandler::Read(string name, class [System.Web]System.Web.HttpContext context)
0x9595  stloc.2
0x9596  ldloc.2
0x9597  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x959c  brfalse.s loc_95A0
0x959e  ldnull
0x959f  ret
0x95a0  ldarg.0
0x95a1  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x95a6  ldloc.2
0x95a7  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::Decode(string nonceCookie)
0x95ac  ldarg.0
0x95ad  callvirt instance class Microsoft.Crm.Authentication.Claims.INonceCookieHandler Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::get_NonceCookieHandler()
0x95b2  ldloc.1
0x95b3  ldarg.1
0x95b4  callvirt instance void Microsoft.Crm.Authentication.Claims.INonceCookieHandler::Delete(string name, class [System.Web]System.Web.HttpContext context)
0x95b9  ret
```
