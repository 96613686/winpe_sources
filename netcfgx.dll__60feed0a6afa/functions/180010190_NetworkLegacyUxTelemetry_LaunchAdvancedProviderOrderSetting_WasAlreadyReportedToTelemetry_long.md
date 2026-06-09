# NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::WasAlreadyReportedToTelemetry(long)

- ea: `0x180010190`
- end: `0x18001019e`
- name: `?WasAlreadyReportedToTelemetry@LaunchAdvancedProviderOrderSetting@NetworkLegacyUxTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
bool __fastcall NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::WasAlreadyReportedToTelemetry(
        NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x180010190  mov     eax, edx
0x180010192  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x180010198  cmp     eax, edx
0x18001019a  setz    al
0x18001019d  retn
```
