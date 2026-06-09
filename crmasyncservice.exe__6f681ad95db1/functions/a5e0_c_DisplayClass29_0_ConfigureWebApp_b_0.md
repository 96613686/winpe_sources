# <>c__DisplayClass29_0::<ConfigureWebApp>b__0

- ea: `0xa5e0`
- end: `0xa5f3`
- name: `<>c__DisplayClass29_0::<ConfigureWebApp>b__0`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c

```

## disassembly

```asm
0xa5e0  ldarg.0
0xa5e1  ldfld    class [Microsoft.Xrm.Async.Bridges.WebApp]Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder <>c__DisplayClass29_0::webAppBuilder
0xa5e6  ldarg.0
0xa5e7  ldfld    class [Autofac]Autofac.IContainer <>c__DisplayClass29_0::container
0xa5ec  ldarg.1
0xa5ed  callvirt instance void [Microsoft.Xrm.Async.Bridges.WebApp]Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::Initialize(class [Autofac]Autofac.ILifetimeScope, class [Owin]Owin.IAppBuilder)
0xa5f2  ret
```
