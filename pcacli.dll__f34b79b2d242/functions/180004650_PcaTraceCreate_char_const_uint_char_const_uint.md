# PcaTraceCreate(char const *,uint,char const *,uint)

- ea: `0x180004650`
- end: `0x1800046b7`
- name: `?PcaTraceCreate@@YAXPEBDI0I@Z`
- size: `103`
- prototype: `void __fastcall(const char *, unsigned int, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180003220`

## callees

- `0x1800046c0`
- `0x180004790`
- `0x1800050e0`

## string_xrefs

- `0x180004673`: `PcaCliDebug`
- `0x1800046a0`: `PcaCliDebug`
- `0x180004654`: `PcaCliTrace`

## pseudocode

```c
void __fastcall PcaTraceCreate(const char *a1, __int64 a2, const char *a3)
{
  AslLogCreate(&g_PcapLogTrace, "PcaCliTrace");
  AslLogPublishToPeb(g_PcapLogTrace);
  AslLogCreate(&g_PcapLogDebug, "PcaCliDebug");
  g_AslLogPfnVPrintf = (__int64)&PcapTraceDebugCallback;
  AslLogPublishToPeb(g_PcapLogDebug);
  AslTelemetryCreate(&g_PcaTelemetry, "PcaCliDebug");
}

```

## disassembly

```asm
0x180004650  sub     rsp, 28h
0x180004654  lea     rdx, aPcaclitrace; "PcaCliTrace"
0x18000465b  lea     rcx, ?g_PcapLogTrace@@3_KA; unsigned __int64 g_PcapLogTrace
0x180004662  call    AslLogCreate
0x180004667  mov     rcx, cs:?g_PcapLogTrace@@3_KA; unsigned __int64 g_PcapLogTrace
0x18000466e  call    AslLogPublishToPeb
0x180004673  lea     rdx, aPcaclidebug; "PcaCliDebug"
0x18000467a  lea     rcx, ?g_PcapLogDebug@@3_KA; unsigned __int64 g_PcapLogDebug
0x180004681  call    AslLogCreate
0x180004686  mov     rcx, cs:?g_PcapLogDebug@@3_KA; unsigned __int64 g_PcapLogDebug
0x18000468d  lea     rax, ?PcapTraceDebugCallback@@YAXW4ASL_LOG_LEVEL@@PEBD_K1PEAD@Z; PcapTraceDebugCallback(ASL_LOG_LEVEL,char const *,unsigned __int64,char const *,char *)
0x180004694  mov     cs:g_AslLogPfnVPrintf, rax
0x18000469b  call    AslLogPublishToPeb
0x1800046a0  lea     rdx, aPcaclidebug; "PcaCliDebug"
0x1800046a7  lea     rcx, ?g_PcaTelemetry@@3_KA; unsigned __int64 g_PcaTelemetry
0x1800046ae  add     rsp, 28h
0x1800046b2  jmp     AslTelemetryCreate
```
