# KerbRetrieveDomainFromDn(_CERT_CONTEXT const *,_UNICODE_STRING *)

- ea: `0x180060ce4`
- end: `0x180060fbc`
- name: `?KerbRetrieveDomainFromDn@@YAEPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@@Z`
- size: `728`
- prototype: `unsigned __int8 __fastcall(const struct _CERT_CONTEXT *, struct _UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058f14`
- `0x18005f7fc`
- `0x18006dc2c`
- `0x1800c4d58`

## callees

- `0x180007e80`
- `0x18000b300`
- `0x180050fe0`
- `0x180060ce4`
- `0x180070680`
- `0x1800744cf`
- `0x18008b70c`
- `0x1800f1ea0`
- `0x1800f1ef4`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060f79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060f79`
- `ntdll!RtlInitUnicodeString` at `0x180060f16`
- `ntdll!RtlInitUnicodeString` at `0x180060f16`
- `CRYPT32!CryptDecodeObjectEx` at `0x180060d55`
- `CRYPT32!CryptDecodeObjectEx` at `0x180060d55`

## string_xrefs

- `0x180060f2f`: `No DC component in RDN\n`

## pseudocode

```c

```
