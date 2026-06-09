# NlSitesAddSubnetFromDs_Old(uchar *)

- ea: `0x180042278`
- end: `0x180042631`
- name: `?NlSitesAddSubnetFromDs_Old@@YAKPEAE@Z`
- size: `953`
- prototype: `unsigned int __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180041de0`
- `0x18007070c`

## callees

- `0x180007278`
- `0x180007b50`
- `0x1800164f0`
- `0x18003f684`
- `0x1800416f0`
- `0x180042014`
- `0x180042278`
- `0x180042638`
- `0x180042d34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004248e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004248e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800425cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800425ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800425fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800425cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800425ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800425fc`
- `LSASRV!LsaIGetSiteName` at `0x1800422a8`
- `LSASRV!LsaIGetSiteName` at `0x1800422a8`
- `LSASRV!LsaIQuerySubnetInfo` at `0x18004237a`
- `LSASRV!LsaIQuerySubnetInfo` at `0x18004237a`
- `LSASRV!LsaIFree_LSAP_SUBNET_INFO` at `0x18004260b`
- `LSASRV!LsaIFree_LSAP_SUBNET_INFO` at `0x18004260b`
- `LSASRV!LsaIFree_LSAP_SITENAME_INFO` at `0x18004261a`
- `LSASRV!LsaIFree_LSAP_SITENAME_INFO` at `0x18004261a`
- `ntdll!RtlEqualUnicodeString` at `0x18004242b`
- `ntdll!RtlEqualUnicodeString` at `0x18004242b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800425b8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800425b8`
- `ntdll!RtlEnterCriticalSection` at `0x18004257c`
- `ntdll!RtlEnterCriticalSection` at `0x18004257c`

## string_xrefs

- `0x18004234c`: `Set GC-running bit after netlogon.dll unload\n`
- `0x1800424e4`: `%wZ: %wZ: Cannot add subnet-to-site mapping to cache: %ld\n`

## pseudocode

```c

```
