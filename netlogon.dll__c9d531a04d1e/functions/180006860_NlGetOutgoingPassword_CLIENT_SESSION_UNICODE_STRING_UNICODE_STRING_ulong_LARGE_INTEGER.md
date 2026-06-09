# NlGetOutgoingPassword(_CLIENT_SESSION *,_UNICODE_STRING * *,_UNICODE_STRING * *,ulong *,_LARGE_INTEGER *)

- ea: `0x180006860`
- end: `0x180006ec0`
- name: `?NlGetOutgoingPassword@@YAJPEAU_CLIENT_SESSION@@PEAPEAU_UNICODE_STRING@@1PEAKPEAT_LARGE_INTEGER@@@Z`
- size: `1632`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, struct _UNICODE_STRING **, struct _UNICODE_STRING **, unsigned int *, union _LARGE_INTEGER *)`
- caller_count: `5`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180033a34`
- `0x180036df8`
- `0x180059e9c`
- `0x18005abe0`
- `0x18005af40`

## callees

- `0x180006860`
- `0x180007278`
- `0x18000d710`
- `0x18002a178`
- `0x1800366e8`
- `0x18003e294`
- `0x18003e71c`
- `0x18003f540`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a60`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006aeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006d95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e0a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a60`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006aeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006d95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006942`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006957`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006942`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006957`
- `LSASRV!LsarClose` at `0x180006bef`
- `LSASRV!LsarClose` at `0x180006bef`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x18000698f`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x18000698f`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180006ea4`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180006ea4`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180006e81`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180006e90`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180006e81`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180006e90`
- `LSASRV!LsarQuerySecret` at `0x180006d52`
- `LSASRV!LsarQuerySecret` at `0x180006d52`
- `ntdll!RtlInitUnicodeString` at `0x180006c50`
- `ntdll!RtlInitUnicodeString` at `0x180006c50`

## string_xrefs

- `0x180006a02`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180006d2d`: `NlGetOutgoingPassword: cannot NlOpenSecret 0x%lx\n`

## pseudocode

```c

```
