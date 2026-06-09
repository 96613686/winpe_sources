# CROIDTable::ClientBulkUpdateOIDWithPingServer(ulong,ulong)

- ea: `0x180099410`
- end: `0x180099fea`
- name: `?ClientBulkUpdateOIDWithPingServer@CROIDTable@@CAJKK@Z`
- size: `3034`
- prototype: `HRESULT __fastcall(unsigned int cOxidsToRemove, unsigned int cSOidsToUnpin)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180099334`
- `0x1800993a8`
- `0x1801244d0`

## callees

- `0x180006250`
- `0x18000712c`
- `0x18003a8bc`
- `0x180040078`
- `0x180075da4`
- `0x180077a10`
- `0x1800865f4`
- `0x18008cbe4`
- `0x180099410`
- `0x1800bf288`
- `0x1800fafc4`
- `0x180130b34`
- `0x180189448`
- `0x1801999b0`
- `0x180199d80`
- `0x18019a080`

## import_xrefs

- `RPCRT4!NdrClientCall2` at `0x180099ce7`
- `RPCRT4!NdrClientCall2` at `0x180099ce7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099564`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009962f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099564`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009962f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099943`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099f30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099f47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099943`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099f30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099f47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800999e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099b4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099ba1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099c4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099f12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800999e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099b4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099ba1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099c4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099f12`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180099d6e`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180099d6e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180099d55`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180099d55`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180099a3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180099a3b`

## string_xrefs

- `0x180099e35`: `onecore\com\combase\dcomrem\idobj.cxx`
- `0x180099a08`: `onecore\com\combase\dcomrem\ipidtbl.cxx`
- `0x180099bd0`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x180099d44`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x18009957e`: `onecore\com\combase\dcomrem\refcache.cxx`
- `0x1800999f1`: `onecore\com\combase\dcomrem\refcache.cxx`
- `0x180099e0d`: `onecore\com\combase\dcomrem\refcache.cxx`
- `0x180099faa`: `onecore\com\combase\dcomrem\refcache.cxx`
- `0x180099dfb`: `CROIDTable::ClientBulkUpdateOIDWithPingServer`
- `0x180099de4`: `SCM bulk update OIDs, to add: %d (%ws), to remove: %d (%ws), status %08X`

## pseudocode

```c

```
