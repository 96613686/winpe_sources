# Microsoft.Crm.Sandbox.SandboxTracker::WriteTrace

- ea: `0x7700`
- end: `0x774a`
- name: `Microsoft.Crm.Sandbox.SandboxTracker::WriteTrace`
- size: `74`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x72c0`
- `0x7330`
- `0x7380`
- `0x7410`
- `0x7440`
- `0x7480`

## callees

- `0x1450`
- `0x77f0`
- `0xafd0`

## string_xrefs

- `0x771c`: `SandboxTracker.WriteTrace: enter`

## pseudocode

```c

```

## disassembly

```asm
0x7700  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x7705  stloc.0
0x7706  ldloc.0
0x7707  ldarg.1
0x7708  stfld    string <>c__DisplayClass17_0::traceType
0x770d  ldloc.0
0x770e  ldarg.0
0x770f  stfld    class Microsoft.Crm.Sandbox.SandboxTracker <>c__DisplayClass17_0::<>4__this
0x7714  ldarg.0
0x7715  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTracker::_organizationId
0x771a  ldc.i4.s 0x27
0x771c  ldstr    aSandboxtracker_1// "SandboxTracker.WriteTrace: enter"
0x7721  ldc.i4.0
0x7722  newarr   [mscorlib]System.Object
0x7727  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x772c  ldloc.0
0x772d  ldftn    instance string <>c__DisplayClass17_0::<WriteTrace>b__0()
0x7733  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x7738  stloc.1
0x7739  ldarg.0
0x773a  ldnull
0x773b  ldarg.0
0x773c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTracker::_organizationId
0x7741  ldarg.2
0x7742  ldarg.3
0x7743  ldloc.1
0x7744  call     instance void Microsoft.Crm.Sandbox.SandboxTracker::LogTrace(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, class [mscorlib]System.Func`1<string> traceFunction)
0x7749  ret
```
