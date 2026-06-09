# LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity::WasAlreadyReportedToTelemetry(long)

- ea: `0x14000c7a0`
- end: `0x14000c7ae`
- name: `?WasAlreadyReportedToTelemetry@LanguagePackRemovalActivity@LanguagePackDiskCleanupTraceProvider@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity *this, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity::WasAlreadyReportedToTelemetry(
        LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x14000c7a0  mov     eax, edx
0x14000c7a2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x14000c7a8  cmp     eax, edx
0x14000c7aa  setz    al
0x14000c7ad  retn
```
