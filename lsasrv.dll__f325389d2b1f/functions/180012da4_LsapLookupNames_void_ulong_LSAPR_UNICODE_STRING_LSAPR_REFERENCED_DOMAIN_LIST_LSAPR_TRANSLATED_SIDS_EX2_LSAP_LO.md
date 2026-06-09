# LsapLookupNames(void *,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST * *,_LSAPR_TRANSLATED_SIDS_EX2 *,_LSAP_LOOKUP_LEVEL,ulong *,ulong,ulong)

- ea: `0x180012da4`
- end: `0x180013b0b`
- name: `?LsapLookupNames@@YAJPEAXKPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@W4_LSAP_LOOKUP_LEVEL@@PEAKKK@Z`
- size: `3431`
- prototype: ``
- caller_count: `6`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800117f0`
- `0x18005d528`
- `0x180084aa0`
- `0x180106b60`
- `0x180106dc0`
- `0x180107040`

## callees

- `0x1800101e0`
- `0x180012da4`
- `0x180013b20`
- `0x18001b1f4`
- `0x1800284d4`
- `0x180037490`
- `0x1800388a0`
- `0x180052d00`
- `0x180064474`
- `0x180064628`
- `0x180065340`
- `0x180071d00`
- `0x180071e20`
- `0x180072df0`
- `0x180074fe4`
- `0x18008a384`
- `0x18008d958`
- `0x18008dd08`
- `0x18008ddec`
- `0x180091f70`
- `0x18009626c`
- `0x180096388`
- `0x1800ada18`
- `0x1800b1b90`
- `0x1800b1f9c`
- `0x1800b24d0`
- `0x1800b9304`
- `0x1800f4928`
- `0x180117a6c`
- `0x180117d14`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001303f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013859`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013879`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001390d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001391f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013a13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013a27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013a3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001303f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013859`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013879`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001390d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001391f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013a13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013a27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013a3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012fc4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012fe9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013069`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013151`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013176`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013197`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800131b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012fc4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012fe9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013069`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013151`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013176`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013197`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800131b8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012eab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180013a55`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012eab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180013a55`
- `ntdll!RtlInitUnicodeString` at `0x180013010`
- `ntdll!RtlInitUnicodeString` at `0x1800132d9`
- `ntdll!RtlInitUnicodeString` at `0x1800132eb`
- `ntdll!RtlInitUnicodeString` at `0x180013010`
- `ntdll!RtlInitUnicodeString` at `0x1800132d9`
- `ntdll!RtlInitUnicodeString` at `0x1800132eb`

## string_xrefs

- `0x18001375a`: `onecore\ds\security\base\lsa\server\dspolicy\dbluname.cxx`
- `0x1800137ba`: `onecore\ds\security\base\lsa\server\dspolicy\dbluname.cxx`

## pseudocode

```c

```
