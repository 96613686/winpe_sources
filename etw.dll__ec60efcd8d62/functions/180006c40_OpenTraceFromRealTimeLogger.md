# OpenTraceFromRealTimeLogger

- ea: `0x180006c40`
- end: `0x180006c59`
- name: `OpenTraceFromRealTimeLogger`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006c60`

## pseudocode

```c
unsigned __int64 __fastcall OpenTraceFromRealTimeLogger(
        const WCHAR *a1,
        const struct ETW_OPEN_TRACE_OPTIONS *a2,
        _OWORD *a3)
{
  return OpenTraceFromRealTimeLoggerWithAllocationOptions(a1, a2, 0, 0, a3);
}

```

## disassembly

```asm
0x180006c40  sub     rsp, 38h
0x180006c44  mov     [rsp+38h+var_18], r8
0x180006c49  xor     r9d, r9d
0x180006c4c  xor     r8d, r8d
0x180006c4f  call    OpenTraceFromRealTimeLoggerWithAllocationOptions
0x180006c54  add     rsp, 38h
0x180006c58  retn
```
