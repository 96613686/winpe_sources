# CXaEnlist_State_Aborting::Enter_State(CXaEnlist *)

- ea: `0x1800a8de0`
- end: `0x1800a8f36`
- name: `?Enter_State@CXaEnlist_State_Aborting@@UEAAXPEAVCXaEnlist@@@Z`
- size: `342`
- prototype: `void __fastcall(CXaEnlist_State_Aborting *__hidden this, struct CXaEnlist *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800a7db0`

## callees

- `0x1800240b0`
- `0x18009abb8`
- `0x18009df64`
- `0x18009e338`
- `0x1800a2ce0`
- `0x1800a8de0`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8ee9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8ee9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8e92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8e92`

## string_xrefs

- `0x1800a8f03`: `com\complus\dtc\dtc\xatm\src\xaenlist.cpp`
- `0x1800a8f0a`: `CRollbackTask`

## pseudocode

```c

```
