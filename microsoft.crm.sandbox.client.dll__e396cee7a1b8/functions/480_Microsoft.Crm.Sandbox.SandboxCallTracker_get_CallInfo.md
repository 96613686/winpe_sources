# Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo

- ea: `0x480`
- end: `0x49f`
- name: `Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo`
- size: `31`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x110`
- `0x4b0`
- `0x2030`
- `0x23d0`
- `0x2c40`
- `0x3450`
- `0x8dc0`

## callees

- `0x480`

## pseudocode

```c

```

## disassembly

```asm
0x480  ldarg.0
0x481  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::sandboxCallInfo
0x486  brtrue.s loc_498
0x488  ldarg.0
0x489  call     valuetype [mscorlib]System.Guid [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::get_CurrentThreadActivityId()
0x48e  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::.ctor(valuetype [mscorlib]System.Guid)
0x493  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::sandboxCallInfo
0x498  ldarg.0
0x499  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::sandboxCallInfo
0x49e  ret
```
