# LsapLookupSids(void *,_LSAPR_SID_ENUM_BUFFER *,_LSAPR_REFERENCED_DOMAIN_LIST * *,_LSAPR_TRANSLATED_NAMES_EX *,_LSAP_LOOKUP_LEVEL,ulong *,ulong,ulong)

- ea: `0x180011cdc`
- end: `0x180012d9c`
- name: `?LsapLookupSids@@YAJPEAXPEAU_LSAPR_SID_ENUM_BUFFER@@PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@W4_LSAP_LOOKUP_LEVEL@@PEAKKK@Z`
- size: `4288`
- prototype: ``
- caller_count: `5`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800119f0`
- `0x18005e2b0`
- `0x18007fa50`
- `0x18010d870`
- `0x18010dad0`

## callees

- `0x1800093b0`
- `0x180009410`
- `0x1800101e0`
- `0x180011cdc`
- `0x180013b20`
- `0x180014160`
- `0x1800143e0`
- `0x18001ddc0`
- `0x1800284d4`
- `0x180036610`
- `0x1800377c0`
- `0x1800381b4`
- `0x180038470`
- `0x180039400`
- `0x180039d24`
- `0x18003a0c0`
- `0x180052d00`
- `0x180061e88`
- `0x180071d00`
- `0x180072670`
- `0x180082230`
- `0x180097c3c`
- `0x1800ada18`
- `0x1800b1e74`
- `0x1800b1f9c`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800ec6cc`
- `0x18010d3a0`
- `0x18011d35c`
- `0x18011d6e4`
- `0x18011d850`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012122`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800123e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800124a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800126f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800127d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012927`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012c55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012c7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ccc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012122`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800123e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800124a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800126f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800127d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012927`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012c55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012c7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ccc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011e54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011ea8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011efa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011fdd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011e54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011ea8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011efa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011fdd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011da8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012699`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011da8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012699`
- `ntdll!RtlReleaseResource` at `0x18001208f`
- `ntdll!RtlReleaseResource` at `0x1800122c5`
- `ntdll!RtlReleaseResource` at `0x18001208f`
- `ntdll!RtlReleaseResource` at `0x1800122c5`
- `ntdll!RtlAcquireResourceShared` at `0x180012072`
- `ntdll!RtlAcquireResourceShared` at `0x180012072`
- `ntdll!RtlValidSid` at `0x1800125c9`
- `ntdll!RtlValidSid` at `0x1800125c9`
- `ntdll!EtwLogTraceEvent` at `0x18001261c`
- `ntdll!EtwLogTraceEvent` at `0x180012666`
- `ntdll!EtwLogTraceEvent` at `0x18001261c`
- `ntdll!EtwLogTraceEvent` at `0x180012666`
- `ntdll!RtlEqualSid` at `0x1800122df`
- `ntdll!RtlEqualSid` at `0x1800122df`

## pseudocode

```c

```
