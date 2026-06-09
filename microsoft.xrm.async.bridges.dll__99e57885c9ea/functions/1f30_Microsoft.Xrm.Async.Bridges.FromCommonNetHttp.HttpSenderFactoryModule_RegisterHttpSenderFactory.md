# Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.HttpSenderFactoryModule::RegisterHttpSenderFactory

- ea: `0x1f30`
- end: `0x1f77`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.HttpSenderFactoryModule::RegisterHttpSenderFactory`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ec0`

## callees

- `0x1ea0`

## pseudocode

```c

```

## disassembly

```asm
0x1f30  ldarg.1
0x1f31  call     T0x2B000058
0x1f36  ldarg.0
0x1f37  call     instance string Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.HttpSenderFactoryModule::get_ConnectionStringKey()
0x1f3c  call     T0x2B000059
0x1f41  call     T0x2B00005A
0x1f46  ldstr    aHttpsenderfact// "HttpSenderFactory.Inner"
0x1f4b  callvirt T0x2B00005B
0x1f50  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1f55  pop
0x1f56  ldarg.1
0x1f57  call     T0x2B00005C
0x1f5c  ldstr    aHttpsenderfact// "HttpSenderFactory.Inner"
0x1f61  call     T0x2B00005D
0x1f66  call     T0x2B00005E
0x1f6b  callvirt T0x2B00005F
0x1f70  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache, class [Autofac]Autofac.Builder.ConcreteReflectionActivatorData, class [Autofac]Autofac.Builder.SingleRegistrationStyle>::SingleInstance()
0x1f75  pop
0x1f76  ret
```
