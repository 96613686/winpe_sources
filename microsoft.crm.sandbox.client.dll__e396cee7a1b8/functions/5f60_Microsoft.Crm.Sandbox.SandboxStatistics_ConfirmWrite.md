# Microsoft.Crm.Sandbox.SandboxStatistics::ConfirmWrite

- ea: `0x5f60`
- end: `0x5f94`
- name: `Microsoft.Crm.Sandbox.SandboxStatistics::ConfirmWrite`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x5f67`: `SandboxStatistics.ConfirmWrite: enter`

## pseudocode

```c

```

## disassembly

```asm
0x5f60  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5f65  ldc.i4.s 0x28
0x5f67  ldstr    aSandboxstatist_4// "SandboxStatistics.ConfirmWrite: enter"
0x5f6c  ldc.i4.0
0x5f6d  newarr   [mscorlib]System.Object
0x5f72  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5f77  ldarg.0
0x5f78  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x5f7d  ldstr    aPxr_0// "_pxr"
0x5f82  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5f87  ldarg.0
0x5f88  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord Microsoft.Crm.Sandbox.SandboxStatistics::_pxr
0x5f8d  ldc.i4.1
0x5f8e  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::set_WrittenToPluginTypeStatistic(bool)
0x5f93  ret
```
