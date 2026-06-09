# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthModule::Load

- ea: `0x24c0`
- end: `0x2505`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthModule::Load`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x24c0  ldarg.1
0x24c1  call     T0x2B000061
0x24c6  callvirt T0x2B000062
0x24cb  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextFactory, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x24d0  pop
0x24d1  ldarg.1
0x24d2  call     T0x2B000063
0x24d7  callvirt T0x2B000064
0x24dc  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x24e1  pop
0x24e2  ldarg.1
0x24e3  call     T0x2B000065
0x24e8  callvirt T0x2B000066
0x24ed  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthProviderFactory, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x24f2  pop
0x24f3  ldarg.1
0x24f4  call     T0x2B000067
0x24f9  callvirt T0x2B000068
0x24fe  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionStringConfigParser, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x2503  pop
0x2504  ret
```
