# KerbMakeHttpCall(_KERB_PROXY_LOGON_CRED *,_UNICODE_STRING *,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *,ulong,uchar *,_UNICODE_STRING *)

- ea: `0x180051720`
- end: `0x1800520ec`
- name: `?KerbMakeHttpCall@@YAJPEAU_KERB_PROXY_LOGON_CRED@@PEAU_UNICODE_STRING@@PEAU_KERB_MESSAGE_BUFFER@@2KPEAE1@Z`
- size: `2508`
- prototype: `__int64 __fastcall(struct _KERB_PROXY_LOGON_CRED *, struct _UNICODE_STRING *, struct _KERB_MESSAGE_BUFFER *, struct _KERB_MESSAGE_BUFFER *, unsigned int, unsigned __int8 *, struct _UNICODE_STRING *Destination)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800363f4`

## callees

- `0x180005320`
- `0x1800068d0`
- `0x1800093f0`
- `0x18000aa74`
- `0x18000b300`
- `0x18001018c`
- `0x180010328`
- `0x1800107f8`
- `0x180037c64`
- `0x180039ae4`
- `0x1800514dc`
- `0x180051720`
- `0x1800520f4`
- `0x18005228c`
- `0x18006d6a4`
- `0x18007108c`
- `0x18008b70c`
- `0x180097308`
- `0x18009a5c4`
- `0x18009a624`
- `0x18009a738`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051c19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051c19`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051d4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051d4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051e7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051ea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052019`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052043`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052075`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005209f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051e7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051ea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052019`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052043`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052075`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005209f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005196c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180051979`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180051f82`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180051f8f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005196c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180051979`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180051f82`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180051f8f`
- `ntdll!RtlEnterCriticalSection` at `0x1800517d5`
- `ntdll!RtlEnterCriticalSection` at `0x1800519b3`
- `ntdll!RtlEnterCriticalSection` at `0x1800517d5`
- `ntdll!RtlEnterCriticalSection` at `0x1800519b3`
- `ntdll!RtlLeaveCriticalSection` at `0x180051823`
- `ntdll!RtlLeaveCriticalSection` at `0x180051bc4`
- `ntdll!RtlLeaveCriticalSection` at `0x180051c27`
- `ntdll!RtlLeaveCriticalSection` at `0x180051c86`
- `ntdll!RtlLeaveCriticalSection` at `0x180051c99`
- `ntdll!RtlLeaveCriticalSection` at `0x180051cad`
- `ntdll!RtlLeaveCriticalSection` at `0x180051823`
- `ntdll!RtlLeaveCriticalSection` at `0x180051bc4`
- `ntdll!RtlLeaveCriticalSection` at `0x180051c27`
- `ntdll!RtlLeaveCriticalSection` at `0x180051c86`
- `ntdll!RtlLeaveCriticalSection` at `0x180051c99`
- `ntdll!RtlLeaveCriticalSection` at `0x180051cad`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800519d3`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800519d3`
- `CRYPT32!CertFreeCertificateContext` at `0x180051b10`
- `CRYPT32!CertFreeCertificateContext` at `0x1800520ad`
- `CRYPT32!CertFreeCertificateContext` at `0x180051b10`
- `CRYPT32!CertFreeCertificateContext` at `0x1800520ad`

## string_xrefs

- `0x180051aaf`: `onecore\ds\security\protocols\kerberos\client2\krbproxy.cxx`
- `0x180051b87`: `KerbImpersonateClient failed: %#x, LogonUser %d, logon session %#x:%x\n`
- `0x180051fc9`: `failed to create kdc proxy cache entry: %#x`

## pseudocode

```c

```
