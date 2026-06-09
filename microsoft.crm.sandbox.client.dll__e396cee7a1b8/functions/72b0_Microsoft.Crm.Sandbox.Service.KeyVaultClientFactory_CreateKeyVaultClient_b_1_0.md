# Microsoft.Crm.Sandbox.Service.KeyVaultClientFactory::<CreateKeyVaultClient>b__1_0

- ea: `0x72b0`
- end: `0x72cd`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultClientFactory::<CreateKeyVaultClient>b__1_0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7240`

## pseudocode

```c

```

## disassembly

```asm
0x72b0  ldarg.1
0x72b1  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::.ctor(string)
0x72b6  ldarg.2
0x72b7  ldarg.0
0x72b8  call     instance class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate Microsoft.Crm.Sandbox.Service.KeyVaultClientFactory::GetCRMCredentials()
0x72bd  callvirt instance class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::AcquireToken(string, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate)
0x72c2  callvirt instance string [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult::get_AccessToken()
0x72c7  call     T0x2B000017
0x72cc  ret
```
