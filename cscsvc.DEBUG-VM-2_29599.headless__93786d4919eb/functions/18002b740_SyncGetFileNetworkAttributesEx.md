# SyncGetFileNetworkAttributesEx

- ea: `0x18002b740`
- end: `0x18002bb03`
- name: `SyncGetFileNetworkAttributesEx`
- size: `963`
- prototype: `__int64 __fastcall(HANDLE hHandle, PVOID FileInformation)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035ad8`

## callees

- `0x18002b740`
- `0x180030634`
- `0x180030bf0`
- `0x1800360c0`
- `0x180036394`
- `0x180039610`
- `0x18003c460`
- `0x18005fa04`
- `0x180072758`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x18002b7e3`
- `ntdll!NtQueryInformationFile` at `0x18002b7e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b7fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b7fa`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002b902`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002b9e5`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002b902`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002b9e5`
- `KERNEL32!FileTimeToSystemTime` at `0x18002b8ee`
- `KERNEL32!FileTimeToSystemTime` at `0x18002b9d1`
- `KERNEL32!FileTimeToSystemTime` at `0x18002b8ee`
- `KERNEL32!FileTimeToSystemTime` at `0x18002b9d1`

## string_xrefs

- `0x18002b955`: `SyncItemPrintTime:    CURRENT : %02d/%02d/%d  %02d:%02d:%02d.%d`
- `0x18002ba14`: `SyncItemPrintTime:    CURRENT : %02d/%02d/%d  %02d:%02d:%02d.%d`
- `0x18002b845`: `SyncGetFileNetworkAttributesEx: This server does not support FileNetworkOpenInformation -- combining Basic and Standard`

## pseudocode

```c

```
