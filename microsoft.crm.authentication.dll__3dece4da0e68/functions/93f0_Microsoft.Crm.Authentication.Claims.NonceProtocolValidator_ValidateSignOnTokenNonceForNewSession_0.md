# Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::ValidateSignOnTokenNonceForNewSession_0

- ea: `0x93f0`
- end: `0x94d1`
- name: `Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::ValidateSignOnTokenNonceForNewSession_0`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x7780`
- `0x9230`
- `0x93f0`
- `0x9550`
- `0x95c0`
- `0x9800`

## string_xrefs

- `0x941e`: `NonceValidator.ValidateSignOnTokenNonceForNewSession Unable to find nonce context!`
- `0x946b`: `NonceValidator.ValidateSignOnTokenNonceForNewSession Nonce context is invalid!`
- `0x94b1`: `NonceValidator.ValidateSignOnTokenNonceForNewSession Unable to find session nonce for session!`

## pseudocode

```c

```

## disassembly

```asm
0x93f0  ldarg.2
0x93f1  ldstr    aContext// "context"
0x93f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x93fb  ldarg.3
0x93fc  ldstr    aPrincipal// "principal"
0x9401  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9406  ldarg.0
0x9407  ldarg.3
0x9408  call     instance bool Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::BypassKnownClients(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x940d  brfalse.s loc_9411
0x940f  ldc.i4.1
0x9410  ret
0x9411  ldarg.1
0x9412  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x9417  brfalse.s loc_9435
0x9419  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x941e  ldstr    aNoncevalidator// "NonceValidator.ValidateSignOnTokenNonce"...
0x9423  ldc.i4.0
0x9424  newarr   [mscorlib]System.Object
0x9429  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x942e  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x9433  ldc.i4.0
0x9434  ret
0x9435  ldarg.1
0x9436  ldarg.0
0x9437  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x943c  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GetNoncePrefix()
0x9441  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x9446  brfalse.s loc_9466
0x9448  ldarg.1
0x9449  ldc.i4.0
0x944a  ldarg.0
0x944b  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x9450  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GetNoncePrefix()
0x9455  callvirt instance int32 [mscorlib]System.String::get_Length()
0x945a  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0x945f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x9464  brfalse.s loc_9482
0x9466  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x946b  ldstr    aNoncevalidator_0// "NonceValidator.ValidateSignOnTokenNonce"...
0x9470  ldc.i4.0
0x9471  newarr   [mscorlib]System.Object
0x9476  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x947b  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x9480  ldc.i4.0
0x9481  ret
0x9482  ldarg.1
0x9483  ldc.i4.0
0x9484  ldarg.0
0x9485  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x948a  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GetNoncePrefix()
0x948f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9494  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0x9499  starg.s  1
0x949b  ldarg.0
0x949c  ldarg.2
0x949d  ldarg.1
0x949e  call     instance string Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::RetrieveSessionNonce(class [System.Web]System.Web.HttpContext context, string nonce)
0x94a3  stloc.0
0x94a4  ldloc.0
0x94a5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x94aa  brfalse.s loc_94C8
0x94ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x94b1  ldstr    aNoncevalidator_2// "NonceValidator.ValidateSignOnTokenNonce"...
0x94b6  ldc.i4.0
0x94b7  newarr   [mscorlib]System.Object
0x94bc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x94c1  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x94c6  ldc.i4.0
0x94c7  ret
0x94c8  ldarg.0
0x94c9  ldloc.0
0x94ca  ldarg.1
0x94cb  call     instance bool Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::ValidateNonce(string requiredNonce, string nonce)
0x94d0  ret
```
