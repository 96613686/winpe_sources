# CAepStoreAccess::GetProperties(ushort const *,ulong,ulong,_DEVPROPCOMPKEY const *,ulong *,_DEVPROPERTY const * *)

- ea: `0x1800424c0`
- end: `0x180042638`
- name: `?GetProperties@CAepStoreAccess@@UEAAJPEBGKKPEBU_DEVPROPCOMPKEY@@PEAKPEAPEBU_DEVPROPERTY@@@Z`
- size: `376`
- prototype: `int(CAepStoreAccess *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const struct _DEVPROPCOMPKEY *, unsigned int *, const struct _DEVPROPERTY **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009590`
- `0x1800248dc`
- `0x18003bc80`
- `0x1800424c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004259d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004259d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042602`
- `api-ms-win-devices-query-l1-1-1!DevGetObjectPropertiesEx` at `0x1800425ef`
- `api-ms-win-devices-query-l1-1-1!DevGetObjectPropertiesEx` at `0x1800425ef`

## pseudocode

```c

```
