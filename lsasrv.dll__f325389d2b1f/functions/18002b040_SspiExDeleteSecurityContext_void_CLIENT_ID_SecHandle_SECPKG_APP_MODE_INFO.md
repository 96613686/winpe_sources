# SspiExDeleteSecurityContext(void *,_CLIENT_ID *,_SecHandle *,_SECPKG_APP_MODE_INFO *)

- ea: `0x18002b040`
- end: `0x18002b382`
- name: `?SspiExDeleteSecurityContext@@YAJPEAXPEAU_CLIENT_ID@@PEAU_SecHandle@@PEAU_SECPKG_APP_MODE_INFO@@@Z`
- size: `834`
- prototype: `__int64 __fastcall(void *, struct _CLIENT_ID *, struct _SecHandle *, struct _SECPKG_APP_MODE_INFO *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180028528`
- `0x18002b040`
- `0x18002b390`
- `0x18002b8a0`
- `0x18005608c`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b125`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b19e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b125`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b19e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b170`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b185`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b1ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b371`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b170`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b185`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b1ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b371`
- `ntdll!RtlFreeHeap` at `0x18002b107`
- `ntdll!RtlFreeHeap` at `0x18002b107`
- `ntdll!NtClose` at `0x18002b0cf`
- `ntdll!NtClose` at `0x18002b253`
- `ntdll!NtClose` at `0x18002b2be`
- `ntdll!NtClose` at `0x18002b0cf`
- `ntdll!NtClose` at `0x18002b253`
- `ntdll!NtClose` at `0x18002b2be`
- `ntdll!NtSetInformationThread` at `0x18002b2a8`
- `ntdll!NtSetInformationThread` at `0x18002b2a8`

## pseudocode

```c

```
