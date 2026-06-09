# Microsoft.Crm.Asynchronous.V5ProxyPlugin::Execute

- ea: `0x3520`
- end: `0x35d4`
- name: `Microsoft.Crm.Asynchronous.V5ProxyPlugin::Execute`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x33c0`
- `0x3520`
- `0x35f0`

## pseudocode

```c

```

## disassembly

```asm
0x3520  ldarg.0
0x3521  ldfld    object Microsoft.Crm.Asynchronous.V5ProxyPlugin::_plugin
0x3526  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IPlugin
0x352b  stloc.0
0x352c  ldarg.0
0x352d  ldfld    object Microsoft.Crm.Asynchronous.V5ProxyPlugin::_plugin
0x3532  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IIsolatablePlugin
0x3537  stloc.1
0x3538  ldarg.0
0x3539  ldfld    object Microsoft.Crm.Asynchronous.V5ProxyPlugin::_plugin
0x353e  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin
0x3543  stloc.2
0x3544  ldloc.2
0x3545  brfalse.s loc_3581
0x3547  ldarg.0
0x3548  ldfld    bool Microsoft.Crm.Asynchronous.V5ProxyPlugin::_pluginUsesEarlyBoundTypes
0x354d  brfalse.s loc_3579
0x354f  ldloc.2
0x3550  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3555  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x355a  ldarg.0
0x355b  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::get_Context()
0x3560  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ProxyTypesAssemblyContext::.ctor(class [mscorlib]System.Reflection.Assembly, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IProxyTypesAssemblyProvider)
0x3565  stloc.3
0x3566  ldloc.2
0x3567  ldarg.1
0x3568  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin::Execute(class [mscorlib]System.IServiceProvider)
0x356d  leave.s  loc_35D3
0x356f  ldloc.3
0x3570  brfalse.s loc_3578
0x3572  ldloc.3
0x3573  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3578  endfinally
0x3579  ldloc.2
0x357a  ldarg.1
0x357b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin::Execute(class [mscorlib]System.IServiceProvider)
0x3580  ret
0x3581  ldloc.1
0x3582  brfalse.s loc_35B0
0x3584  ldarg.0
0x3585  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::get_Context()
0x358a  newobj   instance void [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.V5AsyncExecutionContext::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext)
0x358f  stloc.s  4
0x3591  ldloc.s  4
0x3593  newobj   instance void Microsoft.Crm.Asynchronous.LegacyServiceProvider::.ctor(class [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.V5AsyncExecutionContext context)
0x3598  stloc.s  5
0x359a  ldloc.1
0x359b  ldloc.s  5
0x359d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IIsolatablePlugin::Execute(class [mscorlib]System.IServiceProvider)
0x35a2  leave.s  loc_35D3
0x35a4  ldloc.s  4
0x35a6  brfalse.s loc_35AF
0x35a8  ldloc.s  4
0x35aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35af  endfinally
0x35b0  ldarg.0
0x35b1  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::get_Context()
0x35b6  newobj   instance void [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.V5AsyncExecutionContext::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext)
0x35bb  stloc.s  6
0x35bd  ldloc.0
0x35be  ldloc.s  6
0x35c0  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IPlugin::Execute(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IPluginExecutionContext)
0x35c5  leave.s  loc_35D3
0x35c7  ldloc.s  6
0x35c9  brfalse.s loc_35D2
0x35cb  ldloc.s  6
0x35cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35d2  endfinally
0x35d3  ret
```
