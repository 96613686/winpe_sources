# MyCryptProtectData

- ea: `0x180012568`
- end: `0x1800127ef`
- name: `MyCryptProtectData`
- size: `647`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, int, DWORD dwMilliseconds, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013350`
- `0x180015ebc`
- `0x18005c848`
- `0x18005c920`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x180010fac`
- `0x180011548`
- `0x180012568`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180012727`
- `ntdll!RtlNtStatusToDosError` at `0x180012750`
- `ntdll!RtlNtStatusToDosError` at `0x180012727`
- `ntdll!RtlNtStatusToDosError` at `0x180012750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800127de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800127de`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800126bf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800126bf`
- `DPAPI!CryptProtectDataNoUI` at `0x1800125fa`
- `DPAPI!CryptProtectDataNoUI` at `0x1800125fa`

## string_xrefs

- `0x1800125c1`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180012795`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`

## pseudocode

```c

```
