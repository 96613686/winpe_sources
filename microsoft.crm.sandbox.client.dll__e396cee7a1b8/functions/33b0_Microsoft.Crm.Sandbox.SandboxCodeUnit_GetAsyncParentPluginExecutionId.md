# Microsoft.Crm.Sandbox.SandboxCodeUnit::GetAsyncParentPluginExecutionId

- ea: `0x33b0`
- end: `0x33e5`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::GetAsyncParentPluginExecutionId`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8dc0`

## callees

- `0x33b0`

## pseudocode

```c

```

## disassembly

```asm
0x33b0  ldarg.0
0x33b1  isinst   [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Crm.Sandbox.IAsyncExecutionContext
0x33b6  stloc.0
0x33b7  ldloc.0
0x33b8  brfalse.s loc_33D9
0x33ba  ldloc.0
0x33bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Crm.Sandbox.IAsyncExecutionContext::get_ParentPluginExecutionId()
0x33c0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33c5  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x33ca  brfalse.s loc_33D9
0x33cc  ldarg.1
0x33cd  ldloc.0
0x33ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Crm.Sandbox.IAsyncExecutionContext::get_ParentPluginExecutionId()
0x33d3  stobj    [mscorlib]System.Guid
0x33d8  ret
0x33d9  ldarg.1
0x33da  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33df  stobj    [mscorlib]System.Guid
0x33e4  ret
```
