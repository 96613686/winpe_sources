# DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::WasAlreadyReportedToTelemetry(long)

- ea: `0x14000d490`
- end: `0x14000d49e`
- name: `?WasAlreadyReportedToTelemetry@CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *this, __int32)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
bool __fastcall DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::WasAlreadyReportedToTelemetry(
        DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x14000d490  mov     eax, edx
0x14000d492  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x14000d498  cmp     eax, edx
0x14000d49a  setz    al
0x14000d49d  retn
```
