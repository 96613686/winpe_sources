# Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.HttpSenderFactoryModule::Load

- ea: `0x1ec0`
- end: `0x1f30`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.HttpSenderFactoryModule::Load`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1f30`

## pseudocode

```c

```

## disassembly

```asm
0x1ec0  ldarg.1
0x1ec1  call     T0x2B00004F
0x1ec6  ldc.r8   1.0
0x1ecf  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromHours(float64)
0x1ed4  call     T0x2B000034
0x1ed9  call     T0x2B000050
0x1ede  callvirt T0x2B000051
0x1ee3  pop
0x1ee4  ldarg.1
0x1ee5  call     T0x2B000052
0x1eea  callvirt T0x2B000053
0x1eef  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommon.UriEqualityComparer, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1ef4  pop
0x1ef5  ldarg.0
0x1ef6  ldarg.1
0x1ef7  call     instance void Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.HttpSenderFactoryModule::RegisterHttpSenderFactory(class [Autofac]Autofac.ContainerBuilder builder)
0x1efc  ldarg.1
0x1efd  call     T0x2B00003F
0x1f02  callvirt T0x2B000040
0x1f07  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommon.NullInMemoryCacheEvents, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1f0c  pop
0x1f0d  ldarg.1
0x1f0e  call     T0x2B000054
0x1f13  callvirt T0x2B000055
0x1f18  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.NullAuthProviderEvents, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1f1d  pop
0x1f1e  ldarg.1
0x1f1f  call     T0x2B000056
0x1f24  callvirt T0x2B000057
0x1f29  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ConfigTargetEndpointConfigLookup, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1f2e  pop
0x1f2f  ret
```
