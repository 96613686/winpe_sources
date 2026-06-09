# PcaTraceDelete(void)

- ea: `0x180003290`
- end: `0x1800032de`
- name: `?PcaTraceDelete@@YAXXZ`
- size: `78`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003220`

## callees

- `0x1800032f0`
- `0x1800033c0`

## pseudocode

```c
void PcaTraceDelete(void)
{
  g_AslLogPfnVPrintf = 0;
  AslLogDelete((char *)g_PcapLogTrace);
  g_PcapLogTrace = 0;
  AslLogDelete((char *)g_PcapLogDebug);
  g_PcapLogDebug = 0;
  AslTelemetryDelete((char *)g_PcaTelemetry);
  g_PcaTelemetry = 0;
}

```

## disassembly

```asm
0x180003290  push    rbx
0x180003292  sub     rsp, 20h
0x180003296  mov     rcx, cs:?g_PcapLogTrace@@3_KA; P
0x18000329d  xor     ebx, ebx
0x18000329f  mov     cs:g_AslLogPfnVPrintf, rbx
0x1800032a6  call    AslLogDelete
0x1800032ab  mov     rcx, cs:?g_PcapLogDebug@@3_KA; P
0x1800032b2  mov     cs:?g_PcapLogTrace@@3_KA, rbx; unsigned __int64 g_PcapLogTrace
0x1800032b9  call    AslLogDelete
0x1800032be  mov     rcx, cs:?g_PcaTelemetry@@3_KA; P
0x1800032c5  mov     cs:?g_PcapLogDebug@@3_KA, rbx; unsigned __int64 g_PcapLogDebug
0x1800032cc  call    AslTelemetryDelete
0x1800032d1  mov     cs:?g_PcaTelemetry@@3_KA, rbx; unsigned __int64 g_PcaTelemetry
0x1800032d8  add     rsp, 20h
0x1800032dc  pop     rbx
0x1800032dd  retn
```
