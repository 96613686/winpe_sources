# NlSetDsSPN(uchar,uchar,uchar,uchar,_DOMAIN_INFO *,ushort *,ushort *,ushort *,ulong,uchar)

- ea: `0x18005cdb4`
- end: `0x18005d081`
- name: `?NlSetDsSPN@@YAKEEEEPEAU_DOMAIN_INFO@@PEAG11KE@Z`
- size: `717`
- prototype: `unsigned int __fastcall(unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int8, struct _DOMAIN_INFO *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *Src, unsigned int, char)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18002e03c`
- `0x180060840`
- `0x18006e50c`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x180025eb8`
- `0x18005cdb4`
- `0x18005d090`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005ce66`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005ce66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cf00`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cf00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d070`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d070`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18005d05d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18005d05d`
- `ntdll!RtlLeaveCriticalSection` at `0x18005ce79`
- `ntdll!RtlLeaveCriticalSection` at `0x18005ce79`
- `ntdll!RtlEnterCriticalSection` at `0x18005ce4c`
- `ntdll!RtlEnterCriticalSection` at `0x18005ce4c`

## string_xrefs

- `0x18005cf37`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005d034`: `NlSetDsSPN: Queuing SPN update for %ws on %ws.\n`

## pseudocode

```c

```
