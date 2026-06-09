# CleanupMgrTelemetry::PurgeClients::WasAlreadyReportedToTelemetry(long)

- ea: `0x140011fd0`
- end: `0x140011fde`
- name: `?WasAlreadyReportedToTelemetry@PurgeClients@CleanupMgrTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(CleanupMgrTelemetry::PurgeClients *this, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall CleanupMgrTelemetry::PurgeClients::WasAlreadyReportedToTelemetry(
        CleanupMgrTelemetry::PurgeClients *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x140011fd0  mov     eax, edx
0x140011fd2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x140011fd8  cmp     eax, edx
0x140011fda  setz    al
0x140011fdd  retn
```
