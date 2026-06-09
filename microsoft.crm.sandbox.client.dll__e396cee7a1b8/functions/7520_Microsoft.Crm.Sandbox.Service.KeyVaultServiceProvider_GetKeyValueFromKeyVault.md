# Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::GetKeyValueFromKeyVault

- ea: `0x7520`
- end: `0x7606`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::GetKeyValueFromKeyVault`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x7200`
- `0x74d0`
- `0x7520`
- `0x7610`

## string_xrefs

- `0x7573`: `KeyVaultServiceProvider.GetKeyValueFromKeyVault error getting {0}`
- `0x75ac`: `KeyVaultServiceProvider.GetKeyValueFromKeyVault error getting {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7520  ldarg.3
0x7521  ldstr    aKey1// "key1"
0x7526  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x752b  ldarg.s  4
0x752d  ldstr    aKey2// "key2"
0x7532  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7537  ldarg.0
0x7538  ldarg.1
0x7539  call     instance void Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::CheckKeyVaultURI(string keyVaultUri)
0x753e  ldarg.0
0x753f  ldfld    class Microsoft.Crm.Sandbox.Service.IKeyVaultClientFactory Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::keyVaultClientFactory
0x7544  callvirt instance class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient Microsoft.Crm.Sandbox.Service.IKeyVaultClientFactory::CreateKeyVaultClient()
0x7549  stloc.0
0x754a  ldnull
0x754b  stloc.1
0x754c  ldnull
0x754d  stloc.2
0x754e  ldloc.0
0x754f  ldarg.1
0x7550  ldarg.3
0x7551  ldnull
0x7552  ldloca.s 3
0x7554  initobj  [mscorlib]System.Threading.CancellationToken
0x755a  ldloc.3
0x755b  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret> [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient::GetSecretAsync(string, string, string, valuetype [mscorlib]System.Threading.CancellationToken)
0x7560  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret>::get_Result()
0x7565  callvirt instance string [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret::get_Value()
0x756a  stloc.1
0x756b  leave.s  loc_7585
0x756d  stloc.s  4
0x756f  ldarg.0
0x7570  ldloc.s  4
0x7572  ldarg.2
0x7573  ldstr    aKeyvaultservic_1// "KeyVaultServiceProvider.GetKeyValueFrom"...
0x7578  ldarg.3
0x7579  call     string [mscorlib]System.String::Format(string, object)
0x757e  call     instance void Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::ProcessAggregateExceptionTrace(class [mscorlib]System.AggregateException aggregateException, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, string message)
0x7583  leave.s  loc_7585
0x7585  nop
0x7586  ldloc.0
0x7587  ldarg.1
0x7588  ldarg.s  4
0x758a  ldnull
0x758b  ldloca.s 3
0x758d  initobj  [mscorlib]System.Threading.CancellationToken
0x7593  ldloc.3
0x7594  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret> [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient::GetSecretAsync(string, string, string, valuetype [mscorlib]System.Threading.CancellationToken)
0x7599  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret>::get_Result()
0x759e  callvirt instance string [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret::get_Value()
0x75a3  stloc.2
0x75a4  leave.s  loc_75BF
0x75a6  stloc.s  5
0x75a8  ldarg.0
0x75a9  ldloc.s  5
0x75ab  ldarg.2
0x75ac  ldstr    aKeyvaultservic_1// "KeyVaultServiceProvider.GetKeyValueFrom"...
0x75b1  ldarg.s  4
0x75b3  call     string [mscorlib]System.String::Format(string, object)
0x75b8  call     instance void Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::ProcessAggregateExceptionTrace(class [mscorlib]System.AggregateException aggregateException, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, string message)
0x75bd  leave.s  loc_75BF
0x75bf  ldloc.1
0x75c0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75c5  brfalse.s loc_75DD
0x75c7  ldstr    a0IsMissing// "{0} is missing"
0x75cc  ldarg.3
0x75cd  call     string [mscorlib]System.String::Format(string, object)
0x75d2  ldc.i4   0x8009100C
0x75d7  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmKeyVaultException::.ctor(string, int32)
0x75dc  throw
0x75dd  ldloc.2
0x75de  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75e3  brfalse.s loc_75FC
0x75e5  ldstr    a0IsMissing// "{0} is missing"
0x75ea  ldarg.s  4
0x75ec  call     string [mscorlib]System.String::Format(string, object)
0x75f1  ldc.i4   0x8009100C
0x75f6  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmKeyVaultException::.ctor(string, int32)
0x75fb  throw
0x75fc  ldarg.s  5
0x75fe  ldloc.1
0x75ff  ldloc.2
0x7600  callvirt instance var<u1> class [mscorlib]System.Func`3<string, string, mvar<u1>>::Invoke(bool, var<u1>)
0x7605  ret
```
