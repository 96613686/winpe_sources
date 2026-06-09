# appinfosvc_close_jitv_silo(ulong,void *)

- ea: `0x1800828f8`
- end: `0x180082ba0`
- name: `?appinfosvc_close_jitv_silo@@YAXKPEAX@Z`
- size: `680`
- prototype: `void __fastcall(unsigned int, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007c4e0`
- `0x18007ca40`

## callees

- `0x180005794`
- `0x180005fac`
- `0x180010a84`
- `0x180013100`
- `0x18001432c`
- `0x180033538`
- `0x1800828f8`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082abf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082abf`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180082934`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008295b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180082934`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008295b`
- `msvcp_win!_Mtx_lock` at `0x18008291f`
- `msvcp_win!_Mtx_lock` at `0x18008291f`
- `msvcp_win!_Mtx_unlock` at `0x180082b48`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800829ec`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800829ec`

## string_xrefs

- `0x180082b8e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c

```
