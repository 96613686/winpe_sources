# Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::ConfigureLifetimeScope

- ea: `0x110`
- end: `0x127`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::ConfigureLifetimeScope`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd0`

## pseudocode

```c

```

## disassembly

```asm
0x110  ldarg.1
0x111  ldc.i4.1
0x112  newarr   [mscorlib]System.Reflection.Assembly
0x117  dup
0x118  ldc.i4.0
0x119  ldarg.0
0x11a  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::get_ApiControllerAssembly()
0x11f  stelem.ref
0x120  call     class [Autofac]Autofac.Builder.IRegistrationBuilder`3<object, class [Autofac]Autofac.Features.Scanning.ScanningActivatorData, class [Autofac]Autofac.Builder.DynamicRegistrationStyle> [Autofac.Integration.WebApi]Autofac.Integration.WebApi.RegistrationExtensions::RegisterApiControllers(class [Autofac]Autofac.ContainerBuilder, class [mscorlib]System.Reflection.Assembly[])
0x125  pop
0x126  ret
```
