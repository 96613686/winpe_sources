# Microsoft.Crm.Asynchronous.V5ProxyPlugin::.ctor

- ea: `0x3450`
- end: `0x351b`
- name: `Microsoft.Crm.Asynchronous.V5ProxyPlugin::.ctor`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2db0`

## callees

- `0x32c0`
- `0x3450`

## pseudocode

```c

```

## disassembly

```asm
0x3450  ldarg.0
0x3451  ldarg.2
0x3452  call     instance void Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x3457  ldarg.1
0x3458  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin
0x345d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3462  callvirt instance string [mscorlib]System.Type::get_FullName()
0x3467  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetInterface(string)
0x346c  ldnull
0x346d  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3472  brfalse.s loc_34B3
0x3474  ldarg.0
0x3475  ldarg.0
0x3476  ldarg.1
0x3477  ldarg.2
0x3478  call     T0x2B000007
0x347d  stfld    object Microsoft.Crm.Asynchronous.V5ProxyPlugin::_plugin
0x3482  ldarg.0
0x3483  ldfld    object Microsoft.Crm.Asynchronous.V5ProxyPlugin::_plugin
0x3488  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x348d  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x3492  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.ProxyTypesAssemblyAttribute
0x3497  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x349c  ldc.i4.0
0x349d  callvirt instance object[] [mscorlib]System.Reflection.Assembly::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x34a2  stloc.0
0x34a3  ldloc.0
0x34a4  brfalse.s loc_350B
0x34a6  ldloc.0
0x34a7  ldlen
0x34a8  brfalse.s loc_350B
0x34aa  ldarg.0
0x34ab  ldc.i4.1
0x34ac  stfld    bool Microsoft.Crm.Asynchronous.V5ProxyPlugin::_pluginUsesEarlyBoundTypes
0x34b1  br.s     loc_350B
0x34b3  ldarg.1
0x34b4  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IIsolatablePlugin
0x34b9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34be  callvirt instance string [mscorlib]System.Type::get_FullName()
0x34c3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetInterface(string)
0x34c8  ldnull
0x34c9  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34ce  brfalse.s loc_34E0
0x34d0  ldarg.0
0x34d1  ldarg.0
0x34d2  ldarg.1
0x34d3  ldarg.2
0x34d4  call     T0x2B000008
0x34d9  stfld    object Microsoft.Crm.Asynchronous.V5ProxyPlugin::_plugin
0x34de  br.s     loc_350B
0x34e0  ldarg.1
0x34e1  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IPlugin
0x34e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34eb  callvirt instance string [mscorlib]System.Type::get_FullName()
0x34f0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetInterface(string)
0x34f5  ldnull
0x34f6  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34fb  brfalse.s loc_350B
0x34fd  ldarg.0
0x34fe  ldarg.0
0x34ff  ldarg.1
0x3500  ldarg.2
0x3501  call     T0x2B000006
0x3506  stfld    object Microsoft.Crm.Asynchronous.V5ProxyPlugin::_plugin
0x350b  ldarg.0
0x350c  ldfld    object Microsoft.Crm.Asynchronous.V5ProxyPlugin::_plugin
0x3511  brtrue.s loc_3517
0x3513  ldarg.3
0x3514  ldc.i4.0
0x3515  stind.i1
0x3516  ret
0x3517  ldarg.3
0x3518  ldc.i4.1
0x3519  stind.i1
0x351a  ret
```
