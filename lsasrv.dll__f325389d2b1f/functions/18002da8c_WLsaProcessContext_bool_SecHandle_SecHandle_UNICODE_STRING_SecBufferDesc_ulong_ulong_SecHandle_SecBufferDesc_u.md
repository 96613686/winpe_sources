# WLsaProcessContext(bool,_SecHandle *,_SecHandle *,_UNICODE_STRING *,_SecBufferDesc *,ulong,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x18002da8c`
- end: `0x18002ea79`
- name: `?WLsaProcessContext@@YAJ_NPEAU_SecHandle@@1PEAU_UNICODE_STRING@@PEAU_SecBufferDesc@@KK13PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `4077`
- prototype: `int(bool, struct _SecHandle *, struct _SecHandle *, struct _UNICODE_STRING *, struct _SecBufferDesc *, unsigned int, unsigned int, struct _SecHandle *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `6`
- callee_count: `29`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019010`
- `0x18002c710`
- `0x18002d880`
- `0x18002d990`
- `0x18002ec1c`
- `0x180030828`

## callees

- `0x180009734`
- `0x18000b7d0`
- `0x180011278`
- `0x180026ef4`
- `0x180027010`
- `0x1800273ac`
- `0x1800284d4`
- `0x18002a2a8`
- `0x18002d5c4`
- `0x18002d7a0`
- `0x18002da8c`
- `0x180073c40`
- `0x18007694c`
- `0x1800779ac`
- `0x180077b00`
- `0x1800788d8`
- `0x180080388`
- `0x180082214`
- `0x180097c3c`
- `0x18009e644`
- `0x18009eeb4`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800c1308`
- `0x1800c136c`
- `0x1800c820c`
- `0x1800c83fc`
- `0x1800debd4`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002db88`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002dba5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e9c6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002db88`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002dba5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e9c6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002dd06`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002dfe8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002e10f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002dd06`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002dfe8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002e10f`
- `ntdll!NtQueryInformationToken` at `0x18002e5db`
- `ntdll!NtQueryInformationToken` at `0x18002e5db`

## string_xrefs

- `0x18002e0d4`: `InitializeSecurityContext`
- `0x18002e8ad`: `InitializeSecurityContext`
- `0x18002e0cd`: `AcceptSecurityContext`

## pseudocode

```c

```
