# Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::ValidateSignOnTokenNonceForNewSession

- ea: `0x9290`
- end: `0x93ed`
- name: `Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::ValidateSignOnTokenNonceForNewSession`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x7780`
- `0x9230`
- `0x9290`
- `0x9550`
- `0x95c0`
- `0x9800`

## string_xrefs

- `0x933b`: `NonceValidator.ValidateSignOnTokenNonceForNewSession Unable to find nonce context!`
- `0x9388`: `NonceValidator.ValidateSignOnTokenNonceForNewSession Nonce context is invalid!`
- `0x93cd`: `NonceValidator.ValidateSGetNonceKeyignOnTokenNonceForNewSession Unable to find session nonce for session!`

## pseudocode

```c

```

## disassembly

```asm
0x9290  ldarg.1
0x9291  ldstr    aContext// "context"
0x9296  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x929b  ldarg.2
0x929c  ldstr    aPrincipal// "principal"
0x92a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x92a6  ldarg.0
0x92a7  ldarg.2
0x92a8  call     instance bool Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::BypassKnownClients(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x92ad  brfalse.s loc_92B1
0x92af  ldc.i4.1
0x92b0  ret
0x92b1  ldarg.1
0x92b2  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x92b7  ldstr    aWctx// "wctx"
0x92bc  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x92c1  stloc.0
0x92c2  ldsfld   string [mscorlib]System.String::Empty
0x92c7  stloc.1
0x92c8  ldloc.0
0x92c9  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x92ce  brtrue.s loc_932E
0x92d0  ldloc.0
0x92d1  call     class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpUtility::ParseQueryString(string)
0x92d6  stloc.3
0x92d7  ldloc.3
0x92d8  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x92dd  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0x92e2  stloc.s  4
0x92e4  br.s     loc_930E
0x92e6  ldloc.s  4
0x92e8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x92ed  castclass [mscorlib]System.String
0x92f2  stloc.s  5
0x92f4  ldloc.s  5
0x92f6  ldstr    aNonce// "nonce"
0x92fb  ldc.i4.5
0x92fc  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x9301  brtrue.s loc_930E
0x9303  ldloc.3
0x9304  ldloc.s  5
0x9306  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x930b  stloc.1
0x930c  leave.s  loc_932E
0x930e  ldloc.s  4
0x9310  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9315  brtrue.s loc_92E6
0x9317  leave.s  loc_932E
0x9319  ldloc.s  4
0x931b  isinst   [mscorlib]System.IDisposable
0x9320  stloc.s  6
0x9322  ldloc.s  6
0x9324  brfalse.s loc_932D
0x9326  ldloc.s  6
0x9328  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x932d  endfinally
0x932e  ldloc.1
0x932f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x9334  brfalse.s loc_9352
0x9336  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x933b  ldstr    aNoncevalidator// "NonceValidator.ValidateSignOnTokenNonce"...
0x9340  ldc.i4.0
0x9341  newarr   [mscorlib]System.Object
0x9346  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x934b  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x9350  ldc.i4.0
0x9351  ret
0x9352  ldloc.1
0x9353  ldarg.0
0x9354  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x9359  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GetNoncePrefix()
0x935e  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x9363  brfalse.s loc_9383
0x9365  ldloc.1
0x9366  ldc.i4.0
0x9367  ldarg.0
0x9368  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x936d  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GetNoncePrefix()
0x9372  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9377  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0x937c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x9381  brfalse.s loc_939F
0x9383  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9388  ldstr    aNoncevalidator_0// "NonceValidator.ValidateSignOnTokenNonce"...
0x938d  ldc.i4.0
0x938e  newarr   [mscorlib]System.Object
0x9393  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9398  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x939d  ldc.i4.0
0x939e  ret
0x939f  ldloc.1
0x93a0  ldc.i4.0
0x93a1  ldarg.0
0x93a2  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x93a7  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GetNoncePrefix()
0x93ac  callvirt instance int32 [mscorlib]System.String::get_Length()
0x93b1  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0x93b6  stloc.1
0x93b7  ldarg.0
0x93b8  ldarg.1
0x93b9  ldloc.1
0x93ba  call     instance string Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::RetrieveSessionNonce(class [System.Web]System.Web.HttpContext context, string nonce)
0x93bf  stloc.2
0x93c0  ldloc.2
0x93c1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x93c6  brfalse.s loc_93E4
0x93c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x93cd  ldstr    aNoncevalidator_1// "NonceValidator.ValidateSGetNonceKeyignO"...
0x93d2  ldc.i4.0
0x93d3  newarr   [mscorlib]System.Object
0x93d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x93dd  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x93e2  ldc.i4.0
0x93e3  ret
0x93e4  ldarg.0
0x93e5  ldloc.2
0x93e6  ldloc.1
0x93e7  call     instance bool Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::ValidateNonce(string requiredNonce, string nonce)
0x93ec  ret
```
