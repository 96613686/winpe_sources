# Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultProviderModule::RegisterSecretLookup

- ea: `0x1c50`
- end: `0x1c87`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultProviderModule::RegisterSecretLookup`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1b80`

## pseudocode

```c

```

## disassembly

```asm
0x1c50  ldarg.1
0x1c51  call     T0x2B000041
0x1c56  ldstr    aSecretlookupIn// "SecretLookup.Inner"
0x1c5b  callvirt T0x2B000042
0x1c60  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1c65  pop
0x1c66  ldarg.1
0x1c67  call     T0x2B000043
0x1c6c  ldstr    aSecretlookupIn// "SecretLookup.Inner"
0x1c71  call     T0x2B000044
0x1c76  call     T0x2B000045
0x1c7b  callvirt T0x2B000046
0x1c80  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1c85  pop
0x1c86  ret
```
