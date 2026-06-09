# NlSitesAddSubnetFromDs_Old(uchar *)

- ea: `0x180044f3c`
- end: `0x180045338`
- name: `?NlSitesAddSubnetFromDs_Old@@YAKPEAE@Z`
- size: `1020`
- prototype: `unsigned int __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180044a68`
- `0x180075b60`

## callees

- `0x180007518`
- `0x180007e90`
- `0x180016f10`
- `0x180041fbc`
- `0x1800442dc`
- `0x180044cc0`
- `0x180044f3c`
- `0x180045340`
- `0x180045ad0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045164`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045164`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800452b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800452da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800452f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800452b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800452da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800452f0`
- `LSASRV!LsaIGetSiteName` at `0x180044f6c`
- `LSASRV!LsaIGetSiteName` at `0x180044f6c`
- `LSASRV!LsaIQuerySubnetInfo` at `0x180045044`
- `LSASRV!LsaIQuerySubnetInfo` at `0x180045044`
- `LSASRV!LsaIFree_LSAP_SUBNET_INFO` at `0x180045305`
- `LSASRV!LsaIFree_LSAP_SUBNET_INFO` at `0x180045305`
- `LSASRV!LsaIFree_LSAP_SITENAME_INFO` at `0x18004531a`
- `LSASRV!LsaIFree_LSAP_SITENAME_INFO` at `0x18004531a`
- `ntdll!RtlEqualUnicodeString` at `0x1800450fb`
- `ntdll!RtlEqualUnicodeString` at `0x1800450fb`
- `ntdll!RtlLeaveCriticalSection` at `0x18004529a`
- `ntdll!RtlLeaveCriticalSection` at `0x18004529a`
- `ntdll!RtlEnterCriticalSection` at `0x180045258`
- `ntdll!RtlEnterCriticalSection` at `0x180045258`

## string_xrefs

- `0x180045016`: `Set GC-running bit after netlogon.dll unload\n`
- `0x1800451c0`: `%wZ: %wZ: Cannot add subnet-to-site mapping to cache: %ld\n`

## pseudocode

```c

```
