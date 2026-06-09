# Microsoft.Crm.Asynchronous.V4ProxyPlugin::Execute

- ea: `0x3410`
- end: `0x3435`
- name: `Microsoft.Crm.Asynchronous.V4ProxyPlugin::Execute`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x33c0`
- `0x3410`

## pseudocode

```c

```

## disassembly

```asm
0x3410  ldarg.0
0x3411  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext Microsoft.Crm.Asynchronous.VersionedProxyPluginBase::get_Context()
0x3416  newobj   instance void [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.V4AsyncExecutionContext::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext)
0x341b  stloc.0
0x341c  ldarg.0
0x341d  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IPlugin Microsoft.Crm.Asynchronous.V4ProxyPlugin::_plugin
0x3422  ldloc.0
0x3423  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IPlugin::Execute(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IPluginExecutionContext)
0x3428  leave.s  loc_3434
0x342a  ldloc.0
0x342b  brfalse.s loc_3433
0x342d  ldloc.0
0x342e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3433  endfinally
0x3434  ret
```
