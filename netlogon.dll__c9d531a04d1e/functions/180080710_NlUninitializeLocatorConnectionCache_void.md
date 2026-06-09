# NlUninitializeLocatorConnectionCache(void)

- ea: `0x180080710`
- end: `0x18008083d`
- name: `?NlUninitializeLocatorConnectionCache@@YAXXZ`
- size: `301`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000d1f0`
- `0x180028834`

## callees

- `0x18000d710`
- `0x180018414`
- `0x18001843c`
- `0x180080710`
- `0x180081130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180080809`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180080809`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080760`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080760`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18008076d`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180080797`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x1800807e0`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18008076d`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180080797`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x1800807e0`

## string_xrefs

- `0x18008077d`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x1800807ad`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\ldapcache.cxx`
- `0x1800807b4`: `RtlNumberGenericTableElementsAvl(&_connectionCache) == _connectionCacheCount`
- `0x180080784`: `RtlNumberGenericTableElementsAvl(&_connectionCache) == 0`

## pseudocode

```c

```
