# CTSSession::DisconnectSession(ulong,ulong,ITerminal * *)

- ea: `0x180034508`
- end: `0x180034f68`
- name: `?DisconnectSession@CTSSession@@AEAAJKKPEAPEAUITerminal@@@Z`
- size: `2656`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, unsigned int, unsigned int, struct ITerminal **)`
- caller_count: `8`
- callee_count: `43`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180035bf4`
- `0x180048d50`
- `0x180049d70`
- `0x18004a970`
- `0x18006b024`
- `0x18006d000`
- `0x18006dd70`
- `0x180073920`

## callees

- `0x180002a60`
- `0x1800077a0`
- `0x18000c17c`
- `0x18000c684`
- `0x180010ef8`
- `0x1800115a8`
- `0x1800118f4`
- `0x180011a28`
- `0x180011a50`
- `0x180011a78`
- `0x180011aa8`
- `0x180011e6c`
- `0x1800120d0`
- `0x180012194`
- `0x1800123b0`
- `0x1800124b4`
- `0x1800125d0`
- `0x18001266c`
- `0x1800129d0`
- `0x180014b20`
- `0x180021464`
- `0x180022030`
- `0x1800232c0`
- `0x180026124`
- `0x180026238`
- `0x180026548`
- `0x1800266bc`
- `0x180026748`
- `0x180026b1c`
- `0x18002701c`
- `0x180029f3c`
- `0x18002c878`
- `0x180030a7c`
- `0x180031650`
- `0x180034508`
- `0x18004e850`
- `0x18006c750`
- `0x18006c7c8`
- `0x18006d674`
- `0x1800709ac`
- `0x180072e84`
- `0x180099590`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlConvertSharedToExclusive` at `0x180034874`
- `ntdll!RtlConvertSharedToExclusive` at `0x180034a27`
- `ntdll!RtlConvertSharedToExclusive` at `0x180034874`
- `ntdll!RtlConvertSharedToExclusive` at `0x180034a27`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800347ea`
- `ntdll!RtlConvertExclusiveToShared` at `0x180034994`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800347ea`
- `ntdll!RtlConvertExclusiveToShared` at `0x180034994`
- `ntdll!NtQuerySystemTime` at `0x180034cab`
- `ntdll!NtQuerySystemTime` at `0x180034cab`
- `ntdll!EtwEventActivityIdControl` at `0x1800345c7`
- `ntdll!EtwEventActivityIdControl` at `0x1800345c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800349a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800349c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800349a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800349c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180034cfd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180034cfd`

## string_xrefs

- `0x180034c30`: `Task completed successfully`
- `0x18003491e`: `Skipping SendDisconnectMsg since it was already sent`

## pseudocode

```c

```
