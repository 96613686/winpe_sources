# Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor

- ea: `0x18d0`
- end: `0x1923`
- name: `Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7b0`
- `0x1240`
- `0x2060`

## callees

- `0x1990`

## pseudocode

```c

```

## disassembly

```asm
0x18d0  ldarg.0
0x18d1  call     instance void [mscorlib]System.Object::.ctor()
0x18d6  ldarg.0
0x18d7  ldarg.1
0x18d8  stfld    string Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_contextName
0x18dd  ldarg.0
0x18de  ldarg.2
0x18df  stfld    valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_traceLevel
0x18e4  ldarg.0
0x18e5  ldarg.3
0x18e6  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_orgId
0x18eb  ldarg.0
0x18ec  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x18f1  stfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_contextTime
0x18f6  ldarg.0
0x18f7  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_contextTime
0x18fc  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x1901  ldarg.0
0x1902  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_orgId
0x1907  ldarg.2
0x1908  ldstr    a0StartingPerfo// "{0}: Starting performance monitor"
0x190d  ldarg.0
0x190e  ldfld    string Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::_contextName
0x1913  call     string [mscorlib]System.String::Format(string, object)
0x1918  ldstr    aSandboxPerform// "Sandbox_Performance"
0x191d  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1922  ret
```
