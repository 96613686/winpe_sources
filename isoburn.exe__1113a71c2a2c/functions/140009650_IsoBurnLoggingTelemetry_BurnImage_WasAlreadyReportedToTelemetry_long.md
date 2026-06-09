# IsoBurnLoggingTelemetry::BurnImage::WasAlreadyReportedToTelemetry(long)

- ea: `0x140009650`
- end: `0x14000965e`
- name: `?WasAlreadyReportedToTelemetry@BurnImage@IsoBurnLoggingTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(IsoBurnLoggingTelemetry::BurnImage *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall IsoBurnLoggingTelemetry::BurnImage::WasAlreadyReportedToTelemetry(
        IsoBurnLoggingTelemetry::BurnImage *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x140009650  mov     eax, edx
0x140009652  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x140009658  cmp     eax, edx
0x14000965a  setz    al
0x14000965d  retn
```
