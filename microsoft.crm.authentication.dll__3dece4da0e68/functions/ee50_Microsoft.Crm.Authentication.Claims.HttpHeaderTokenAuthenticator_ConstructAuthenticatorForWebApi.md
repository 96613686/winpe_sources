# Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::ConstructAuthenticatorForWebApi

- ea: `0xee50`
- end: `0xee69`
- name: `Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::ConstructAuthenticatorForWebApi`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xee30`
- `0xee80`
- `0xeea0`
- `0xf460`

## pseudocode

```c

```

## disassembly

```asm
0xee50  newobj   instance void Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::.ctor()
0xee55  dup
0xee56  ldc.i4.0
0xee57  newobj   instance void Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::.ctor(bool loadCrmServiceConfiguration)
0xee5c  callvirt instance void Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::set_Handler(class Microsoft.Crm.Authentication.Claims.IHttpHeaderTokenHandler value)
0xee61  dup
0xee62  ldc.i4.0
0xee63  callvirt instance void Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::set_SetCrmIdentityClaims(bool value)
0xee68  ret
```
