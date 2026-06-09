# Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultProviderModule::Load

- ea: `0x1b80`
- end: `0x1c4e`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultProviderModule::Load`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1b60`
- `0x1b80`
- `0x1c50`

## pseudocode

```c

```

## disassembly

```asm
0x1b80  ldarg.1
0x1b81  call     T0x2B00002F
0x1b86  callvirt T0x2B000030
0x1b8b  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommon.SecureStringConverter, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1b90  pop
0x1b91  ldarg.1
0x1b92  ldsfld   class [mscorlib]System.Func`2<class [Autofac]Autofac.IComponentContext, class [mscorlib]System.StringComparer> <>c::<>9__5_0
0x1b97  dup
0x1b98  brtrue.s loc_1BB1
0x1b9a  pop
0x1b9b  ldsfld   class <>c <>c::<>9
0x1ba0  ldftn    instance class [mscorlib]System.StringComparer <>c::<Load>b__5_0(class [Autofac]Autofac.IComponentContext c)
0x1ba6  newobj   instance void class [mscorlib]System.Func`2<class [Autofac]Autofac.IComponentContext, class [mscorlib]System.StringComparer>::.ctor(object, native int)
0x1bab  dup
0x1bac  stsfld   class [mscorlib]System.Func`2<class [Autofac]Autofac.IComponentContext, class [mscorlib]System.StringComparer> <>c::<>9__5_0
0x1bb1  call     T0x2B000031
0x1bb6  callvirt T0x2B000032
0x1bbb  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class [mscorlib]System.StringComparer, class [Autofac]Autofac.Builder.SimpleActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1bc0  pop
0x1bc1  ldarg.1
0x1bc2  call     T0x2B000033
0x1bc7  ldarg.0
0x1bc8  call     instance int32 Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultProviderModule::get_SecretExpireTimeInMinutes()
0x1bcd  conv.r8
0x1bce  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x1bd3  call     T0x2B000034
0x1bd8  call     T0x2B000035
0x1bdd  callvirt T0x2B000036
0x1be2  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommon.InMemoryCache`2<string, class [mscorlib]System.Security.SecureString>, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1be7  pop
0x1be8  ldarg.1
0x1be9  call     T0x2B000037
0x1bee  callvirt T0x2B000038
0x1bf3  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommon.CertificateLookup, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1bf8  pop
0x1bf9  ldarg.1
0x1bfa  call     T0x2B000039
0x1bff  pop
0x1c00  ldarg.1
0x1c01  call     T0x2B00003A
0x1c06  pop
0x1c07  ldarg.1
0x1c08  ldarg.0
0x1c09  ldftn    instance class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.IKeyVaultClient Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultProviderModule::CreateKeyVaultAdapter(class [Autofac]Autofac.IComponentContext context)
0x1c0f  newobj   instance void class [mscorlib]System.Func`2<class [Autofac]Autofac.IComponentContext, class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.IKeyVaultClient>::.ctor(object, native int)
0x1c14  call     T0x2B00003B
0x1c19  callvirt T0x2B00003C
0x1c1e  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.IKeyVaultClient, class [Autofac]Autofac.Builder.SimpleActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1c23  pop
0x1c24  ldarg.0
0x1c25  ldarg.1
0x1c26  call     instance void Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultProviderModule::RegisterSecretLookup(class [Autofac]Autofac.ContainerBuilder builder)
0x1c2b  ldarg.1
0x1c2c  call     T0x2B00003D
0x1c31  callvirt T0x2B00003E
0x1c36  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommon.NullSecretLookupEvents, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1c3b  pop
0x1c3c  ldarg.1
0x1c3d  call     T0x2B00003F
0x1c42  callvirt T0x2B000040
0x1c47  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommon.NullInMemoryCacheEvents, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1c4c  pop
0x1c4d  ret
```
