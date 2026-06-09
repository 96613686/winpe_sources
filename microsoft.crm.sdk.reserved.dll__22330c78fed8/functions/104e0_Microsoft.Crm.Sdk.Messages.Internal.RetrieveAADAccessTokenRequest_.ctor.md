# Microsoft.Crm.Sdk.Messages.Internal.RetrieveAADAccessTokenRequest::.ctor

- ea: `0x104e0`
- end: `0x10507`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveAADAccessTokenRequest::.ctor`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x10420`
- `0x10470`
- `0x104c0`

## string_xrefs

- `0x104e7`: `RetrieveAADAccessToken`

## pseudocode

```c

```

## disassembly

```asm
0x104e0  ldarg.0
0x104e1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x104e6  ldarg.0
0x104e7  ldstr    aRetrieveaadacc// "RetrieveAADAccessToken"
0x104ec  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x104f1  ldarg.0
0x104f2  ldnull
0x104f3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RetrieveAADAccessTokenRequest::set_ClientId(string value)
0x104f8  ldarg.0
0x104f9  ldnull
0x104fa  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RetrieveAADAccessTokenRequest::set_ServerId(string value)
0x104ff  ldarg.0
0x10500  ldnull
0x10501  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RetrieveAADAccessTokenRequest::set_Tenant(string value)
0x10506  ret
```
