# IpTlsLimitedBroadcastPacket

- ea: `0x18006532c`
- end: `0x1800655d2`
- name: `IpTlsLimitedBroadcastPacket`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180047570`

## callees

- `0x18000d7b0`
- `0x180061694`
- `0x1800646b8`
- `0x18006532c`
- `0x1800671a8`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x1800653a5`
- `ntdll!RtlLookupEntryHashTable` at `0x1800653a5`
- `ntdll!RtlGetNextEntryHashTable` at `0x18006548e`
- `ntdll!RtlGetNextEntryHashTable` at `0x18006548e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065385`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065385`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800654bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800654bf`

## string_xrefs

- `0x1800653b1`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800653c4`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800654b5`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c

```
