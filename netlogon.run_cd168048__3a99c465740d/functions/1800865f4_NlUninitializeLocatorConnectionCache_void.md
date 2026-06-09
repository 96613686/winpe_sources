# NlUninitializeLocatorConnectionCache(void)

- ea: `0x1800865f4`
- end: `0x180086740`
- name: `?NlUninitializeLocatorConnectionCache@@YAXXZ`
- size: `332`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180029d5c`
- `0x180079874`

## callees

- `0x18000dd00`
- `0x180018f38`
- `0x180018f68`
- `0x1800865f4`
- `0x1800870ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180086705`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180086705`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180086644`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180086644`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180086657`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180086687`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x1800866d6`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180086657`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180086687`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x1800866d6`

## string_xrefs

- `0x18008666d`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x1800866a3`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x1800866aa`: `RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount`
- `0x180086674`: `RtlNumberGenericTableElementsAvl(&_connectionCache) == 0`

## pseudocode

```c

```
