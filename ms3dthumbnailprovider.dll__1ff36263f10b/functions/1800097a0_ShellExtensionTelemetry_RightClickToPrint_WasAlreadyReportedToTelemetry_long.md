# ShellExtensionTelemetry::RightClickToPrint::WasAlreadyReportedToTelemetry(long)

- ea: `0x1800097a0`
- end: `0x1800097ae`
- name: `?WasAlreadyReportedToTelemetry@RightClickToPrint@ShellExtensionTelemetry@@MEAA_NJ@Z`
- size: `14`
- prototype: `bool __fastcall(ShellExtensionTelemetry::RightClickToPrint *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
bool __fastcall ShellExtensionTelemetry::RightClickToPrint::WasAlreadyReportedToTelemetry(
        ShellExtensionTelemetry::RightClickToPrint *this,
        __int32 a2)
{
  return _InterlockedExchange(&`wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry'::`2'::s_lastFailureSeen, a2) == a2;
}

```

## disassembly

```asm
0x1800097a0  mov     eax, edx
0x1800097a2  xchg    eax, cs:?s_lastFailureSeen@?1??WasAlreadyReportedToTelemetry@TraceLoggingProvider@wil@@KA_NJ@Z@4JC; long volatile `wil::TraceLoggingProvider::WasAlreadyReportedToTelemetry(long)'::`2'::s_lastFailureSeen
0x1800097a8  cmp     eax, edx
0x1800097aa  setz    al
0x1800097ad  retn
```
