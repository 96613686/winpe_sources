# CscSec_LookupAccountName(ushort const *,ushort const *,void * *,ushort * *,_SID_NAME_USE *)

- ea: `0x180080990`
- end: `0x180080acb`
- name: `?CscSec_LookupAccountName@@YAJPEBG0PEAPEAXPEAPEAGPEAW4_SID_NAME_USE@@@Z`
- size: `315`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, void **, unsigned __int16 **, enum _SID_NAME_USE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800611e0`

## callees

- `0x18000d640`
- `0x18001be00`
- `0x18002edf8`
- `0x18002f10c`
- `0x180080990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a02`
- `ADVAPI32!LookupAccountNameW` at `0x1800809ee`
- `ADVAPI32!LookupAccountNameW` at `0x180080a85`
- `ADVAPI32!LookupAccountNameW` at `0x1800809ee`
- `ADVAPI32!LookupAccountNameW` at `0x180080a85`

## pseudocode

```c

```
