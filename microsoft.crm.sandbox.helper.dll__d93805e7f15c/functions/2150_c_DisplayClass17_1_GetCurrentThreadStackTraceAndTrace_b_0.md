# <>c__DisplayClass17_1::<GetCurrentThreadStackTraceAndTrace>b__0

- ea: `0x2150`
- end: `0x21b4`
- name: `<>c__DisplayClass17_1::<GetCurrentThreadStackTraceAndTrace>b__0`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1990`
- `0x2150`

## string_xrefs

- `0x2178`: `GetCurrentThreadStackTraceAndAbort: Error trying to release thread to obtain plugin StackTrace: `
- `0x21a6`: `GetCurrentThreadStackTraceAndAbort: Unhandled exception in safeThread.`

## pseudocode

```c

```

## disassembly

```asm
0x2150  ldarg.0
0x2151  ldfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass17_1::safeThreadReady
0x2156  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x215b  pop
0x215c  br.s     loc_218B
0x215e  nop
0x215f  ldarg.0
0x2160  ldfld    class <>c__DisplayClass17_0 <>c__DisplayClass17_1::CS$<>8__locals1
0x2165  ldfld    class [mscorlib]System.Threading.Thread <>c__DisplayClass17_0::executeThread
0x216a  callvirt instance void [mscorlib]System.Threading.Thread::Resume()
0x216f  leave.s  loc_218B
0x2171  stloc.0
0x2172  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2177  ldc.i4.1
0x2178  ldstr    aGetcurrentthre_3// "GetCurrentThreadStackTraceAndAbort: Err"...
0x217d  ldloc.0
0x217e  call     string [mscorlib]System.String::Concat(object, object)
0x2183  ldnull
0x2184  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x2189  leave.s  loc_218B
0x218b  ldarg.0
0x218c  ldfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass17_1::safeThreadGracefullyFinish
0x2191  ldc.i4   0x1F4
0x2196  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(int32)
0x219b  brfalse.s loc_215E
0x219d  leave.s  loc_21B3
0x219f  pop
0x21a0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21a5  ldc.i4.1
0x21a6  ldstr    aGetcurrentthre_4// "GetCurrentThreadStackTraceAndAbort: Unh"...
0x21ab  ldnull
0x21ac  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x21b1  leave.s  loc_21B3
0x21b3  ret
```
