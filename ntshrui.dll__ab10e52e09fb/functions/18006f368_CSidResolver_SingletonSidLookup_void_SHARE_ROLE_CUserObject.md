# CSidResolver::SingletonSidLookup(void *,SHARE_ROLE,CUserObject * *)

- ea: `0x18006f368`
- end: `0x18006f49d`
- name: `?SingletonSidLookup@CSidResolver@@QEAAJPEAXW4SHARE_ROLE@@PEAPEAVCUserObject@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(CSidResolver *__hidden this, void *, enum SHARE_ROLE, struct CUserObject **)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180054d90`
- `0x180067504`
- `0x180069830`
- `0x18006c660`
- `0x18006fbcc`

## callees

- `0x180009830`
- `0x1800259bc`
- `0x180053fd4`
- `0x18006f368`
- `0x18006f6a4`
- `0x18006fb34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f476`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f476`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006f480`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006f48a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006f480`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006f48a`

## pseudocode

```c

```
