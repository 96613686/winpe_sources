# DWriteTraceLogging::RegisterClientSideTraceLogging(void)

- ea: `0x1801deb24`
- end: `0x1801debcf`
- name: `?RegisterClientSideTraceLogging@DWriteTraceLogging@@YAXXZ`
- size: `171`
- prototype: `void __fastcall(DWriteTraceLogging *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1801ed1ac`

## callees

- `0x1801debd8`
- `0x180212490`

## import_xrefs

- `rpcrt4!UuidCreate` at `0x1801deb49`
- `rpcrt4!UuidCreate` at `0x1801deb49`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801deb79`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801deb9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801deb79`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801deb9b`

## pseudocode

```c
void __fastcall DWriteTraceLogging::RegisterClientSideTraceLogging(DWriteTraceLogging *this)
{
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  TraceLoggingRegisterEx_EventRegister_EventSetInformation(this);
  Uuid = 0;
  UuidCreate(&Uuid);
  DWriteTraceLogging::g_telemetryClientAggregator = (__int64)&g_hDWriteTraceLoggingProvider;
  xmmword_1804B4CCC = (__int128)Uuid;
  DWriteTraceLogging::g_telemetryFileUsageAggregator = &g_hDWriteTraceLoggingProvider;
  xmmword_1804B8630 = (__int128)Uuid;
  qword_1804B4CE8 = GetTickCount64();
  qword_1804B4CE0 = 20000;
  dword_1804B4CF0 = 0;
  qword_1804B8648 = GetTickCount64();
  qword_1804B8640 = 20000;
  dword_1804B8650 = 0;
}

```

## disassembly

```asm
0x1801deb24  sub     rsp, 48h
0x1801deb28  mov     rax, cs:__security_cookie
0x1801deb2f  xor     rax, rsp
0x1801deb32  mov     [rsp+48h+var_18], rax
0x1801deb37  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1801deb3c  xorps   xmm0, xmm0
0x1801deb3f  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1801deb44  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1801deb49  call    cs:__imp_UuidCreate
0x1801deb4f  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x1801deb54  lea     rax, g_hDWriteTraceLoggingProvider
0x1801deb5b  mov     cs:?g_telemetryClientAggregator@DWriteTraceLogging@@3V?$Aggregator@VTraceLoggingTimePolicy@DWriteTraceLogging@@V?$AggregationCircularArrayData@UDownloadOperationStats@DWriteTraceLogging@@$0BE@$0A@@2@UDownloadOperationStats@2@@1@A, rax; DWriteTraceLogging::Aggregator<DWriteTraceLogging::TraceLoggingTimePolicy,DWriteTraceLogging::AggregationCircularArrayData<DWriteTraceLogging::DownloadOperationStats,20,0>,DWriteTraceLogging::DownloadOperationStats> DWriteTraceLogging::g_telemetryClientAggregator
0x1801deb62  movdqu  cs:xmmword_1804B4CCC, xmm0
0x1801deb6a  mov     cs:?g_telemetryFileUsageAggregator@DWriteTraceLogging@@3V?$Aggregator@VTraceLoggingTimePolicy@DWriteTraceLogging@@VAggregationFontUsageLocationData@2@UFontUsageLocationInfo@2@@1@A, rax; DWriteTraceLogging::Aggregator<DWriteTraceLogging::TraceLoggingTimePolicy,DWriteTraceLogging::AggregationFontUsageLocationData,DWriteTraceLogging::FontUsageLocationInfo> DWriteTraceLogging::g_telemetryFileUsageAggregator
0x1801deb71  movdqu  cs:xmmword_1804B8630, xmm0
0x1801deb79  call    cs:__imp_GetTickCount64
0x1801deb7f  mov     cs:qword_1804B4CE8, rax
0x1801deb86  mov     cs:qword_1804B4CE0, 4E20h
0x1801deb91  mov     cs:dword_1804B4CF0, 0
0x1801deb9b  call    cs:__imp_GetTickCount64
0x1801deba1  mov     cs:qword_1804B8648, rax
0x1801deba8  mov     cs:qword_1804B8640, 4E20h
0x1801debb3  mov     cs:dword_1804B8650, 0
0x1801debbd  mov     rcx, [rsp+48h+var_18]
0x1801debc2  xor     rcx, rsp; StackCookie
0x1801debc5  call    __security_check_cookie
0x1801debca  add     rsp, 48h
0x1801debce  retn
```
