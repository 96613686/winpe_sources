# Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::.ctor

- ea: `0xee30`
- end: `0xee49`
- name: `Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::.ctor`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xeb70`
- `0xee50`

## callees

- `0xee80`
- `0xeea0`
- `0xf440`

## pseudocode

```c

```

## disassembly

```asm
0xee30  ldarg.0
0xee31  call     instance void [mscorlib]System.Object::.ctor()
0xee36  ldarg.0
0xee37  newobj   instance void Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::.ctor()
0xee3c  call     instance void Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::set_Handler(class Microsoft.Crm.Authentication.Claims.IHttpHeaderTokenHandler value)
0xee41  ldarg.0
0xee42  ldc.i4.1
0xee43  call     instance void Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::set_SetCrmIdentityClaims(bool value)
0xee48  ret
```
