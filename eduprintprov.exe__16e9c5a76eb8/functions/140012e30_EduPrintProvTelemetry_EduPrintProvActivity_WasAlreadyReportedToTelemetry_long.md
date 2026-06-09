# EduPrintProvTelemetry::EduPrintProvActivity::WasAlreadyReportedToTelemetry(long)

- ea: `0x140012e30`
- end: `0x140012e3e`
- name: `?WasAlreadyReportedToTelemetry@EduPrintProvActivity@EduPrintProvTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(EduPrintProvTelemetry::EduPrintProvActivity *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall EduPrintProvTelemetry::EduPrintProvActivity::WasAlreadyReportedToTelemetry(
        EduPrintProvTelemetry::EduPrintProvActivity *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x140012e30  mov     eax, edx
0x140012e32  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x140012e38  cmp     eax, edx
0x140012e3a  setz    al
0x140012e3d  retn
```
