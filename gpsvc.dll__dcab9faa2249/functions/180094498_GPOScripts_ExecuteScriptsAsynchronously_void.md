# GPOScripts::ExecuteScriptsAsynchronously(void *)

- ea: `0x180094498`
- end: `0x180094796`
- name: `?ExecuteScriptsAsynchronously@GPOScripts@@AEAAKPEAX@Z`
- size: `766`
- prototype: `__int64 __fastcall(GPOScripts *this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022d38`

## callees

- `0x180021e54`
- `0x180066684`
- `0x180075ec0`
- `0x18007de08`
- `0x180094498`
- `0x1800950d0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180094705`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180094705`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180094691`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180094691`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800946b1`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800946b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094772`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094772`
- `ntdll!NtSetInformationProcess` at `0x1800946a7`
- `ntdll!NtSetInformationProcess` at `0x1800946a7`

## string_xrefs

- `0x180094720`: `GPOScripts::ExecuteScriptsAsynchronously: Completed WaitForSingleObject.`
- `0x180094743`: `GPOScripts::ExecuteScriptsAsynchronously: Completed WaitForSingleObject.`

## pseudocode

```c

```
