# IpTlsRemoveAllNeighborDiscoveryEntries

- ea: `0x1800473f4`
- end: `0x18004755c`
- name: `IpTlsRemoveAllNeighborDiscoveryEntries`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180064fc0`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180030d24`
- `0x1800473f4`
- `0x180047b38`

## import_xrefs

- `ntdll!RtlInitEnumerationHashTable` at `0x18004744a`
- `ntdll!RtlInitEnumerationHashTable` at `0x18004744a`
- `ntdll!RtlEnumerateEntryHashTable` at `0x1800474aa`
- `ntdll!RtlEnumerateEntryHashTable` at `0x1800474aa`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800474c5`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800474c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047430`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047430`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004745d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800474d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004745d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800474d4`

## string_xrefs

- `0x18004751e`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c

```
