# NlGetOutgoingPassword(_CLIENT_SESSION *,_UNICODE_STRING * *,_UNICODE_STRING * *,ulong *,_LARGE_INTEGER *)

- ea: `0x180006a94`
- end: `0x180007143`
- name: `?NlGetOutgoingPassword@@YAJPEAU_CLIENT_SESSION@@PEAPEAU_UNICODE_STRING@@1PEAKPEAT_LARGE_INTEGER@@@Z`
- size: `1711`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, struct _UNICODE_STRING **, struct _UNICODE_STRING **, unsigned int *, union _LARGE_INTEGER *)`
- caller_count: `5`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180035924`
- `0x180038f68`
- `0x18005dfe0`
- `0x18005ee10`
- `0x18005f180`

## callees

- `0x180006a94`
- `0x180007518`
- `0x18000dd00`
- `0x18002b964`
- `0x1800387d8`
- `0x1800409c4`
- `0x180040f18`
- `0x180041e68`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ca6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006d37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ff9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007074`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ca6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006d37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ff9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b91`
- `LSASRV!LsarClose` at `0x180006e41`
- `LSASRV!LsarClose` at `0x180006e41`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180006bcf`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180006bcf`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180007120`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180007120`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x1800070f1`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180007106`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x1800070f1`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180007106`
- `LSASRV!LsarQuerySecret` at `0x180006fb0`
- `LSASRV!LsarQuerySecret` at `0x180006fb0`
- `ntdll!RtlInitUnicodeString` at `0x180006ea8`
- `ntdll!RtlInitUnicodeString` at `0x180006ea8`

## string_xrefs

- `0x180006c48`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x180006f8b`: `NlGetOutgoingPassword: cannot NlOpenSecret 0x%lx\n`

## pseudocode

```c

```
