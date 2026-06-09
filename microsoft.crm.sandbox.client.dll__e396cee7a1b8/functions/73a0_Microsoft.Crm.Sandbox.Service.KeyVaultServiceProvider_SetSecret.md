# Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::SetSecret

- ea: `0x73a0`
- end: `0x73eb`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::SetSecret`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7200`
- `0x73a0`
- `0x7610`

## string_xrefs

- `0x73d8`: `KeyVaultServiceProvider.SetSecret error setting {0}`

## pseudocode

```c

```

## disassembly

```asm
0x73a0  ldarg.2
0x73a1  ldstr    aSecretname// "secretName"
0x73a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x73ab  ldarg.0
0x73ac  ldfld    class Microsoft.Crm.Sandbox.Service.IKeyVaultClientFactory Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::keyVaultClientFactory
0x73b1  callvirt instance class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient Microsoft.Crm.Sandbox.Service.IKeyVaultClientFactory::CreateKeyVaultClient()
0x73b6  stloc.0
0x73b7  ldloc.0
0x73b8  ldarg.1
0x73b9  ldarg.2
0x73ba  ldarg.3
0x73bb  ldnull
0x73bc  ldnull
0x73bd  ldnull
0x73be  ldloca.s 1
0x73c0  initobj  [mscorlib]System.Threading.CancellationToken
0x73c6  ldloc.1
0x73c7  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret> [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient::SetSecretAsync(string, string, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>, string, class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.SecretAttributes, valuetype [mscorlib]System.Threading.CancellationToken)
0x73cc  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Wait()
0x73d1  leave.s  loc_73EA
0x73d3  stloc.2
0x73d4  ldarg.0
0x73d5  ldloc.2
0x73d6  ldarg.s  4
0x73d8  ldstr    aKeyvaultservic_0// "KeyVaultServiceProvider.SetSecret error"...
0x73dd  ldarg.2
0x73de  call     string [mscorlib]System.String::Format(string, object)
0x73e3  call     instance void Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::ProcessAggregateExceptionTrace(class [mscorlib]System.AggregateException aggregateException, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, string message)
0x73e8  leave.s  loc_73EA
0x73ea  ret
```
