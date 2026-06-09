# Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::GetSecret

- ea: `0x7350`
- end: `0x73a0`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::GetSecret`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7200`
- `0x7350`
- `0x7610`

## string_xrefs

- `0x738a`: `KeyVaultServiceProvider.GetSecret error getting {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7350  ldarg.2
0x7351  ldstr    aSecretname// "secretName"
0x7356  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x735b  ldarg.0
0x735c  ldfld    class Microsoft.Crm.Sandbox.Service.IKeyVaultClientFactory Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::keyVaultClientFactory
0x7361  callvirt instance class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient Microsoft.Crm.Sandbox.Service.IKeyVaultClientFactory::CreateKeyVaultClient()
0x7366  stloc.0
0x7367  ldloc.0
0x7368  ldarg.1
0x7369  ldarg.2
0x736a  ldnull
0x736b  ldloca.s 1
0x736d  initobj  [mscorlib]System.Threading.CancellationToken
0x7373  ldloc.1
0x7374  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret> [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient::GetSecretAsync(string, string, string, valuetype [mscorlib]System.Threading.CancellationToken)
0x7379  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret>::get_Result()
0x737e  callvirt instance string [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret::get_Value()
0x7383  stloc.2
0x7384  leave.s  loc_739E
0x7386  stloc.3
0x7387  ldarg.0
0x7388  ldloc.3
0x7389  ldarg.3
0x738a  ldstr    aKeyvaultservic// "KeyVaultServiceProvider.GetSecret error"...
0x738f  ldarg.2
0x7390  call     string [mscorlib]System.String::Format(string, object)
0x7395  call     instance void Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::ProcessAggregateExceptionTrace(class [mscorlib]System.AggregateException aggregateException, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, string message)
0x739a  ldnull
0x739b  stloc.2
0x739c  leave.s  loc_739E
0x739e  ldloc.2
0x739f  ret
```
