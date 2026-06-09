# Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::ApplyTransportSecurity

- ea: `0x1000`
- end: `0x1016`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::ApplyTransportSecurity`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1850`

## string_xrefs

- `0x1000`: `ID3227: Issued token authentication is not supported for Transport security. IssuedTokenWSTrustBinding.SecurityMode must be set to 'Message' or 'TransportWithMessageCredential'.`

## pseudocode

```c

```

## disassembly

```asm
0x1000  ldstr    aId3227IssuedTo// "ID3227: Issued token authentication is "...
0x1005  ldc.i4.0
0x1006  newarr   [mscorlib]System.Object
0x100b  call     string Microsoft.Crm.Protocols.WSTrust.Bindings.ClientExceptionHelper::GetString(string value, object[] args)
0x1010  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1015  throw
```
