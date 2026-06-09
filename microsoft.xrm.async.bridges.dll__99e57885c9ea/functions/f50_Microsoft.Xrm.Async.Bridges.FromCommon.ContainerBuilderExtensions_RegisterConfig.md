# Microsoft.Xrm.Async.Bridges.FromCommon.ContainerBuilderExtensions::RegisterConfig

- ea: `0xf50`
- end: `0xf7b`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ContainerBuilderExtensions::RegisterConfig`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xf50`

## pseudocode

```c

```

## disassembly

```asm
0xf50  ldarg.0
0xf51  ldsfld   class [mscorlib]System.Func`2<class [Autofac]Autofac.IComponentContext, var<u1>> class <>c__0`1<mvar<u1>>::<>9__0_0
0xf56  dup
0xf57  brtrue.s loc_F70
0xf59  pop
0xf5a  ldsfld   class <>c__0`1<var<u1>> class <>c__0`1<mvar<u1>>::<>9
0xf5f  ldftn    instance var<u1> class <>c__0`1<mvar<u1>>::<RegisterConfig>b__0_0(!!T0)
0xf65  newobj   instance void class [mscorlib]System.Func`2<class [Autofac]Autofac.IComponentContext, mvar<u1>>::.ctor(object, native int)
0xf6a  dup
0xf6b  stsfld   class [mscorlib]System.Func`2<class [Autofac]Autofac.IComponentContext, var<u1>> class <>c__0`1<mvar<u1>>::<>9__0_0
0xf70  call     T0x2B000023
0xf75  callvirt instance class [Autofac]Autofac.Builder.IRegistrationBuilder`3<var<u1>, !!T0, var<u1>> class [Autofac]Autofac.Builder.IRegistrationBuilder`3<mvar<u1>, !!T0, class [Autofac]Autofac.Builder.SimpleActivatorData>::SingleInstance()
0xf7a  ret
```
