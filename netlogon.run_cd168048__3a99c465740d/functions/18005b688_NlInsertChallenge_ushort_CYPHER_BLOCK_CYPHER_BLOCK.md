# NlInsertChallenge(ushort *,_CYPHER_BLOCK *,_CYPHER_BLOCK *)

- ea: `0x18005b688`
- end: `0x18005b948`
- name: `?NlInsertChallenge@@YAJPEAGPEAU_CYPHER_BLOCK@@1@Z`
- size: `704`
- prototype: `__int64 __fastcall(unsigned __int16 *Src, struct _CYPHER_BLOCK *, struct _CYPHER_BLOCK *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800633a0`

## callees

- `0x180007518`
- `0x18005b688`
- `0x18005c14c`
- `0x18005c38c`
- `0x1800797bc`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand_s` at `0x18005b780`
- `api-ms-win-crt-private-l1-1-0!_o_rand_s` at `0x18005b780`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005b8f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005b8f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b908`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b908`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b6e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b6e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b793`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b793`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005b8ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005b8ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005b6ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005b6ff`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b7a6`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b871`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b92c`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b7a6`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b871`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b92c`
- `ntdll!RtlEnterCriticalSection` at `0x18005b740`
- `ntdll!RtlEnterCriticalSection` at `0x18005b89c`
- `ntdll!RtlEnterCriticalSection` at `0x18005b740`
- `ntdll!RtlEnterCriticalSection` at `0x18005b89c`

## string_xrefs

- `0x18005b6b9`: `ComputerName too long: %ws\n`

## pseudocode

```c

```
