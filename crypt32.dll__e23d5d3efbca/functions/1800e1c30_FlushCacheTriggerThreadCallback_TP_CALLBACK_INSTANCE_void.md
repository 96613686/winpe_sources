# _FlushCacheTriggerThreadCallback(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x1800e1c30`
- end: `0x1800e1eec`
- name: `?_FlushCacheTriggerThreadCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `700`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _DWORD *Context)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180010610`
- `0x180028d60`
- `0x18005665c`
- `0x180056cc8`
- `0x1800bec20`
- `0x1800c65d0`
- `0x1800e1b60`
- `0x1800e1c30`
- `0x1800f0f14`
- `0x1800f3854`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e1da5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e1da5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e1d74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e1d74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e1c73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e1c73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e1cef`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e1e37`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e1e93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e1cef`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e1e37`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e1e93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1de9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1de9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e1ccf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e1ccf`
- `ntdll!RtlPublishWnfStateData` at `0x1800e1d18`
- `ntdll!RtlPublishWnfStateData` at `0x1800e1e63`
- `ntdll!RtlPublishWnfStateData` at `0x1800e1eb9`
- `ntdll!RtlPublishWnfStateData` at `0x1800e1d18`
- `ntdll!RtlPublishWnfStateData` at `0x1800e1e63`
- `ntdll!RtlPublishWnfStateData` at `0x1800e1eb9`

## pseudocode

```c

```
