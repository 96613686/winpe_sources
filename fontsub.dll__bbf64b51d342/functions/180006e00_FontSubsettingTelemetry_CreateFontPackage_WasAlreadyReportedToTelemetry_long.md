# FontSubsettingTelemetry::CreateFontPackage::WasAlreadyReportedToTelemetry(long)

- ea: `0x180006e00`
- end: `0x180006e0e`
- name: `?WasAlreadyReportedToTelemetry@CreateFontPackage@FontSubsettingTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(FontSubsettingTelemetry::CreateFontPackage *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall FontSubsettingTelemetry::CreateFontPackage::WasAlreadyReportedToTelemetry(
        FontSubsettingTelemetry::CreateFontPackage *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x180006e00  mov     eax, edx
0x180006e02  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x180006e08  cmp     eax, edx
0x180006e0a  setz    al
0x180006e0d  retn
```
