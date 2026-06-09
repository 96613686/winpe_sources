# DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::WasAlreadyReportedToTelemetry(long)

- ea: `0x14000f6d0`
- end: `0x14000f6de`
- name: `?WasAlreadyReportedToTelemetry@DXGIAdapterCacheHealthActivity@DXGIAdapterCacheTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *this, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::WasAlreadyReportedToTelemetry(
        DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x14000f6d0  mov     eax, edx
0x14000f6d2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x14000f6d8  cmp     eax, edx
0x14000f6da  setz    al
0x14000f6dd  retn
```
