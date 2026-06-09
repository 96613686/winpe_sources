# AcquireResidentSystemAddressInCpuHostAperture

- ea: `0x1400c9160`
- end: `0x1400c932f`
- name: `AcquireResidentSystemAddressInCpuHostAperture`
- size: `463`
- prototype: `__int64 __usercall@<rax>(struct VIDMM_PHYSICAL_ALLOC *@<rcx>, unsigned __int64@<rdx>, VIDMM_CPU_HOST_APERTURE *this@<r8>, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400f9288`

## callees

- `0x140031934`
- `0x140058760`
- `0x1400c9160`
- `0x1400d3838`
- `0x1400f9720`
- `0x1400f9ab8`
- `0x1401090c8`
- `0x140121f38`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400c92b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c92b0`
- `watchdog!WdLogSingleEntry0` at `0x1400c9290`
- `watchdog!WdLogSingleEntry0` at `0x1400c9290`
- `watchdog!WdLogSingleEntry1` at `0x1400c91b2`
- `watchdog!WdLogSingleEntry1` at `0x1400c91fa`
- `watchdog!WdLogSingleEntry1` at `0x1400c923e`
- `watchdog!WdLogSingleEntry1` at `0x1400c91b2`
- `watchdog!WdLogSingleEntry1` at `0x1400c91fa`
- `watchdog!WdLogSingleEntry1` at `0x1400c923e`

## pseudocode

```c

```
