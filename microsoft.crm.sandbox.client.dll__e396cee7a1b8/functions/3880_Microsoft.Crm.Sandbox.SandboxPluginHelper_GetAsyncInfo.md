# Microsoft.Crm.Sandbox.SandboxPluginHelper::GetAsyncInfo

- ea: `0x3880`
- end: `0x38a7`
- name: `Microsoft.Crm.Sandbox.SandboxPluginHelper::GetAsyncInfo`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3630`

## pseudocode

```c

```

## disassembly

```asm
0x3880  ldarg.0
0x3881  isinst   [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Crm.Sandbox.IAsyncExecutionContext
0x3886  stloc.0
0x3887  ldloc.0
0x3888  ldstr    aAsyncexecution// "asyncExecutionContext"
0x388d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3892  ldarg.1
0x3893  ldloc.0
0x3894  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Crm.Sandbox.IAsyncExecutionContext::get_CallerOrigin()
0x3899  stind.ref
0x389a  ldarg.2
0x389b  ldloc.0
0x389c  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Crm.Sandbox.IAsyncExecutionContext::get_CorrelationUpdatedTime()
0x38a1  stobj    [mscorlib]System.DateTime
0x38a6  ret
```
