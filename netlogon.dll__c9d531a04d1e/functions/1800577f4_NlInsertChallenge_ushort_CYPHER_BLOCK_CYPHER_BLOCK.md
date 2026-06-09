# NlInsertChallenge(ushort *,_CYPHER_BLOCK *,_CYPHER_BLOCK *)

- ea: `0x1800577f4`
- end: `0x180057a6b`
- name: `?NlInsertChallenge@@YAJPEAGPEAU_CYPHER_BLOCK@@1@Z`
- size: `631`
- prototype: `__int64 __fastcall(unsigned __int16 *Src, struct _CYPHER_BLOCK *, struct _CYPHER_BLOCK *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005ef30`

## callees

- `0x180007278`
- `0x1800577f4`
- `0x180058218`
- `0x180058434`
- `0x180074038`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand_s` at `0x1800578da`
- `api-ms-win-crt-private-l1-1-0!_o_rand_s` at `0x1800578da`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180057a2e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180057a2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005784d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005784d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800578e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800578e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800579e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800579e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180057865`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180057865`
- `ntdll!RtlLeaveCriticalSection` at `0x1800578f4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800579b9`
- `ntdll!RtlLeaveCriticalSection` at `0x180057a56`
- `ntdll!RtlLeaveCriticalSection` at `0x1800578f4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800579b9`
- `ntdll!RtlLeaveCriticalSection` at `0x180057a56`
- `ntdll!RtlEnterCriticalSection` at `0x1800578a0`
- `ntdll!RtlEnterCriticalSection` at `0x1800579de`
- `ntdll!RtlEnterCriticalSection` at `0x1800578a0`
- `ntdll!RtlEnterCriticalSection` at `0x1800579de`

## string_xrefs

- `0x180057825`: `ComputerName too long: %ws\n`

## pseudocode

```c

```
