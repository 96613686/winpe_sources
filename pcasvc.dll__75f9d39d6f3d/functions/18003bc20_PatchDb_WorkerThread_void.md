# PatchDb_WorkerThread(void *)

- ea: `0x18003bc20`
- end: `0x18003bd52`
- name: `?PatchDb_WorkerThread@@YAKPEAX@Z`
- size: `306`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18003bc20`
- `0x18003bd58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003bd1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003bd1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bc77`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bcd4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bc77`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bcd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd34`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003bcde`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003bcfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003bcde`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003bcfe`

## string_xrefs

- `0x18003bc54`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18003bcb0`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18003bc98`: `PatchDbUpdateTickCount`
- `0x18003bc3e`: `PatchDbUpdateInterval`

## pseudocode

```c

```
