# Microsoft.Crm.Sandbox.SandboxTraceListener::Write_0

- ea: `0x93d0`
- end: `0x9442`
- name: `Microsoft.Crm.Sandbox.SandboxTraceListener::Write_0`
- size: `114`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x9240`
- `0x92a0`
- `0x9330`
- `0x93b0`
- `0x93c0`

## callees

- `0x1130`
- `0x1420`
- `0x1450`
- `0x14a0`
- `0x14d0`
- `0x93d0`

## pseudocode

```c

```

## disassembly

```asm
0x93d0  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x93d5  callvirt instance bool [mscorlib]System.AppDomain::get_IsFullyTrusted()
0x93da  brfalse.s loc_9441
0x93dc  ldarg.2
0x93dd  ldc.i4.1
0x93de  sub
0x93df  switch   loc_9408, loc_941C, loc_93F5, loc_942F
0x93f4  ret
0x93f5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x93fa  ldarg.0
0x93fb  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Sandbox.SandboxTraceListener::_traceCategory
0x9400  ldarg.1
0x9401  ldarg.3
0x9402  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9407  ret
0x9408  ldnull
0x9409  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x940e  ldarg.0
0x940f  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Sandbox.SandboxTraceListener::_traceCategory
0x9414  ldarg.1
0x9415  ldarg.3
0x9416  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x941b  ret
0x941c  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x9421  ldarg.0
0x9422  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Sandbox.SandboxTraceListener::_traceCategory
0x9427  ldarg.1
0x9428  ldarg.3
0x9429  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x942e  ret
0x942f  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x9434  ldarg.0
0x9435  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Sandbox.SandboxTraceListener::_traceCategory
0x943a  ldarg.1
0x943b  ldarg.3
0x943c  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9441  ret
```
