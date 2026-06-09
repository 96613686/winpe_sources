# CTSSession::DisconnectSession(ulong,ulong,ITerminal * *)

- ea: `0x180032424`
- end: `0x180032e4d`
- name: `?DisconnectSession@CTSSession@@AEAAJKKPEAPEAUITerminal@@@Z`
- size: `2601`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, unsigned int, unsigned int, struct ITerminal **)`
- caller_count: `8`
- callee_count: `43`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180033ac0`
- `0x180045be0`
- `0x180046c80`
- `0x1800477b0`
- `0x18006731c`
- `0x180069230`
- `0x180069f40`
- `0x18006f910`

## callees

- `0x180002a48`
- `0x1800074c0`
- `0x180008f04`
- `0x180008f64`
- `0x1800092a4`
- `0x1800093d0`
- `0x1800093f8`
- `0x180009420`
- `0x18000944c`
- `0x180009810`
- `0x180009a68`
- `0x180009b2c`
- `0x18000a2a4`
- `0x18000a4d0`
- `0x18000a5d0`
- `0x18000a6f0`
- `0x18000aad4`
- `0x180010fb0`
- `0x180018200`
- `0x18001ce00`
- `0x18001f064`
- `0x18001fd20`
- `0x180020ea0`
- `0x180022d58`
- `0x1800242f0`
- `0x1800245e4`
- `0x180024884`
- `0x180024910`
- `0x180024b9c`
- `0x180025070`
- `0x180028784`
- `0x18002a83c`
- `0x18002eaa0`
- `0x18002f624`
- `0x180032424`
- `0x18004b460`
- `0x1800689c8`
- `0x180068a38`
- `0x180069880`
- `0x18006caec`
- `0x18006eed4`
- `0x180094040`
- `0x180097010`

## import_xrefs

- `ntdll!RtlConvertSharedToExclusive` at `0x180032784`
- `ntdll!RtlConvertSharedToExclusive` at `0x18003291f`
- `ntdll!RtlConvertSharedToExclusive` at `0x180032784`
- `ntdll!RtlConvertSharedToExclusive` at `0x18003291f`
- `ntdll!RtlConvertExclusiveToShared` at `0x180032700`
- `ntdll!RtlConvertExclusiveToShared` at `0x18003289e`
- `ntdll!RtlConvertExclusiveToShared` at `0x180032700`
- `ntdll!RtlConvertExclusiveToShared` at `0x18003289e`
- `ntdll!NtQuerySystemTime` at `0x180032b9d`
- `ntdll!NtQuerySystemTime` at `0x180032b9d`
- `ntdll!EtwEventActivityIdControl` at `0x1800324e3`
- `ntdll!EtwEventActivityIdControl` at `0x1800324e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800328a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800328c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800328a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800328c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180032be9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180032be9`

## string_xrefs

- `0x180032b22`: `Task completed successfully`
- `0x180032828`: `Skipping SendDisconnectMsg since it was already sent`

## pseudocode

```c

```
