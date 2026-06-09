# UserTargetInfo::ProcessWatchTraceEvent(_DBGKD_TRACE_DATA *,_ADDR *,INTERNAL_CMD_STATE *)

- ea: `0x1800b0fb0`
- end: `0x1800b153d`
- name: `?ProcessWatchTraceEvent@UserTargetInfo@@UEAAXPEAT_DBGKD_TRACE_DATA@@PEAU_ADDR@@PEAW4INTERNAL_CMD_STATE@@@Z`
- size: `1421`
- prototype: `void(UserTargetInfo *__hidden this, union _DBGKD_TRACE_DATA *, struct _ADDR *, enum INTERNAL_CMD_STATE *)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callees

- `0x180072c8c`
- `0x1800793cc`
- `0x1800797ec`
- `0x18007c2dc`
- `0x18007cf9c`
- `0x18008d550`
- `0x1800b0fb0`
- `0x1800b1544`
- `0x1800c12b8`
- `0x1800f0f40`
- `0x18029c1d0`
- `0x18029c848`
- `0x18029ca24`
- `0x18029dd9c`
- `0x18029e200`
- `0x18029e37c`
- `0x1804da3a3`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800b1363`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800b138d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800b14dc`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800b14fb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800b1363`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800b138d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800b14dc`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800b14fb`

## string_xrefs

- `0x1800b1386`: `ntdll!_ZwCallbackReturn`
- `0x1800b135c`: `ntdll!_KiUserCallBackDispatcher`
- `0x1800b14d5`: `ntdll!ZwRaiseException`
- `0x1800b14f4`: `ntdll!_ZwRaiseException`

## pseudocode

```c

```
