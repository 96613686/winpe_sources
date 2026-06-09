# Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::Initialize

- ea: `0xe0`
- end: `0x10c`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::Initialize`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x130`

## pseudocode

```c

```

## disassembly

```asm
0xe0  ldarg.0
0xe1  ldarg.1
0xe2  ldstr    aWebapp// "WebApp"
0xe7  ldarg.0
0xe8  dup
0xe9  ldvirtftn instance void Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::ConfigureLifetimeScope(class [Autofac]Autofac.ContainerBuilder builder)
0xef  newobj   instance void class [mscorlib]System.Action`1<class [Autofac]Autofac.ContainerBuilder>::.ctor(object, native int)
0xf4  callvirt instance class [Autofac]Autofac.ILifetimeScope [Autofac]Autofac.ILifetimeScope::BeginLifetimeScope(object, class [mscorlib]System.Action`1<class [Autofac]Autofac.ContainerBuilder>)
0xf9  stfld    class [Autofac]Autofac.ILifetimeScope Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::innerScope
0xfe  ldarg.0
0xff  ldarg.0
0x100  ldfld    class [Autofac]Autofac.ILifetimeScope Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::innerScope
0x105  ldarg.2
0x106  callvirt instance void Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::ConfigureWebApp(class [Autofac]Autofac.ILifetimeScope scope, class [Owin]Owin.IAppBuilder app)
0x10b  ret
```
