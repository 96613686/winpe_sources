# Microsoft.Crm.Asynchronous.AsyncService::ConfigureWebApp

- ea: `0x1090`
- end: `0x1114`
- name: `Microsoft.Crm.Asynchronous.AsyncService::ConfigureWebApp`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1040`

## callees

- `0x1090`
- `0xa410`
- `0xa5d0`

## pseudocode

```c

```

## disassembly

```asm
0x1090  newobj   instance void <>c__DisplayClass29_0::.ctor()
0x1095  stloc.0
0x1096  ldarg.0
0x1097  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::_context
0x109c  stloc.s  4
0x109e  ldloc.s  4
0x10a0  brfalse.s loc_10A8
0x10a2  ldloc.s  4
0x10a4  ldc.i4.1
0x10a5  beq.s    loc_10B0
0x10a7  ret
0x10a8  ldc.i4   0x1F95
0x10ad  stloc.1
0x10ae  br.s     loc_10B6
0x10b0  ldc.i4   0x1F96
0x10b5  stloc.1
0x10b6  ldloc.1
0x10b7  newobj   instance void Microsoft.Crm.Asynchronous.Bridges.BridgesModule::.ctor(int32 port)
0x10bc  stloc.2
0x10bd  ldarg.1
0x10be  ldloc.2
0x10bf  call     class [Autofac]Autofac.Core.Registration.IModuleRegistrar [Autofac]Autofac.ModuleRegistrationExtensions::RegisterModule(class [Autofac]Autofac.ContainerBuilder, class [Autofac]Autofac.Core.IModule)
0x10c4  pop
0x10c5  ldarg.1
0x10c6  call     T0x2B000003
0x10cb  pop
0x10cc  ldloc.0
0x10cd  ldarg.1
0x10ce  ldc.i4.0
0x10cf  callvirt instance class [Autofac]Autofac.IContainer [Autofac]Autofac.ContainerBuilder::Build(valuetype [Autofac]Autofac.Builder.ContainerBuildOptions)
0x10d4  stfld    class [Autofac]Autofac.IContainer <>c__DisplayClass29_0::container
0x10d9  ldloc.0
0x10da  ldloc.0
0x10db  ldfld    class [Autofac]Autofac.IContainer <>c__DisplayClass29_0::container
0x10e0  call     T0x2B000004
0x10e5  stfld    class [Microsoft.Xrm.Async.Bridges.WebApp]Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder <>c__DisplayClass29_0::webAppBuilder
0x10ea  ldstr    aHttps// "https://*:"
0x10ef  ldloc.1
0x10f0  box      [mscorlib]System.Int32
0x10f5  call     string [mscorlib]System.String::Concat(object, object)
0x10fa  stloc.3
0x10fb  ldarg.0
0x10fc  ldloc.3
0x10fd  ldloc.0
0x10fe  ldftn    instance void <>c__DisplayClass29_0::<ConfigureWebApp>b__0(class [Owin]Owin.IAppBuilder app)
0x1104  newobj   instance void class [mscorlib]System.Action`1<class [Owin]Owin.IAppBuilder>::.ctor(object, native int)
0x1109  call     class [mscorlib]System.IDisposable [Microsoft.Owin.Hosting]Microsoft.Owin.Hosting.WebApp::Start(string, class [mscorlib]System.Action`1<class [Owin]Owin.IAppBuilder>)
0x110e  stfld    class [mscorlib]System.IDisposable Microsoft.Crm.Asynchronous.AsyncService::webApp
0x1113  ret
```
