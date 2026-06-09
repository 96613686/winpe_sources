# PlaiCallFileCallback<_DELETE_EXCEPT_CTX *,long (*)(ushort const *,ulong,_WIN32_FIND_DATAW *,_DELETE_EXCEPT_CTX *)>(ushort const *,ushort const *,ulong,ushort *,unsigned __int64,long (*)(ushort const *,ulong,_WIN32_FIND_DATAW *,_DELETE_EXCEPT_CTX *),_DELETE_EXCEPT_CTX *)

- ea: `0x18006f9e8`
- end: `0x18006fde3`
- name: `??$PlaiCallFileCallback@PEAU_DELETE_EXCEPT_CTX@@P6AJPEBGKPEAU_WIN32_FIND_DATAW@@PEAU1@@Z@@YAJPEBG0KPEAG_KP6AJ0KPEAU_WIN32_FIND_DATAW@@PEAU_DELETE_EXCEPT_CTX@@@Z4@Z`
- size: `1019`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, unsigned __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800e3874`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x180046c60`
- `0x18006f9e8`
- `0x180138778`
- `0x18013ae9a`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fc58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fc58`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006fb44`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006fb44`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006fc4b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006fc4b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006fc7a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006fc7a`

## pseudocode

```c

```
