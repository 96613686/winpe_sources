# LsapCallAuthPackagesForPreLogonSurrogate(void * *,_SECURITY_LOGON_TYPE,void *,_LSAP_LOGON_USER_ARGS *,_SECPKG_SURROGATE_LOGON *)

- ea: `0x180058878`
- end: `0x180058c79`
- name: `?LsapCallAuthPackagesForPreLogonSurrogate@@YAJPEAPEAXW4_SECURITY_LOGON_TYPE@@PEAXPEAU_LSAP_LOGON_USER_ARGS@@PEAU_SECPKG_SURROGATE_LOGON@@@Z`
- size: `1025`
- prototype: `__int64 __fastcall(void **, enum _SECURITY_LOGON_TYPE, void *, struct _LSAP_LOGON_USER_ARGS *, struct _SECPKG_SURROGATE_LOGON *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056fec`

## callees

- `0x180011278`
- `0x1800284d4`
- `0x180058878`
- `0x180058c80`
- `0x180058c98`
- `0x180058ca4`
- `0x180058cd8`
- `0x18005915c`
- `0x1800bd6e0`
- `0x1800c7d98`
- `0x1800debd4`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800588f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800588f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058908`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058908`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800588a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800588a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180058a13`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180058a3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180058b4e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180058b87`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180058a13`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180058a3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180058b4e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180058b87`
- `ntdll!RtlReleaseResource` at `0x1800589c4`
- `ntdll!RtlReleaseResource` at `0x1800589c4`
- `ntdll!RtlAcquireResourceShared` at `0x180058971`
- `ntdll!RtlAcquireResourceShared` at `0x180058971`

## pseudocode

```c

```
