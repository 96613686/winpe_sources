# LsapDbSlowQueryInformationPolicy(void *,_POLICY_INFORMATION_CLASS,_LSAPR_POLICY_INFORMATION * *)

- ea: `0x18008f168`
- end: `0x18008fb68`
- name: `?LsapDbSlowQueryInformationPolicy@@YAJPEAXW4_POLICY_INFORMATION_CLASS@@PEAPEAT_LSAPR_POLICY_INFORMATION@@@Z`
- size: `2560`
- prototype: `__int64 __fastcall(void *, enum _POLICY_INFORMATION_CLASS, union _LSAPR_POLICY_INFORMATION **)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e530`
- `0x18008ef90`
- `0x18008f09c`

## callees

- `0x18000f130`
- `0x180011278`
- `0x18001b520`
- `0x18003a848`
- `0x1800533b0`
- `0x18008f168`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800bc040`
- `0x1800bd6e0`
- `0x1801013ac`
- `0x18010cbd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f62e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f62e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fa24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fa5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fa93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fac5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008faf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fa24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fa5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fa93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fac5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008faf4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f4f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f577`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f5e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f689`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f6ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f825`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f89f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f904`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f4f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f577`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f5e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f689`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f6ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f825`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f89f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f904`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008f5c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18008f5c3`
- `ntdll!RtlInitUnicodeString` at `0x18008f612`
- `ntdll!RtlInitUnicodeString` at `0x18008f612`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtConvertSystemPolicyFromStorageToOldPublicFormat` at `0x18008f7af`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtConvertSystemPolicyFromStorageToOldPublicFormat` at `0x18008f7af`

## pseudocode

```c

```
