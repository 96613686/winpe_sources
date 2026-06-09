# Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::Dispose

- ea: `0x1930`
- end: `0x1972`
- name: `Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::Dispose`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2060`

## callees

- `0x1990`

## pseudocode

```c

```

## disassembly

```asm
0x1930  ldarg.0
0x1931  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_contextTime
0x1936  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x193b  ldarg.0
0x193c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_orgId
0x1941  ldarg.0
0x1942  ldfld    valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_traceLevel
0x1947  ldstr    a0StoppedPerfor// "{0}: Stopped performance monitor. Execu"...
0x194c  ldarg.0
0x194d  ldfld    string Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_contextName
0x1952  ldarg.0
0x1953  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_contextTime
0x1958  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x195d  box      [mscorlib]System.Int64
0x1962  call     string [mscorlib]System.String::Format(string, object, object)
0x1967  ldstr    aSandboxPerform// "Sandbox_Performance"
0x196c  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1971  ret
```
