# NlSetDsSPN(uchar,uchar,uchar,uchar,_DOMAIN_INFO *,ushort *,ushort *,ushort *,ulong,uchar)

- ea: `0x180058e0c`
- end: `0x1800590b4`
- name: `?NlSetDsSPN@@YAKEEEEPEAU_DOMAIN_INFO@@PEAG11KE@Z`
- size: `680`
- prototype: `unsigned int __fastcall(unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int8, struct _DOMAIN_INFO *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *Src, unsigned int, char)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18002c5b4`
- `0x18005c560`
- `0x180069580`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x180024e80`
- `0x180058e0c`
- `0x1800590c0`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180058eb8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180058eb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058f46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058f46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800590a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800590a9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18005909c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18005909c`
- `ntdll!RtlLeaveCriticalSection` at `0x180058ec5`
- `ntdll!RtlLeaveCriticalSection` at `0x180058ec5`
- `ntdll!RtlEnterCriticalSection` at `0x180058ea4`
- `ntdll!RtlEnterCriticalSection` at `0x180058ea4`

## string_xrefs

- `0x180058f77`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x180059073`: `NlSetDsSPN: Queuing SPN update for %ws on %ws.\n`

## pseudocode

```c

```
