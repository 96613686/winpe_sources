# FixPrinterSecurityDescriptor(void * *,void * *,ulong,ulong,int)

- ea: `0x180098ccc`
- end: `0x180098f35`
- name: `?FixPrinterSecurityDescriptor@@YAKPEAPEAX0KKH@Z`
- size: `617`
- prototype: `unsigned int(void **, void **, unsigned int, unsigned int, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800522f8`
- `0x180053d10`
- `0x18007bd7c`
- `0x1800982c8`

## callees

- `0x180027594`
- `0x18003ea2c`
- `0x180046a20`
- `0x180098590`
- `0x180098ccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098ed8`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180098d5e`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180098e42`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180098d5e`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180098e42`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180098e8c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180098e8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098eb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ee3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098eec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ef5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098efe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098eb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ee3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098eec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ef5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098efe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098d90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098dad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098dca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098de7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098d90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098dad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098dca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098de7`

## string_xrefs

- `0x180098f0f`: `FixPrinterSecurityDescriptor`
- `0x180098f08`: `Failed to adjust printer security descriptor`

## pseudocode

```c

```
