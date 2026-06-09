# GetPlginCLSID(HKEY__ *,_GUID *)

- ea: `0x1001a2cc`
- end: `0x1001a31d`
- name: `?GetPlginCLSID@@YGJPAUHKEY__@@PAU_GUID@@@Z`
- size: `81`
- prototype: `int __cdecl(HKEY, struct _GUID *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1001a323`
- `0x1001a414`

## callees

- `0x1001a2cc`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1001a2ed`
- `ADVAPI32!RegQueryValueExW` at `0x1001a2ed`

## pseudocode

```c

```
