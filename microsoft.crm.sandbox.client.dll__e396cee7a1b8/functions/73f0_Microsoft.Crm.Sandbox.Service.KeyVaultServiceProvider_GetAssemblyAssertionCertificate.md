# Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::GetAssemblyAssertionCertificate

- ea: `0x73f0`
- end: `0x744e`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::GetAssemblyAssertionCertificate`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x73f0`
- `0x74b0`

## string_xrefs

- `0x73fc`: `keyVaultUri`

## pseudocode

```c

```

## disassembly

```asm
0x73f0  ldarg.1
0x73f1  ldstr    aAssemblyname// "assemblyName"
0x73f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x73fb  ldarg.2
0x73fc  ldstr    aKeyvaulturi// "keyVaultUri"
0x7401  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7406  ldarg.0
0x7407  ldarg.1
0x7408  call     instance object Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::RemoveInvalidCharactersFromAssemblyName(string assemblyName)
0x740d  dup
0x740e  ldstr    aAppid// "-AppId"
0x7413  call     string [mscorlib]System.String::Concat(object, object)
0x7418  stloc.0
0x7419  ldstr    aCert// "-Cert"
0x741e  call     string [mscorlib]System.String::Concat(object, object)
0x7423  stloc.1
0x7424  ldarg.0
0x7425  ldarg.2
0x7426  ldarg.3
0x7427  ldloc.0
0x7428  ldloc.1
0x7429  ldsfld   class [mscorlib]System.Func`3<string, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCertificate> <>c::<>9__8_0
0x742e  dup
0x742f  brtrue.s loc_7448
0x7431  pop
0x7432  ldsfld   class <>c <>c::<>9
0x7437  ldftn    instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCertificate <>c::<GetAssemblyAssertionCertificate>b__8_0(string appId, string base64Certificate)
0x743d  newobj   instance void class [mscorlib]System.Func`3<string, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCertificate>::.ctor(object, native int)
0x7442  dup
0x7443  stsfld   class [mscorlib]System.Func`3<string, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCertificate> <>c::<>9__8_0
0x7448  call     T0x2B000018
0x744d  ret
```
