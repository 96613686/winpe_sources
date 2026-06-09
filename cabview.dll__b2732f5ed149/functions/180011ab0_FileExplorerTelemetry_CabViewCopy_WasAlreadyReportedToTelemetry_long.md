# FileExplorerTelemetry::CabViewCopy::WasAlreadyReportedToTelemetry(long)

- ea: `0x180011ab0`
- end: `0x180011abe`
- name: `?WasAlreadyReportedToTelemetry@CabViewCopy@FileExplorerTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(FileExplorerTelemetry::CabViewCopy *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall FileExplorerTelemetry::CabViewCopy::WasAlreadyReportedToTelemetry(
        FileExplorerTelemetry::CabViewCopy *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x180011ab0  mov     eax, edx
0x180011ab2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x180011ab8  cmp     eax, edx
0x180011aba  setz    al
0x180011abd  retn
```
