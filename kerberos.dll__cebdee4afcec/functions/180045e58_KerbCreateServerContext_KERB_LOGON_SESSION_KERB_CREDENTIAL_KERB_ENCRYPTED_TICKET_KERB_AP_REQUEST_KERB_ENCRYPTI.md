# KerbCreateServerContext(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,KERB_ENCRYPTED_TICKET *,KERB_AP_REQUEST *,_KERB_ENCRYPTION_KEY *,_LUID *,void * *,ulong,ulong,ulong,ulong,ulong,void * *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_CONTEXT * *,_LARGE_INTEGER *)

- ea: `0x180045e58`
- end: `0x1800460f9`
- name: `?KerbCreateServerContext@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAUKERB_ENCRYPTED_TICKET@@PEAUKERB_AP_REQUEST@@PEAU_KERB_ENCRYPTION_KEY@@PEAU_LUID@@PEAPEAXKKKKK6PEAU_UNICODE_STRING@@77PEAPEAU_KERB_CONTEXT@@PEAT_LARGE_INTEGER@@@Z`
- size: `673`
- prototype: `int(struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, struct KERB_ENCRYPTED_TICKET *, struct KERB_AP_REQUEST *, struct _KERB_ENCRYPTION_KEY *, struct _LUID *, void **, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void **, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _KERB_CONTEXT **, union _LARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18002db10`
- `0x1800cf66c`

## callees

- `0x180006ddc`
- `0x1800072c0`
- `0x180016550`
- `0x180020e10`
- `0x1800210e0`
- `0x180024480`
- `0x18002bd40`
- `0x1800457f0`
- `0x180045e58`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180045f15`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180045fd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180045f15`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180045fd1`
- `ntdll!RtlInitUnicodeString` at `0x180045f2d`
- `ntdll!RtlInitUnicodeString` at `0x180045f45`
- `ntdll!RtlInitUnicodeString` at `0x180045f5d`
- `ntdll!RtlInitUnicodeString` at `0x180045f2d`
- `ntdll!RtlInitUnicodeString` at `0x180045f45`
- `ntdll!RtlInitUnicodeString` at `0x180045f5d`
- `ntdll!RtlEnterCriticalSection` at `0x18004608a`
- `ntdll!RtlEnterCriticalSection` at `0x18004608a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800460a2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800460a2`

## string_xrefs

- `0x1800460d6`: `KerbCreateServerContext`

## pseudocode

```c

```
