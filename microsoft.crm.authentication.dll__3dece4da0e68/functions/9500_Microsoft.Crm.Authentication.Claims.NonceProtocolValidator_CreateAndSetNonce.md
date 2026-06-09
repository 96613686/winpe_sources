# Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::CreateAndSetNonce

- ea: `0x9500`
- end: `0x954b`
- name: `Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::CreateAndSetNonce`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x8f00`
- `0x94e0`
- `0x97e0`
- `0x97f0`
- `0x9800`
- `0x9820`

## pseudocode

```c

```

## disassembly

```asm
0x9500  ldarg.0
0x9501  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x9506  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GenerateNonce()
0x950b  stloc.0
0x950c  ldarg.0
0x950d  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x9512  ldloc.0
0x9513  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GetNonceKey(string nonce)
0x9518  stloc.1
0x9519  ldarg.0
0x951a  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x951f  ldloc.0
0x9520  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::Encode(string nonce)
0x9525  stloc.2
0x9526  ldarg.0
0x9527  callvirt instance class Microsoft.Crm.Authentication.Claims.INonceCookieHandler Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::get_NonceCookieHandler()
0x952c  ldloc.2
0x952d  ldloc.1
0x952e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x9533  ldarg.1
0x9534  callvirt instance void Microsoft.Crm.Authentication.Claims.INonceCookieHandler::Write(string encodedValue, string name, class [System.Web]System.Web.HttpContext context)
0x9539  ldarg.0
0x953a  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_nonceProvider
0x953f  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GetNoncePrefix()
0x9544  ldloc.0
0x9545  call     string [mscorlib]System.String::Concat(string, string)
0x954a  ret
```
