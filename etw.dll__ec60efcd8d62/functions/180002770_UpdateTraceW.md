# UpdateTraceW

- ea: `0x180002770`
- end: `0x18000277b`
- name: `UpdateTraceW`
- size: `11`
- prototype: `ULONG __stdcall(TRACEHANDLE TraceHandle, LPCWSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a300`

## pseudocode

```c
ULONG __stdcall UpdateTraceW(TRACEHANDLE TraceHandle, LPCWSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties)
{
  return ControlTraceW(TraceHandle, InstanceName, Properties, 2u);
}

```

## disassembly

```asm
0x180002770  mov     r9d, 2
0x180002776  jmp     ControlTraceW
```
