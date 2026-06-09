# UpdateTraceA

- ea: `0x180002750`
- end: `0x18000275b`
- name: `UpdateTraceA`
- size: `11`
- prototype: `ULONG __stdcall(TRACEHANDLE TraceHandle, LPCSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800099c0`

## pseudocode

```c
ULONG __stdcall UpdateTraceA(TRACEHANDLE TraceHandle, LPCSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties)
{
  return ControlTraceA(TraceHandle, InstanceName, Properties, 2u);
}

```

## disassembly

```asm
0x180002750  mov     r9d, 2
0x180002756  jmp     ControlTraceA
```
