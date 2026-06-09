# ZtInitConfig(_ZTDNS_SETTINGS_TYPE,HKEY__ *,_DNS_ZT_SETTINGS * *)

- ea: `0x180054e40`
- end: `0x18005518a`
- name: `?ZtInitConfig@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAUHKEY__@@PEAPEAU_DNS_ZT_SETTINGS@@@Z`
- size: `842`
- prototype: `__int64 __fastcall(int, HKEY, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180055ac4`

## callees

- `0x18002b1f0`
- `0x180046ec0`
- `0x180054e40`
- `0x180055294`
- `0x180068c74`
- `0x180086b1c`
- `0x180086eb4`

## import_xrefs

- `DNSAPI!DnsFreeZtSettings` at `0x180055103`
- `DNSAPI!DnsFreeZtSettings` at `0x180055103`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180054fa1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180054fa1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054f0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054f0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800550f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800550f5`

## pseudocode

```c

```
