# AcquireResidentSystemAddressInCpuHostAperture

- ea: `0x1400cede8`
- end: `0x1400cefb7`
- name: `AcquireResidentSystemAddressInCpuHostAperture`
- size: `463`
- prototype: `__int64 __usercall@<rax>(struct VIDMM_PHYSICAL_ALLOC *@<rcx>, unsigned __int64@<rdx>, VIDMM_CPU_HOST_APERTURE *this@<r8>, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140103b88`

## callees

- `0x14002f7d0`
- `0x140059030`
- `0x1400cede8`
- `0x1400dbb28`
- `0x140104020`
- `0x1401043b8`
- `0x14010d408`
- `0x1401258f8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400cef38`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cef38`
- `watchdog!WdLogSingleEntry0` at `0x1400cef18`
- `watchdog!WdLogSingleEntry0` at `0x1400cef18`
- `watchdog!WdLogSingleEntry1` at `0x1400cee3a`
- `watchdog!WdLogSingleEntry1` at `0x1400cee82`
- `watchdog!WdLogSingleEntry1` at `0x1400ceec6`
- `watchdog!WdLogSingleEntry1` at `0x1400cee3a`
- `watchdog!WdLogSingleEntry1` at `0x1400cee82`
- `watchdog!WdLogSingleEntry1` at `0x1400ceec6`

## pseudocode

```c

```
