# CXaEnlist_State_Preparing::Enter_State(CXaEnlist *)

- ea: `0x1800a9280`
- end: `0x1800a9406`
- name: `?Enter_State@CXaEnlist_State_Preparing@@UEAAXPEAVCXaEnlist@@@Z`
- size: `390`
- prototype: `void __fastcall(CXaEnlist_State_Preparing *__hidden this, struct CXaEnlist *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a9c40`

## callees

- `0x1800240b0`
- `0x1800846c0`
- `0x18009abb8`
- `0x18009df64`
- `0x1800a2ce0`
- `0x1800a9280`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a93b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a93b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a932d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a932d`

## string_xrefs

- `0x1800a9347`: `CPrepareTask::Init (com\complus\dtc\dtc\xatm\src\xataskmgr.cpp@1213): pszXaDll != NULL`
- `0x1800a93d1`: `com\complus\dtc\dtc\xatm\src\xaenlist.cpp`
- `0x1800a93d8`: `CPrepareTask`

## pseudocode

```c

```
