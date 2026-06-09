# Microsoft.Crm.Sandbox.Service.KeyVaultClientFactory::CreateKeyVaultClient

- ea: `0x7220`
- end: `0x7232`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultClientFactory::CreateKeyVaultClient`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x7220  ldarg.0
0x7221  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Crm.Sandbox.Service.KeyVaultClientFactory::<CreateKeyVaultClient>b__1_0(string authority, string resource, string scope)
0x7227  newobj   instance void [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient/AuthenticationCallback::.ctor(object, native int)
0x722c  newobj   instance void [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient::.ctor(class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient/AuthenticationCallback)
0x7231  ret
```
