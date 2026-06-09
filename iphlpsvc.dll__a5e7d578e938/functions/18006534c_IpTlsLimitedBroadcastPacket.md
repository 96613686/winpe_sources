# IpTlsLimitedBroadcastPacket

- ea: `0x18006534c`
- end: `0x1800655f2`
- name: `IpTlsLimitedBroadcastPacket`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180047530`

## callees

- `0x18000d7c0`
- `0x1800616b4`
- `0x1800646d8`
- `0x18006534c`
- `0x1800671c8`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x1800653c5`
- `ntdll!RtlLookupEntryHashTable` at `0x1800653c5`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800654ae`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800654ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800653a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800653a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800654df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800654df`

## string_xrefs

- `0x1800653d1`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800653e4`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800654d5`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c

```
